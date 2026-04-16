+++
title = "Thesis B Seminar Presentation"
outputs = ["Reveal"]
[logo]
src = "dingo-logo.png"
diag = "1%"
[reveal_hugo]
+++

{{% section %}}

## Mobile Application for Cancer Survivorship Passport

*Thesis B Seminar Presentation*

<br>

Christian Denzel Iskandar (z5346200)

Supervisor: Dr. Peter Brown

{{% note %}}
Don't forget to thank the audience.
custom_theme = "reveal-hugo/themes/robot-lung.css"
custom_theme = "reveal-hugo/themes/sunblind.css"
{{% /note %}}

---

### before we start

Please fill in this form

https://forms.cloud.microsoft/r/jajWsH6PUD

{{% /section %}}

---

{{% section %}}

## Statement of Contribution

---

### Acknowledgements

<!-- <ul>
  <li class="fragment fade-up">One</li>
  <li class="fragment fade-up">Two</li>
  <li class="fragment fade-up">Three</li>
</ul> -->

- Dr. Peter Brown (Supervisor)
- Jayden Lang (Previous contributor to CSP)
- Samuel Zheng (Previous contributor to mobile development)

---

### Use of AI

Generate health recommendations

{{<figure src="/ai-recommendations.png" height="400px">}}

---

### Use of AI

Generate sample data

{{<figure src="/ai-sample-data.png" height="160px">}}
{{<figure src="/ai-sample-data-sc.png" height="200px">}}

{{% /section %}}

---

{{% section %}}

## Project Context and Background

> Cancer Survivorship Passport (CSP)

---

### Cancer Survivorship Care

ongoing health management and support provided to individuals from the time of a cancer diagnosis through the rest of their lives (National Cancer Institute, 2024)

{{% fragment %}}care does not end when treatment is complete{{% /fragment %}}

---

### Cancer Survivorship Passport

a personalised summary document that contains a survivor’s past cancer diagnosis and treatments received

{{% note %}}
treatments received such as chemotherapy doses, radiation fields, surgeries, and tailored recommendations for long-term follow-up care
{{% /note %}}


---

<!-- ### Cancer Survivorship Passport -->

{{<figure src="/csp-example.png" height="550px">}}

example: Survivorship Passport (SurPass) from EU

{{% note %}}
contains patient's personal information, diagnosis, treatments, and other information
{{% /note %}}

---

### so, why is it important?

{{% note %}}
why is CSP important
{{% /note %}}

---

### patients

- at risk of recurrence or new primary cancers 
- also at risk of long-term and late effects of treatment
- receive care from multiple oncologists/specialists

> patients need continuous monitoring

---

what if they switch to another oncologist? 

{{% fragment %}}and if they are in a different hospital?{{% /fragment %}}

{{% fragment %}}in a different country?{{% /fragment %}}

{{% note %}}
before i continue, here are some questions to think about

switch to another oncologist - its fine, patient records can be easily transferred to new oncologist

in a different hospital - medical records no longer easily accessible, doctors do not have context, but probably still quite possible to get medical records

in a different country - very hard to get medical records
{{% /note %}}

---

### clinicians

- needs to know full context before they can suggest or proceed with treatment
- want to ensure monitoring is consistent and coordinated

---

### beyond that

- help patients transition from active treatment into life afterwards

{{% note %}}
promote healthy behaviours, monitor for complications or recurrence, and improve long-term outcomes
{{% /note %}}

---

### recap

> problems

- need for long-term survivorship care
- need for monitoring patients
  - and patients to monitor their own needs
- coordination between clinicians
- a standard source-of-truth for patient's care

---

Cancer Survivorship Passport is the solution to these problems...

{{% fragment %}}but, CSP is not too useful if only clinicians can access them and stored in a single hospital{{% /fragment %}}

{{% note %}}
now, we have established that CSP is the solution to these problems, and hence why they are important

but ...
{{% /note %}}

---

### problem statement

Existing cancer survivorship passports are primarily clinician-facing, leaving patients without an accessible platform to view their health information, track medications, and manage long-term follow-up care.

---

### solution

a mobile version of the Cancer Survivorship Passport

{{% note %}}
which can be easily accessed by patients, from anywhere
{{% /note %}}

---

### features

- view detailed data about their care
- view appointments and medication schedules
- notifications for reminder
- view and export health passport

{{% fragment %}}many more...{{% /fragment %}}

{{% /section %}}

---

{{% section %}}

## Technical Background

> a deeper dive on the technical aspect

---

### Standards and Laws

- Health Level Seven (HL7)
  - Fast Healthcare Interoperability Resources (FHIR)
- Australian Privacy Act

{{% note %}}
medical applications need to adhere to standards and laws

FHIR is the newer HL7 standard designed for modern web and mobile use. It represents clinical data as modular resources that can be exchanged using REST APIs and JSON or XML.

privacy act to protect user's identity and to keep their information secure
{{% /note %}}

---

### Data Flow

{{<figure src="/data-flow.png" height="550px">}}

{{% note %}}
this diagram shows how data moves around or gets transmitted
- most important - survivors can read data from the database, which can be shared with hospitals and other clinicians
- data can be input manually but also linked with electronic health records
{{% /note %}}

---

### cloud architecture

{{<figure src="/architecture-diagram.png" height="550px">}}

{{% note %}}
give background - say how cloud services and infrastructure is also part of thesis
{{% /note %}}

---

### cloud architecture

Microsoft Azure (Cloud Services)
- Application Layer
- Authentication Layer
- Database Layer

{{% note %}}
application layer includes App Service

authentication layer includes Entra ID and Auth.js

Database layer includes FHIR service, storage account, sql database
{{% /note %}}

---

### cloud architecture

DevOps
- Infrastructure as Code
- CI/CD
- Monitoring

{{% note %}}
IaC using Terraform

CI/CD configured on GitHub

monitoring using application insights from azure monitor
{{% /note %}}

{{% /section %}}

---

{{% section %}}

## Project Progress

---

in the early weeks...

- learning React Native
- project set-up
- codebase familiarisation + migration of code
- looked into deployment for Web CSP

{{% note %}}
project set-up took a long time due to config issues
{{% /note %}}

---

and most importantly,

### **hi-fi prototyping in Figma**

---

from Lo-Fi designs in Thesis A

{{<figure src="/lofi-design.png">}}

{{% note %}}
for overall structure and layout, more important for navigation
{{% /note %}}

---

to Hi-Fi designs in Thesis B

{{<figure src="/hifi-design.png">}}

---

all of the screens in Hi-Fi

{{<figure src="/hifi-design-all.png">}}

---

in the later weeks...

### mobile app development

---

### mobile app development

- using React Native + Expo
- integrate with FHIR standard for data retrieval

{{% /section %}}

---

# DEMO

---

{{% section %}}

## Technical Decisions

---

### user interface

> recap: survivorship care does not end upon treatment completion

{{% fragment %}}so, design must account for all ages{{% /fragment %}}

---

{{<figure src="/app-sample.png">}}

{{% note %}}
familiar - follows patterns from multiple apps

intuitive - uses labels everywhere to ensure understanding

modern and minimalist

colourful and colour-coded to increase familiarisation
{{% /note %}}

---

### navigation

{{<figure src="/app-navigation.png">}}

{{% note %}}
bottom tabs are inspired by outlook

sidebar also inpired by outlook
{{% /note %}}

---

### information displayed

{{<figure src="/app-information.png">}}

{{% note %}}
dilemma of how much information to display to patients

too much? patients may get paranoid of things that are actually normal/misunderstanding

too little? patients do not know whats happening

result - show everything. in cases of emergency where information is needed, its better to have all than to have some. they need to know whats happening, without having to generate the health passport every time
{{% /note %}}

---

### recommendations

{{<figure src="/app-recommendations.png">}}

{{% note %}}
provides additional information about the specific menu

guides and information so that patients dont feel lost/confused

warnings to make patients aware

colour coded
{{% /note %}}

---

so... there were some differences between the Hi-Fi prototype and the actual app

{{% note %}}
continuous improvements always made

removed unnecessary information like recent activities, indicators in home page, full list of CSP fields in health passport page

made the UI more clean, reducing clutters

fixed how some fields were displayed, since data in Figma are quite short, while real data are longer and more complex than sample data

added some missing fields - some that are computed directly in the app
{{% /note %}}

{{% /section %}}

---

{{% section %}}

## Retrospective

> reflection, future work, and project direction

---

### challenges and response

- ui/ux design
- learning react native and native APIs
  - integrating more features with native APIs (push notifications, calendar)
- exploring cloud services
- time management - could have done more work
  - will dedicate more focus times next term

{{% fragment %}}cloud services are still a **huge** challenge{{% /fragment %}}

{{% note %}}
coming up with a design that is applicable for all ages

native API like the share/export tool in Health Passport
{{% /note %}}

---

### thesis b timeline

{{<figure src="/thesis-b-timeline.png" height="575px">}}

{{% note %}}
initial time spent on project set up, caused delays

how the project evolved relative to the original plan - overall a good progress, finished development for more screens (mention) but was not able to complete deployment and infra setup

why unit testing was not done - app is read-only, testing can be done visually without having to do unit testing

feedback implementation always done, feedback from Peter

why deployment was not done - for web, need to make sure local version is compatible with the mobile. otherwise, it will be pointless to have a deployment done for a broken app. also need to meet with the infra team
{{% /note %}}

---

### thesis c timeline

{{<figure src="/thesis-c-timeline.png" height="575px">}}

{{% note %}}
in thesis b, more focus on mobile development

in thesis c, more focus on deployment and infrastructure

usability testing will be conducted throughout the term, to improve UI and UX

talk a bit more about the dev
- finish integrating appointments and medications page with data from FHIR
- new pages for care team, symptoms, test results
- notifications that actually trigger push notifications
- stretch goals - admin portal for clinicians to add in or edit therapies and medications
  - now it is hardcoded in the web app (clinician facing)
{{% /note %}}

---

### upskilling and resources needed

- need to read up more on cloud services
  - methods to implement them
- how to use more native API
- microsoft azure environment for infrastructure

{{% /section %}}

---

{{% section %}}

## Summary

> key take-home message

{{% note %}}
mobile app for CSP will be beneficial for both patients and clinicians, as patients can easily keep track of their well-being and care, and clinicians can easily retrieve patient history which results in faster actions for patients
{{% /note %}}

{{% /section %}}

---

{{% section %}}

## questions?

{{% /section %}}

---

## Thank you!

Please fill in this form

https://forms.cloud.microsoft/r/jajWsH6PUD

<br>

Christian Denzel Iskandar

z5346200
