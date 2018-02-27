# An overview of the PSD2 Regulatory Technical Standard

[Sundeep Tengur](https://blogs.sas.com/content/author/sundeeptengur/) on October 3, 2017

**This discussion of the Regulatory Technical Standards (RTS) is the third post in a series explaining the Revised Payment Service Directive (PSD2) and how it will affect banks. For background, read my two previous posts, PSD2: Understanding the new payments regulation in Europe and PSD2: How new European payment regulations could elevate fraud risk.**

The European Commission has set out the legislative framework for the new directive and has tasked the European Banking Authority (EBA) to define the standards for the implementation of PSD2.

The RTS defines the technical framework for the implementation of PSD2 with primary focus on strong customer authentication (SCA) and on a common and secure connection. In short, we could say that PSD2 covers the “what” aspect of the regulation whereas the RTS defines the “how.” Here, you'll find a whistle-stop tour of a few key headlines from the RTS.

### Strong customer authentication

The RTS defines minimum requirements such as two-factor authentication to secure electronic transactions and prevent data theft, impersonation or fraud. Under PSD2, all payment service providers will therefore be required to apply SCA every time a payer initiates an electronic payment transaction, with a few exemptions detailed below.

A process known as dynamic linking is also introduced under the SCA where a valid set of authentication components will generate an authentication code specific to the amount and beneficiary defined at the payment initiation stage. This is an important measure to mitigate risks of fraud, session hijacks involving man-in-the-middle attacks or payment repudiation.

Whilst all payment providers will be responsible for ensuring SCA is applied, account servicing payment service providers (i.e. the banks) will be responsible for its design, implementation and audit. This means that banks will bear the added pressure of securing third-party transactions as well as allowing third-party payment providers (TPPs) access to their authentication infrastructure. Authentication cannot be delegated to TPPs; banks are required to conduct their own authentication regardless of the anti-impersonation measures implemented by the third parties.

### SCA exemptions

It’s worth highlighting the latest practical exemptions for applying SCA:

- The threshold for single transactions has increased to €50 for contactless card payments. Payment providers have the option to bypass SCA for five consecutive transactions.
- The low value transactions threshold has been increased from €10 to €30, with a cumulative value of €100 or five consecutive non-SCA transactions, aligned to the contactless exemption above.
- A new exemption based on Transaction Risk Analysis, which will apply to remote transactions below a monetary threshold ranging from €100 to €500 depending on the payment service provider's reference fraud rate.
- Exemption for unattended terminals regarding services such as paying for public transport or parking fares.
- For trusted beneficiaries defined by the payer.

### Third party access

Under PSD2, third party providers (TPPs) will be granted consented access to customer information through the banks’ infrastructure to deliver new value-added services. Given the strategic and operational impact of this change, there has been wide speculation on how the access-to-account (XS2A) mechanism would work, and concerns echoed around malware attacks, fraud propensity and data privacy (driven by the General Data Protection Regulation).

To enable XS2A with, banks are required to offer a communication interface for TPP requests. This TPP interface should have the same functionality and deliver the same level of support as for customers transacting directly with their bank.

The European Banking Authority has suggested the use of ISO 20022 as a potential candidate for the interface format but the RTS does not provide any prescriptive guidance on how exactly XS2A is to be implemented. Whilst there are no regulatory-defined interface formats yet, several industry consortia such as the Berlin Group and the UK’s Open Banking Working Group have published proposed interface templates that banks can use as a baseline.

### Screen-scraping vs. APIs

There has been a long debate on whether screen scraping of data would be allowed under PSD2. Screen-scraping involves extracting data from any online source, often using informal and anonymized techniques as opposed to using an application programming interface (API), which can provide a dedicated interface to communicate with another system. The latest revision of the RTS stipulates that if a bank offers a dedicated API, third party providers are required to use it. In other cases, where APIs do not exist or where the API is unavailable for over 30 seconds, screen-scraping is permissible, but TPPs are required to digitally sign the messages to identify themselves. This is a critical measure to preserve the integrity of customer data and contributes to mitigating data breaches through malware attacks.

### Fraud reporting

The final RTS specifies that the methodology and models used by payment providers to calculate the fraud rates must be documented and made available to local regulatory authorities as well as the European Banking Authority (EBA). This means that the EBA will have access to rich fraud data from individual payment service providers (PSPs) rather than relying on high-level aggregated data shared by national authorities. Moreover, the EU Commission has specified details on how payment service providers need to calculate the risk score of each payment transaction by considering:

- Previous spending patterns by the payment service user.
- Payment transaction history of each PSP’s end user.
- The location of the payer and of the payee at the time of the payment transaction, if applicable.
- Abnormal behavioural payment patterns of the user compared to historical profile.
- Device or software usage logs for the end-user, if applicable.
- And more.

### Real-time fraud detection

We may recall a previous RTS draft which mandated real-time fraud detection to detect and block fraudulent payments but the EBA have since revised their stance on this requirement. The final draft preconizes a pragmatic risk-based fraud approach, balancing customer experience and fraud management. A multi-tiered strategy will therefore be applied where high risk transactions are blocked for suspected fraud, and low risk transactions potentially bypassing SCA.

### Next steps

The final RTS was published by the European Banking Authority in February 2017 and will be applicable 18 months after its adoption by the EU Commission, likely to be third quarter 2018 at the earliest. This is a short timeframe considering the strategic impact and implementation challenges required. Banks therefore need to be proactive and extend their digital transformation programmes to cater for the requirements of PSD2 through external APIs, extended fraud detection and adaptive customer authentication mechanisms.

PSD2 and the RTS are indeed a paradigm shift for many established organisations. Opening their infrastructure for third party access is no simple feat as it impacts several key areas such as data governance, fraud management, operational risk, IT security, etc.

Analytics can help on this journey towards a richer and open banking ecosystem.  The ability to react quickly, in real time, to changing events (which could be precursors of fraud or cyber-attacks) while leveraging the power of machine learning, can be embedded in detection methodology. Using advanced analytics through anomaly detection and peer-group analysis can help block account takeover attempts through XS2A while delivering a frictionless journey for genuine customers.

In short, analytics can empower organisations to adapt to change and mitigate future threats through proactive use of analytics.

Source: [blogs.sas.com](https://blogs.sas.com/content/sascom/2017/10/03/overview-psd2-regulatory-technical-standard/)