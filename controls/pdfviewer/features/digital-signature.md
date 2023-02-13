---
title: Digital Signature
page_title: Digital Signature - WinForms PdfViewer Control
description: With WinForms PdfViewer you are able to both display and verify documents within your application and make sure that it has not been tampered with.
slug: radpdfviewer-features-digital-signature
tags: digital, signature
published: True
position: 0
---

# Digital Signature

With __RadPdfViewer__ you are able to both display,sign and verify documents within your application and make sure that it has not been tampered with.

This article contains the following sections:

* [What is a Digital Signature?](#what-is-a-digital-signature)

* [Cryptography Standards](#cryptography-standards)

* [Signature Field](#signature-field)

* [Validation](#validation)

* [Limitations](#limitations)

## What is a Digital Signature?

The digital signature is the equivalent of the handwritten signature and is intended to solve security problems in the digital communication. The signature is unique to each signer and is widely used to confirm that the document content originated from the signer and has not been modified in any way.

The digital signatures rely on a mathematical algorithm, which generates a public and a private key. The private key is used to create the signature while the user signs the document. The algorithm creates a hash over the document data and uses the signer's private key to encrypt this hash. The result of this operation is the digital signature of the document. Once the document is signed, any change on it invalidates the hash, respectively the signature is invalidated.

## Cryptography Standards

RadPdfViewer enables you to validate signature fields using standard  Cryptography Standards. Following is a list of them:

* adbe.x509.rsa_sha1 ([PKCS #1](https://tools.ietf.org/html/rfc8017))

* adbe.pkcs7.sha1 ([PKCS #7](https://tools.ietf.org/html/rfc2315))

* adbe.pkcs7.detached (PKCS #7 Detached)

For all other formats you might need, there is a flexible API enabling you to implement them. To do so, you should inherit the [SignatureValidationHandlerBase](https://docs.telerik.com/devtools/winforms/api/telerik.windows.documents.fixed.model.digitalsignatures.signaturevalidationhandlerbase.html) and register the new handler in the [SignatureValidationHandlersManager](https://docs.telerik.com/devtools/winforms/api/telerik.windows.documents.fixed.model.digitalsignatures.signaturevalidationhandlersmanager.html). The base class exposes the __ValidationOverride__ method, so you can implement the logic for validating any type of signature. Once the validation is done in the body of this method, an instance of the [SignatureValidationResult](https://docs.telerik.com/devtools/winforms/api/telerik.windows.documents.fixed.model.digitalsignatures.signaturevalidationresultbuilder.html) class will be returned containing data for the signature status.


## Signature Field

The information about a digital signature in a document is stored in a signature field, which can be obtained through the **AcroForm** property of the document. This field exposes a property called __Signature__, which is responsible for validating.

## Signing 

When a document containing a signature field is loaded in **RadPdfViewer**, you can apply a signature to it. This is done through the **SignSignatureDialog**. This dialog gives you the ability to choose a .pfx file representing the certificate and enter the password for it. Clicking the Sign button prompts you to save the signed document to a new file. The newly saved file then opens in **RadPdfViewer**.

![WinForms RadPdfViewer Signing](images/pdfviewer-digital-signature003.gif)

>note As of R1 2021 RadPdfViewerElement offers the cancelable **SignatureDialogShowing** and **SignSignatureDialogShowing** events. They allow customizing or changing the signature dialogs in **RadPdfViewer**.

## Validation

In the PDF document model, the validation is performed per signature. For a valid signed document is considered one that has not been changed after the signing and all of its certificates have valid trusted root certificate.

### Using Signature Panel

The signature panel of RadPdfViewer detects when the imported document contains a signature, validates the document and shows the final result to the user. 

>caption Figure 1: SignaturePanel showing signature status
![WinForms RadPdfViewer SignaturePanel showing signature status](images/pdfviewer-digital-signature001.png)

>note You can use the __PdfViewerElement.AllowSignatureDialog__ property to enable/disable the dialog.

### Using SignaturePropertiesDialog

The SignaturePanel detects if any signatures are present and validates them. However, the panel shows only the end result of the validation and doesn't expose a detailed information on which one is invalid and why. You can obtain this information from the SignaturePropertiesDialog (Just click the signature to open the dialog). 

**Figure 2** shows how it looks like the SignaturePropertiesDialog when visualizing a signature whose validation result is Unknown.

>caption Figure 2: SignaturePropertiesDialog showing the status of a signature
![WinForms RadPdfViewer SignaturePropertiesDialog showing the status of a signature](images/pdfviewer-digital-signature002.png)


### Validate a Signature in Code-Behind

The **Signature** class exposes two methods allowing you to validate a signature:

* **Validate()**: The method accepts a parameter of type SignatureValidationProperties which it uses while validating the signature. The **SignatureValidationProperties** class exposes the following properties:
    *  **Chain**: Gets or sets the chain used to validate the certificate that signed the digital signature. It is of type [X509Chain](https://msdn.microsoft.com/en-us/library/system.security.cryptography.x509certificates.x509chain(v=vs.110).aspx).
    *  **ChainStatusFlags**: Gets or sets the chain status flags which describes the used signature certificate as invalid. It is of type [X509ChainStatusFlags](https://msdn.microsoft.com/en-us/library/system.security.cryptography.x509certificates.x509chainstatusflags(v=vs.110).aspx).
    
    Validate() returns object of type [SignatureValidationResult](http://docs.telerik.com/devtools/winforms/api/html/t_telerik_windows_pdf_documents_fixed_model_digitalsignatures_signaturevalidationresult.htm).

* **TryValidate()**: This method returns a boolean value indicating whether the validation succeeded or not. There are two overloads of this method. The first one accepts an out parameter containing a [SignatureValidationResult](https://docs.telerik.com/devtools/winforms/api/telerik.windows.documents.fixed.model.digitalsignatures.signaturevalidationresult.html) object and the second one allows you to also pass **SignatureValidationProperties**.

>The Validate() method throws an exception if there is a problem with the signature, while TryValidate() returns false in similar cases.

**Example 1** shows how the validation can be used.

#### Example 1: Validate a field


{{source=..\SamplesCS\PdfViewer\DigitalSignatureCode.cs region=DigitalSignatureCode_1}} 
{{source=..\SamplesVB\PdfViewer\DigitalSignatureCode.vb region=DigitalSignatureCode_1}} 
````C#
string validationStatus;
// For simplicity, the example handles only the first signature.
SignatureField firstSignatureField = this.pdfViewer.Document.AcroForm.FormFields.FirstOrDefault(field => field.FieldType == FormFieldType.Signature) as SignatureField;
if (firstSignatureField != null && firstSignatureField.Signature != null)
{
    SignatureValidationResult validationResult;
    if (firstSignatureField.Signature.TryValidate(out validationResult))
    {
        if (!validationResult.IsDocumentModified)
        {
            if (validationResult.IsCertificateValid)
            {
                validationStatus = "Valid";
            }
            else
            {
                validationStatus = "Unknown";
            }
        }
        else
        {
            validationStatus = "Invalid";
        }
    }
    else
    {
        validationStatus = "Invalid";
    }
}
else
{
    validationStatus = "None";
}

````
````VB.NET
Dim validationStatus As String
' For simplicity, the example handles only the first signature.
Dim firstSignatureField As SignatureField = TryCast(Me.pdfViewer.Document.AcroForm.FormFields.FirstOrDefault(Function(field) field.FieldType = FormFieldType.Signature), SignatureField)
If firstSignatureField IsNot Nothing AndAlso firstSignatureField.Signature IsNot Nothing Then
    Dim validationResult As SignatureValidationResult = Nothing
    If firstSignatureField.Signature.TryValidate(validationResult) Then
        If Not validationResult.IsDocumentModified Then
            If validationResult.IsCertificateValid Then
                validationStatus = "Valid"
            Else
                validationStatus = "Unknown"
            End If
        Else
            validationStatus = "Invalid"
        End If
    Else
        validationStatus = "Invalid"
    End If
Else
    validationStatus = "None"
End If

```` 

 
{{endregion}} 
 


## Limitations

There are few limitations related to the usage of a digital signature in RadPdfViewer.

* The validation of a signature depends on the bytes representing the document. Thus, to validate a signature, the stream used to import the document must be still open.

* The validation is always performed for the current field, against the state of the document in the moment of importing.
