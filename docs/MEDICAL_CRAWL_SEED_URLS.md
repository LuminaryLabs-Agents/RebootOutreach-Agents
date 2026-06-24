# Medical Crawl Seed URLs

This file contains the first approved seed URLs for Nexus Crawler medical/XR trigger detection.

Use these URLs for controlled crawling, parser testing, source classification, and signal detection validation.

## First crawl batch

```text
https://www.fda.gov/medical-devices/digital-health-center-excellence/augmented-reality-and-virtual-reality-medical-devices
https://www.fda.gov/medical-devices/digital-health-center-excellence/augmented-reality-and-virtual-reality-medical-devices-questions-consider

https://www.acgme.org/programs-and-institutions/programs/common-program-requirements/
https://www.acgme.org/newsroom/e-communication/2026/april-6-2026/
https://www.acgme.org/newsroom/e-communication/2025/january-13-2025/

https://grants.nih.gov/funding/explore-nih-opportunities
https://grants.nih.gov/grants/guide/pa-files/PAR-25-296.html
https://grants.nih.gov/grants/guide/pa-files/PAR-24-272.html
https://grants.nih.gov/grants/guide/rfa-files/rfa-hs-10-018.html
https://grants.nih.gov/grants/guide/rfa-files/RFA-HS-06-030.html

https://clinicaltrials.gov/study/NCT04404010
https://clinicaltrials.gov/study/NCT05982288
https://clinicaltrials.gov/study/NCT07515092
https://clinicaltrials.gov/study/NCT06917755
https://clinicaltrials.gov/study/NCT04268914
https://clinicaltrials.gov/study/NCT04700384

https://pubmed.ncbi.nlm.nih.gov/39688774
https://pmc.ncbi.nlm.nih.gov/articles/PMC9933861/

https://jobs.mayoclinic.org/employment/united-states-education-jobs/33647/8336944/6252001/2
https://jobs.mayoclinic.org/job/jacksonville/emergency-medicine-physician/33647/93160303184
https://jobs.mayoclinic.org/job/mankato/nurse-practitioner-or-physician-assistant-emergency-medicine-swmn/33647/95029505872
https://jobs.mayoclinic.org/nurseresidencyprograms
https://jobs.mayoclinic.org/Surgicalservices

https://www.massgeneralbrigham.org/en/education-and-training/graduate-medical-education/residencies-and-fellowships/brigham-and-womens-hospital
https://www.massgeneralbrigham.org/en/about/advancing-care/health-equity-community-health/health-care-career-pathways
https://www.massgeneralbrigham.org/en/about/newsroom/press-releases/mayor-boston-public-schools-bloomberg-edward-m-kennedy-academy
https://www.massgeneralbrigham.org/en/research-and-innovation/centers-and-programs/health-design-lab
https://salem.massgeneralbrigham.org/residency/program_directors_message
```

## Source categories

### FDA

Expected use:

- Regulatory source
- Medical AR/VR device context
- Compliance and approved-device language

Expected signal types:

- regulatory_update
- healthcare_xr_market_context

### ACGME

Expected use:

- Residency requirements
- Accreditation language
- Simulation requirement context

Expected signal types:

- accreditation_update
- simulation_requirement

### NIH grants

Expected use:

- Funding opportunities
- Healthcare innovation grants
- Research support language

Expected signal types:

- healthcare_innovation_grant
- funding_opportunity

### ClinicalTrials

Expected use:

- Public clinical study pages
- VR/AR healthcare intervention evidence
- Recruiting or completed clinical studies

Expected signal types:

- clinical_evidence
- study_activity

### PubMed / PMC

Expected use:

- Clinical evidence
- Research support
- Medical training outcomes

Expected signal types:

- clinical_evidence
- market_context

### Mayo Clinic jobs

Expected use:

- Hiring signal testing
- Medical education roles
- Residency and surgical services pages

Expected signal types:

- hiring_signal
- medical_training_context

### Mass General Brigham

Expected use:

- Medical education
- Innovation lab context
- Residency programs
- Press releases

Expected signal types:

- medical_education_signal
- innovation_lab_signal
- press_release_signal

## Crawl priority

Start with this smaller first batch:

```text
https://www.fda.gov/medical-devices/digital-health-center-excellence/augmented-reality-and-virtual-reality-medical-devices
https://www.acgme.org/programs-and-institutions/programs/common-program-requirements/
https://grants.nih.gov/funding/explore-nih-opportunities
https://clinicaltrials.gov/study/NCT04404010
https://jobs.mayoclinic.org/nurseresidencyprograms
https://www.massgeneralbrigham.org/en/research-and-innovation/centers-and-programs/health-design-lab
```

## Notes

- These URLs are seed targets.
- Some pages may change or move.
- If a URL fails, record it in crawler logs instead of removing it immediately.
- Future agents should expand this list with simulation center pages, hospital innovation labs, and university medical education job boards.
