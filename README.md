<p align="center">
  <img width="300" height="200" src="https://github.com/a-pradono/extract_scanned_pdf/blob/main/Images/header.jpg">
</p>
<p align="center">
Photo by <a href="https://unsplash.com/@anniespratt?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Annie Spratt</a> on <a href="https://unsplash.com/s/photos/old-files?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
</p>

## Table of Contents

- [I. Introduction](#i-introduction)
- [II. Data and Methodology](#ii-data-and-methodology)
- [III. Results](#iii-results)
- [IV. Conclusions](#iv-conclusions)
- [Reference](#reference)

## I. Introduction
The process of extracting information can be a challenging task especially from old file report that hasn't been processed with the computer at that time. Take an example from the oil and gas industry since this industry has been around in business since the early 1900s. I remember when I was doing an internship as a geologist in one of the oil and gas companies couple of years ago, I need to go to the company file room to find a report, scan it, and store it one by one during my first week. Therefore, I bet there are still a lot of old data that need to be stored in the database. The objective of this project was to detect a table and extract the text from scanned pdf using optical character recognition (OCR).

## II. Data and Methodology
This project is made off using the [Alaska Division of Geological & Geophysical Survey](https://dggs.alaska.gov/) geochemical publications data. One page has specifically been assigned from multiple pages of the report to perform OCR in the target table text. This data is reliable since it was retrieved from the official government website.

<p align="center">
  <img width="300" height="200" src="https://github.com/a-pradono/extract_scanned_pdf/blob/main/Images/workflow.jpg">
</p>

The workflow above demonstrates how I achieved the objective of this project. First, select scanned pdf and specify the target page that wants to be retrieved. Second, convert the target page of the pdf file with the table to the image file. Third, perform the OCR to detect and extract table in the file. Fourth, store the OCR results into a text document. Fifth, convert the text document to a csv file to clean the results from OCR. Lastly, visualize the data frame into a series of subplots.

## III. Results
In the first figure below, this is the data frame that was obtained from the target page pdf file which has already been converted to the image file. After converting the pdf file to an image file, the next step is to highlight the regions of the images where the table is located in order to extract the information.

<p align="center">
  <img width="200" height="300" src="https://github.com/a-pradono/extract_scanned_pdf/blob/main/Images/plot01.jpg">
</p>

Furthermore, once the regions are already marked with respective coordinates, the crop of the original image for the particular region will be passed into OCR analysis. The results after OCR is shown in the figure below as a text file.

<p align="center">
  <img width="300" height="200" src="https://github.com/a-pradono/extract_scanned_pdf/blob/main/Images/plot02.JPG">
</p>

By looking at the OCR results, this task is still not successfully accomplished yet since detecting the table is the easy part but extracting the data from the structure is the hard part. The summary of the results is shown in the figure below and the most crucial part is if OCR misinterprets the number values in this data frame. 

<p align="center">
  <img width="300" height="200" src="https://github.com/a-pradono/extract_scanned_pdf/blob/main/Images/plot03.jpg">
</p>

I have tried to clean and edit the csv file data using copy to excel clipboard since it only has one page and is easier, at least for me. It was hard for me to perform regular expressions, especially in the numbers part. All of these numbers consist of two digits and some of the numbers didn't separate well. The final data frame is shown in the figure below.

<p align="center">
  <img width="300" height="200" src="https://github.com/a-pradono/extract_scanned_pdf/blob/main/Images/plot04.jpg">
</p>

Moreover, a geochemical log has been constructed and visualized from the Inigok-1 well. This figure below is useful for the geologist to identify the presence of source rock, quality, and maturity based on total organic carbon (TOC) and Rock-Eval pyrolysis data. The parameters most frequently reported are TOC, S1, S2, S3, and Tmax, together with a number of derived parameters like HI, OI, and PI. Here is the further explanation for [TOC](https://wiki.aapg.org/Source_rock_richness) and [Rock-Eval pyrolysis](https://wiki.aapg.org/Rock-Eval_pyrolysis) based on AAPG Wiki.

<p align="center">
  <img width="300" height="400" src="https://github.com/a-pradono/extract_scanned_pdf/blob/main/Images/plot05.jpg">
</p>

## IV. Conclusions
The main objective of this project was to extract table data from scanned pdf using OCR. Although the OCR was able to extract tabular data to a good extent, there are also some limitations. The conclusions made from this project are:
  * Double-check was needed after performing the OCR. The most crucial part of this project is when extracting the number values.
  * Text detection was weak when using OCR on the segmented table region. 
  * It was unable to distinguish between cells containing row or column headers and data.

## Reference
DGSI, Inc., 1999, Total organic carbon (TOC), rock-eval, vitrinite reflectance, and gas chromatography of the following well materials: Malguk #1, Ikpikpuk Test Well #1, Inigok T. W. #1, North Inigok T. W. #1, North Kalikpik T. W. #1, East Teshekpuk T. W. #1, W. T. Foran T. W. #1, and Fish Creek T. W. #1: Alaska Division of Geological & Geophysical Surveys Geologic Materials Center Data Report 286, 47 p. https://doi.org/10.14509/19134
