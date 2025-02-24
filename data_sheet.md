# Datasheet


## Motivation

- For what purpose was the dataset created?
    - The Eclipse and Mozilla Defect Tracking Dataset was created to support software engineering research, particularly in bug prediction, defect analysis, and software quality assessment. It enables the study of defect trends, developer activities, and software reliability.
- Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Who funded the creation of the dataset?
    - The dataset was compiled and released as part of the Mining Software Repositories (MSR) 2013 Challenge. It was curated by researchers from the University of Antwerp and Ghent University, Belgium, in collaboration with the MSR community.
        - Funding sources for the dataset are not explicitly documented, but academic and institutional research groups contributed to its development.
 
## Composition

- What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)?
    - The dataset consists of bug reports from two large open-source projects:
        - Eclipse (Integrated Development Environment).
        - Mozilla (Web browser and application suite).
    - Each instance represents a reported software defect (bug), including details such as:
        - Bug ID, Status, Severity, Priority, Resolution.
        - Developer and Tester Comments.
        - Timestamps (reported, modified, resolved).
        - Textual Descriptions of Defects.
- How many instances of each type are there? 
    - Total Reports: Over 200,000 defect reports.
    - Eclipse Defects: Approximately 130,000 bug reports.
    - Mozilla Defects: Approximately 70,000 bug reports.
- Is there any missing data?
    - Yes, some defect reports may have missing severity, resolution, or timestamps due to incomplete tracking in the original issue management systems.
    - Some textual descriptions may be truncated or absent in a few reports.
- Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by    doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)?
    - No. The dataset is derived from publicly available issue tracking systems of open-source projects.
    - It does not contain personally identifiable information (PII), proprietary code, or confidential communications.

## Collection process

- How was the data acquired? 
    - The dataset was collected from Bugzilla issue tracking systems used by Eclipse and Mozilla projects.
    - The data was retrieved using automated scripts and APIs to extract structured defect information.
- If the data is a sample of a larger subset, what was the sampling strategy? 
    - The dataset includes all reported defects in the selected projects rather than a sample.
    - No artificial sampling was applied — data represents the entire defect history of both projects.
- Over what time frame was the data collected?
    - The dataset includes bug reports spanning from 2001 to 2013, covering over a decade of software evolution.

## Preprocessing/cleaning/labelling

- Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remaining questions in this section. 
    - Yes, several preprocessing steps were applied:
        - Structured Data Cleaning:
            - Standardized column names and labels (e.g., bug_status, priority, severity).
            - Encoded categorical features (priority, status, severity).
        - Text Preprocessing:
            - Removed HTML tags and special characters from descriptions.
            - Applied TF-IDF and NLP embeddings for textual defect reports.
        - Timestamp Processing:
            - Converted timestamps to a unified format.
            - Computed new features such as resolution_time_days, time_since_reported_days.
- Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? 
    - Yes, the original raw dataset remains available via the MSR 2013 repository.
    - The preprocessed dataset includes additional feature-engineered attributes for machine learning tasks
 
## Uses

- What other tasks could the dataset be used for? 
    - In addition to defect severity classification and anomaly detection, the dataset can be applied to:
        - Defect Prediction: Predict which new bug reports are likely to be severe or high-priority.
        - Software Maintenance Planning: Analyze historical defect trends to improve software release planning.
        - Developer Performance Metrics: Evaluate issue resolution times and developer response patterns.
        - Natural Language Processing (NLP) Applications: Extract insights from textual defect reports to automate defect triaging.
- Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other risks or harms (e.g., legal risks, financial harms)? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? 
    - Bias in Defect Severity: The way defects were labeled (low, medium, high) depends on project maintainers’ decisions. The dataset may not generalise to all software projects.
    - Incomplete Historical Data: Some old defects may be missing updates, leading to inconsistent timestamps.
    - Misinterpretation Risks: Using textual descriptions alone without developer feedback may lead to incorrect defect severity predictions.
- Are there tasks for which the dataset should not be used? If so, please provide a description.
    - Real-time Bug Assignment in Critical Systems: The dataset does not account for real-time defect resolution strategies used in modern DevOps workflows.
    - Legal or Regulatory Decision-Making: Since it is open-source software data, it should not be used for legal risk analysis in commercial software.

## Distribution

- How has the dataset already been distributed? 
    - The dataset is publicly available through the Mining Software Repositories (MSR) 2013 dataset repository.
    - Hosted on GitHub: [GitHub - ansymo/msr2013-bug_dataset](https://github.com/ansymo/msr2013-bug_dataset).
- Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?  
    - The dataset is released under an open-access license for research purposes.
    - Bugzilla issue tracking data is publicly available and not subject to any proprietary restrictions.
    - Users should refer to individual project policies (Eclipse, Mozilla) regarding attribution when citing the dataset.

## Maintenance

- Who maintains the dataset?
    - The dataset was originally maintained by academic researchers from the University of Antwerp and Ghent University.
    - The MSR community occasionally updates or expands related datasets.
    - The Bugzilla repositories of Eclipse and Mozilla continue to collect live defect reports, but these are not automatically integrated into this dataset.
