# The need to share PSD2 SCA proof with the PSU to meet GDPR requirements

Michael Adams | 5 January 2018

Following on from my post earlier this week on the need to share proof of consent, I believe GDPR will also have an impact on the method of capturing 'Strong Customer Authentication' (SCA) for PSD2. This is because GDPR deems data "relating to an identified or identifiable natural person ('data subject')" to be personal data. An electronic copy of the SCA proof must therefore be made available to the PSU / data subject, on request. This will be of great value to the PSU in the event of a dispute.

As discussed previously, this requirement can be easily met via Advanced Electronic Signatures or preferably Qualified Electronic Signatures, when using an eIDAS smartcard. 

To support this idea, I have today generated three Qualified Electronic Signatures using the Quali-Sign app on my Android smartphone, connected to my Estonian eResidency (eIDAS) smartcard, via a USB reader. Note for clarity, that the Qualified Signatures are created by the smartcard and the XML signature structure is created by the mobile app.

\-----------------------------------------------------------------------------------------------------

1) Example of Embedded SCA. 

Here is an example of the 'Embedded' SCA model. In this example, the SCA capture procedure is performed by a 'Third Party Provider' issued mobile app combined with an eIDAS smartcard (bank issued or national identity card). In this scenario, a CommitmentType of "Proof of origin" is specified. This "indicates that the signer recognizes to have created, approved and sent the signed data".

Unformatted 

## /futurium/en/file/180105xadesenvelopingscaembeddedinitiationtxt180105xadesenvelopingscaembeddedinitiation.txt

![Plain text icon](https://ec.europa.eu/futurium/modules/file/icons/text-plain.png)[180105xadesenvelopingscaembeddedinitiation.txt](https://ec.europa.eu/futurium/sites/futurium/files/180105xadesenvelopingscaembeddedinitiation.txt)

Formatted 

## /futurium/en/file/180105xadesenvelopingscaembeddedinitiationformatteddocx180105xadesenvelopingscaembeddedinitiation_formatted.docx

![File](https://ec.europa.eu/futurium/modules/file/icons/x-office-document.png)[180105xadesenvelopingscaembeddedinitiation_formatted.docx](https://ec.europa.eu/futurium/sites/futurium/files/180105xadesenvelopingscaembeddedinitiation_formatted.docx)

\------------------------------------------------------------------------------------------------------

2) Examples of Decoupled SCA 

The following examples implement the 'Decoupled' SCA model, whereby the SCA is performed via a dedicated (i.e. single purpose) mobile app issued by the bank  / Account Servicing Payment Services Provider (ASPSP), together with an eIDAS smartcard (bank issued or national identity card). Note, in this context, a bank may choose to allow their customer to dispense with their smartcard and use the smartphone to generate the signatures. However these signatures will not be recognised as Qualified Electronic Signatures (as a smartphone is not currently recognised as a certified Qualified Signature Creation Device)  and as such will not benefit from the legal certainty offered by eIDAS. 

\----------------------------------------------------------------------------------------------------

2a) Decoupled SCA : Payment Approval

In this scenario, a CommitmentType of "Proof of approval" is specified. This "indicates that the signer has approved the content of the signed data."

Unformatted 

![Plain text icon](https://ec.europa.eu/futurium/modules/file/icons/text-plain.png)[180105xadesenvelopingscadecoupledapproval.txt](https://ec.europa.eu/futurium/sites/futurium/files/180105xadesenvelopingscadecoupledapproval_0.txt)

Formatted 

![File](https://ec.europa.eu/futurium/modules/file/icons/x-office-document.png)[180105xadesenvelopingscadecoupledapproval.docx](https://ec.europa.eu/futurium/sites/futurium/files/180105xadesenvelopingscadecoupledapproval.docx)

\-----------------------------------------------------------------------------------------------------

2b) Decoupled SCA : Request for Cancellation (of payment)

This scenario requires the ASPSP to include a proprietary "Cancellation Request" CommitmentType in their signature policy.

Unformatted 

![Plain text icon](https://ec.europa.eu/futurium/modules/file/icons/text-plain.png)[180105xadesenvelopingscadecoupledcancellationrequest.txt](https://ec.europa.eu/futurium/sites/futurium/files/180105xadesenvelopingscadecoupledcancellationrequest.txt)

Formatted 

![File](https://ec.europa.eu/futurium/modules/file/icons/x-office-document.png)[180105xadesenvelopingscadecoupledcancellationrequest.docx](https://ec.europa.eu/futurium/sites/futurium/files/180105xadesenvelopingscadecoupledcancellationrequest.docx)

\----------------------------------------------------------------------------------------------------

You can verify the signatures using [this EU provided tool](https://joinup.ec.europa.eu/dss-webapp/validation). Please select the unformatted file as the 'Signed File'. You do not need to select an Original File because the signature file contains an encoded copy of the original payment file. Please also select a Validation level of 'Validation process for basic signatures'. 

Here is a sample report produced by the tool. 

![PDF icon](https://ec.europa.eu/futurium/modules/file/icons/application-pdf.png)[dss-detailed-report.pdf](https://ec.europa.eu/futurium/sites/futurium/files/dss-detailed-report.pdf)

Note that the signature has fully passed as a QES. There is a warning against the question "Are the issuer distinguished name and the serial number equal?". There appears to be an issue with the verification report as the specification clearly states that the IssuerSerialV2 tag must not be included. The alternative [ETSI PlugTests](http://signatures-conformance-checker.etsi.org/pub/index.shtml) conformance checker tool will reject the signature if this tag is included.

Also, if you would like to view the original payment file, you can do this by decoding the content of the <Object> tag [using this Base64 decoder tool](https://www.base64decode.org/). 

Source: [ec.europa.eu](https://ec.europa.eu/futurium/en/eidas-observatory/need-share-psd2-sca-proof-psu-meet-gdpr-requirements)