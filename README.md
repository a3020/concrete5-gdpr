This page serves as an idea dump from the #gdpr channel of concrete5 Slack

To contribute ideas, please join the Slack channel above.
##General

The General data protection regulation is a law that will be active in May 2018 and affect any internet-wide collection, procession or transfer of personal data of EU citizens. This will affect companies and website owner worldwide, if they interact with EU citizens.

To get some details about the Regulation, look here: [https://www.eugdpr.org/](https://www.eugdpr.org/)

I will try to summarize the relevant points that need to be applied to make a website gdpr-compliant. I am not a lawyer, this is no legal counseling. The whote intent of this page is to provide orientation for the creation of a GDPR-compliance Package / Documentation for the use with concrete5.
Outline

The whole process of being compliant to GDPR can be divided in three separate categories (please educate me if I'm wrong):

1. Behavior as a website owner

2. Documentation

3. Technical bits

The goal of this page is the creation of a working solution to all three:

1. A guidance of behavior for website owners

2. A list of documentation that you must provide as a website owner

3. A package / code adaptation for concrete5 that fulfills the technical bits

##1. Behavior as a website owner

    Data reduction. Only collect the data you actually need.
    Consent. You need to collect the consent of whoever you are collecting the data from. A checkbox with a link to your privacy statement would serve this purpose. Opt-In is required.
    Secure Data Transport. A SSL/TLS certificate seems unavoidable to mitigate MIM attacks. Either obtain a commercial certificate or read up about the Let's Encrypt Initiative to get a high-quality, free certificate.
    Breach reports. GDPR requires that you inform your Data Protection Officer within 72hrs after you know about a data breach or privacy intrusion to your system.

##2. Documentation

    Data Protection Officer. You need to assign a Data protection officer who has knowledge about privacy laws as well as IT security.  Here are some guidelines of how to appoint someone: https://en.wikipedia.org/wiki/General_Data_Protection_Regulation#cite_note-18
    You need to clarify in your privacy statement WHAT data you collect and what the PURPOSE of the collection of this data ist. You need to explain with whom the data can be shared and how you treat it.

##3. Technical bits

Some technical challenges come with GDPR. I will try to outline the technical bits and write up some ideas on how these could be achieved. Please contribute with technical knowledge!

    Pseudonymisation. GDPR requires that even in the case of a data breach, the personal data of the website customers (Name, Address, Birthdata) should not be usable to the intruder. This requires encryption of the data.
    An example of pseudonymisation is encryption, which renders the original data unintelligible and the process cannot be reversed without access to the correct decryption key. The GDPR requires that this additional information (such as the decryption key) be kept separately from the pseudonymised data. Pseudonymisation is recommended to reduce the risks to the concerned data subjects and also help controllers and processors to meet their data-protection obligations (Recital 28). Although the GDPR encourages the use of pseudonymisation to "reduce risks to the data subjects," (Recital 28) pseudonymised data is still considered personal data (Recital 26) and therefore remains covered by the GDPR.
    https://en.wikipedia.org/wiki/General_Data_Protection_Regulation#Pseudonymisation
    Right to acces. You need to enable the customer access to their personal data. This means: a user profile is mandatory and needs to be accessible to the user. But the user shall have the possibility to keep their profile private.
    Right to erasure. The user must be able to delete the profile. I assume that deleting the user profile includes removing the data from the database.
    Data portability. There must be a possibility to export the personal data so that it can be imported to another system.

##Solutions

I will try to outline which technical solutions would help comply to GDPR:
###User profile

    Possibility to delete or request deletion through the user profile
    Possibility to export the user data through the user profile (CSV?)
    Possibility to swith a public profile to "private" through permissions

 
###Security Check

Built-in Checking Tool that will look for SSL or proper configuration of permissions