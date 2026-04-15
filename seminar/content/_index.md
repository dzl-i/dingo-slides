+++
title = "Thesis B Seminar Presentation"
outputs = ["Reveal"]
[logo]
src = "dingo-logo.png"
diag = "1%"
[reveal_hugo]
+++

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

---

### so, why is it important?

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

---

### clinicians

- needs to know full context before they can suggest treatment
- can ensure monitoring is consistent and coordinated

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

---

### problem statement

Existing cancer survivorship passports are primarily clinician-facing, leaving patients without an accessible platform to view their health information, track medications, and manage long-term follow-up care.

---

### solution

a mobile version of the Cancer Survivorship Passport

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
FHIR is the newer HL7 standard designed for modern web and mobile use. It represents clinical data as modular resources that can be exchanged using REST APIs and JSON or XML.
{{% /note %}}

---

### Data Flow

{{<figure src="/data-flow.png" height="550px">}}

---

### cloud architecture

{{<figure src="/architecture-diagram.png" height="550px">}}

---

### cloud architecture

Microsoft Azure (Cloud Services)
- Application Layer
- Authentication Layer
- Database Layer

---

### cloud architecture

DevOps
- Infrastructure as Code
- CI/CD
- Monitoring

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

---

and most importantly,

### **hi-fi prototyping in Figma**

---

from Lo-Fi designs in Thesis A

{{<figure src="/lofi-design.png">}}

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

- using React Native
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

intuitive

modern and minimalist

colourful and colour-coded
{{% /note %}}

---

### navigation

{{<figure src="/app-navigation.png">}}

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

## Reflection

> future work and project direction

{{% /section %}}

---

{{% section %}}

## Summary

{{% /section %}}

---

{{% section %}}

## questions?

{{% /section %}}
