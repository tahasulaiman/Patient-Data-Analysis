# Patient Data Analysis Project

## Project Overview

This project focuses on cleaning, exploring, and analyzing a patient dataset using Python.

The dataset initially contained 632 patient records and 11 columns. The project covers data quality checks, data cleaning, exploratory data analysis (EDA), and visualization to identify patterns and summarize the characteristics of the patient population.

## Objectives

- Understand the structure and quality of the dataset
- Identify missing values and duplicate records
- Clean inconsistent insurance provider names
- Standardize gender values
- Clean and validate date fields
- Standardize state and city information
- Clean email addresses and phone numbers
- Standardize ZIP codes and patient names
- Explore patient demographics and insurance information
- Analyze registration trends
- Create visualizations to communicate findings
- Extract meaningful insights from the cleaned dataset

## Dataset

The original dataset, `patients_easy.csv`, contained:

- 632 patient records
- 11 columns

After removing 24 exact duplicate rows, the dataset contained 608 records.

The dataset includes patient-related information such as:

- Patient ID
- Full Name
- Date of Birth
- Gender
- Email
- Phone
- Address information
- Insurance Provider
- Registration Date

## Data Cleaning

Several data quality issues were identified and handled during the project.

### Insurance Provider

- Missing insurance provider values were labeled as `Not Provided`.
- 27 different insurance spellings were standardized into 8 categories.
- Similar names such as `UnitedHealth`, `United Health`, and `UHC` were combined.

### Duplicate Records

- 24 exact duplicate rows were identified and removed.
- Some patient IDs were shared by two different people. These records were kept because they represented different patients.

### Gender

Different representations such as `M`, `m`, `Male`, `F`, and `Female` were standardized into:

- Male
- Female

### Dates

- Date columns were converted to proper datetime values.
- Future birth dates caused by two-digit years were corrected by moving them back 100 years.
- Birth dates occurring after registration dates were considered invalid and set to missing.

### State and City

- State names were standardized to two-letter state codes.
- City names were cleaned and consistently capitalized.

### Email

Email data was cleaned by fixing issues such as:

- `,com`
- `gmial`
- ` at `
- Titles appearing at the beginning of email values

### Phone

- `unknown` values were converted to missing values.
- Non-numeric characters were removed.
- Phone numbers were standardized to 10 digits where possible.

### ZIP Code

- ZIP codes were standardized to 5 digits.
- Extra digits were removed.
- Leading zeros were restored where necessary.

### Full Name

- Titles such as `Mr.`, `Mrs.`, `Ms.`, and `Dr.` were removed.
- Suffixes such as `MD`, `DDS`, `PhD`, `Jr.`, `Sr.`, `II`, `III`, and `IV` were removed.
- Names were standardized using consistent capitalization.

## Exploratory Data Analysis

After cleaning the dataset, exploratory analysis was performed to understand:

- Patient age distribution
- Insurance provider distribution
- Gender distribution
- Monthly registration trends
- Patient distribution by state
- Age differences across insurance providers
- Gender distribution across insurance providers
- Patient distribution by age group

## Visualizations

The project includes the following visualizations:

1. Patient Age Distribution
2. Patients by Insurance Provider
3. Patients by Gender
4. Registrations per Month
5. Top 10 States by Patients
6. Age by Insurance Provider
7. Gender by Insurance Provider
8. Patients by Age Group

## Key Findings

- Patients are mostly middle-aged, with an average age of approximately 45 and a median age of 46.
- Patient ages range from 3 to 96.
- The largest age group is 36–50.
- Approximately 80% of patients with a known age are between 19 and 65.
- Medicaid, Aetna, and UnitedHealth are among the largest insurance groups, with approximately 92 patients each.
- Self Pay is the smallest insurance group, with approximately 34 patients.
- Approximately 10% of patients have no insurance information recorded.
- The dataset contains slightly more male patients than female patients: 326 males and 282 females.
- Monthly registrations remain relatively steady, averaging approximately 14 patients per month.
- Patients are distributed across states fairly evenly, with no single state representing more than approximately 3% of the dataset.
- Age and gender distributions do not differ substantially between insurance providers.

## Limitations and Assumptions

- Dates such as `09/07/1979` were interpreted as month-first dates.
- Two-digit birth years that resulted in future dates were moved back 100 years.
- ZIP codes with four digits were assumed to have lost a leading zero.
- Missing insurance information was labeled `Not Provided` because it is unknown whether those patients were actually uninsured.
- Some unrealistic age patterns suggest that the dataset may be synthetic.
- The findings describe this dataset only and should not be interpreted as representing a real-world patient population.
- Some missing values remain because the original information was unavailable.

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Project Structure

```text
patient-data-analysis/
│
├── data/
│   ├── patients_easy.csv
│   └── patients_clean.csv
│
├── Patient_Data_Analysis.ipynb
├── README.md
└── requirements.txt
