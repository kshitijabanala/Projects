
## Table of Contents  
1. [Project Overview](#project-overview)  
2. [Data Collection](#data-collection)  
3. [Data Cleaning](#data-cleaning)  
4. [Data Integration](#data-integration)  
5. [Data Analysis](#data-analysis)  
6. [Mediated Schema](#mediated-schema)
7. [Conclusion](#conclusion)
8. [Sources](#sources)  

---

## 1. Project Overview  

<p align="center">
  <img src="https://github.com/user-attachments/assets/13d4fe2a-7e94-4fec-a33e-87dbe88db644" alt="image" width="500">
</p>


This project integrates study abroad program data from **Penn State University (PSU)** and **Ohio State University (OSU)** into a unified and queryable schema. By web scraping public program tables, cleaning inconsistencies, and structuring the data into an SQLite database, we developed a comprehensive database for efficient querying and analysis.  

Key queries provided insights into:  
- Program distributions by **region**, **college**, and **location**.  
- Comparisons between PSU and OSU's offerings.  

This work highlights the power of **data integration** and the importance of **standardizing schema** for multi-source data analysis.  

---

## 2. Data Collection  
### Web Scraping  
- **Source**: Publicly accessible websites of PSU and OSU.  
- **Method**: Python's Beautiful Soup library was used to extract program details such as:  
  - Program Name  
  - City  
  - Country  
  - Region  

- Data was parsed into structured formats and inspected using Pandas.  

---

## 3. Data Cleaning  
Raw datasets contained several inconsistencies that required cleaning:  

- **Multi-City/Region Entries**: Aggregated into generic labels like "multiple cities" or "multiple regions."  
- **Multi-Country Entries**: Split into individual rows to maintain clean mappings.  
- **Formatting Issues**: Leading spaces, commas, and colons were removed.  

A "College" column was added to identify the source of each program (**PSU** or **OSU**).  

---

## 4. Data Integration  
### Database Creation  
- **SQLite Database**: Named `study_abroad_psu_osu`.  
- Merged datasets from PSU and OSU into a single, unified table.  

### Validation  
SQL queries validated data integrity and ensured the schema was ready for analysis.  
For instance, queries checked:  
- Programs offered in specific cities or regions.  

---

## 5. Data Analysis  
### Key Queries and Insights  
1. **Programs in London**:  
   - 6 programs found: 4 from PSU and 2 from OSU.  
2. **Programs in Asia**:  
   - Offered in countries like Cambodia, Singapore, Thailand, Japan, and South Korea.  
3. **Programs in Japan**:  
   - Found in Tokyo, Mito, Sendai, and multi-city programs.  
4. **Program Distribution by Region**:  
   - **Europe**: 300 programs  
   - **Asia**: 64 programs  
   - **Latin America**: 34 programs  
5. **Distribution by College**:  
   - OSU has more programs in the **United Kingdom**.  
   - PSU focuses on **Australia** and **Argentina**.  

---

## 6. Mediated Schema  
### Schema Design  
The schema unified attributes from both datasets into the following structure:  
- **Program Name**  
- **City**  
- **Country**  
- **Region**  
- **College**  

<img width="600" alt="image" src="https://github.com/user-attachments/assets/4ce77d3b-9d6b-4f06-ae23-4395c577fc55" />

Multi-city and multi-country entries were normalized to ensure clean mappings. The schema enabled streamlined analysis and improved query flexibility.  

### Examples  
<img width="600" alt="image" src="https://github.com/user-attachments/assets/3dc9771e-960b-48a9-a006-4c48ecc3c8e0" />

Here we filtered the database to retrieve all programs located in Asia. The results demonstrate the variety of programs offered in countries such as Cambodia, Singapore, Thailand, Japan, and South Korea. This query emphasizes the diverse opportunities available for students interested in studying in this region.

<img width="600" alt="image" src="https://github.com/user-attachments/assets/c1526041-5168-4a88-beea-6bb09ec4014e" />

Focusing further, we analyzed programs specifically offered in Japan. The database revealed entries for cities like Tokyo, Mito, and Sendai, as well as multi-city programs. This query highlights the range of study abroad opportunities available in Japan, catering to different academic and cultural interests.

<img width="450" alt="image" src="https://github.com/user-attachments/assets/f3156d3e-683f-431c-899f-e8201a4862c5" />

Here we examined the distribution of programs by college and country. The analysis shows that OSU has a significant number of programs in the United Kingdom, while PSU offers several in Australia and Argentina. This comparative view highlights the unique regional focuses of the two universities.

 

## Conclusion

This project demonstrates the feasibility and value of creating a unified database for study abroad programs. By integrating data from PSU and OSU, we have streamlined the research process for students and provided universities with a powerful analytical tool. The system simplifies the discovery of study abroad opportunities, empowering students to make informed decisions and promoting international education.
Beyond its immediate benefits, this project lays the foundation for a more interconnected and efficient approach to managing study abroad programs. As global learning continues to grow in importance within higher education, tools like this database will play a critical role in fostering engagement and enhancing the reach of international programs. Ultimately, this database not only promotes accessibility and standardization but also encourages greater participation in global learning experiences, enriching the academic and cultural journeys of students worldwide
![image](https://github.com/user-attachments/assets/9b8086b7-53a6-4b12-9883-18b3e27707f2)

