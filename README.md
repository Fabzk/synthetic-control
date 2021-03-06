# Synthetic Control

##Analysis
The analysis code is split into several different files. The code in "synthetic_control_run.R" provides a template for defining initial constants, running analyses, and generating reports. The minimum files needed to run an analysis are the "synthetic_control_analysis.R" and "synthetic_control_functions.R", which contain the analysis code and functions necessary to run the analysis. Make sure these files, along with any additional code files, are in the same directory. See the table below for a short description of each file.

| File Name | File Dependencies | Details |
| --- | --- | ------------ |
|  synthetic_control_analysis.R | synthetic_control_functions.R | The main analysis code. |
|  synthetic_control_functions.R | N/A | Contains functions for the main analysis. |
|  synthetic_control_plot.R | synthetic_control_analysis.R, synthetic_control_functions.R | Plots results from analysis. |
|  synthetic_control_write_results.R | synthetic_control_analysis.R, synthetic_control_functions.R | Writes results from analysis to CSV files. |
|  synthetic_control_report.R | synthetic_control_analysis.R, synthetic_control_functions.R, synthetic_control_plot.R, synthetic_control_write_results.R, synthetic_control_report.Rmd | Handles package dependencies and prepares arguments for "synthetic_control_report.Rmd". |
|  synthetic_control_report.Rmd | synthetic_control_analysis.R, synthetic_control_functions.R, synthetic_control_plot.R | Generates an HTML report of analysis results containing tables and graphs. |
|  synthetic_control_run.R | synthetic_control_analysis.R, synthetic_control_functions.R, synthetic_control_plot.R, synthetic_control_write_results.R, synthetic_control_report.R, synthetic_control_report.Rmd | A template for running analyses containing a list of constants (and a breif description of each). Demonstrates how other relevant analysis files should be called. |
|  synthetic_control_set_vars.R | synthetic_control_analysis.R, synthetic_control_functions.R, synthetic_control_plot.R, synthetic_control_write_results.R, synthetic_control_report.R, synthetic_control_report.Rmd | A more complicated example of how the constants can be defined for multiple regions. Demonstrates how reports can be generated in a loop. |

##Data

To prepare data that can be used for analysis, make sure the date column is in the format YYYY-MM-DD. There should be only column that designates group stratification. If you wish to have multiple layers of stratification, combine the group columns into one column (e.g., region and age group columns could combine to a single age group-region column). The outcome and covariate columns (i.e., every column other than the date and group columns) should be numeric. The file type must be `.csv`. Sample datasets are provided as well - see below for more details.

###Sample Data

The sample data, found in the folder "Datasets for PNAS", are CSV files formatted for use with the synthetic control analysis. There are five files, each containing data from different countries. The data are subsetted by age group, which can be translated using the list below. In addition to the analysis files listed in the previous sections, the applet files can be found in the folder labeled "synthetic_control".

|Numeric Representation | Age Group |
| --- | ------------ |
|  0  | < 3 months |
|  1  | 3-<12 months |
|  2  | 12-24 months |
|  3  | 24-59 months |
|  4  | 5-<18 years |
|  5  | 18-<40 years |
|  6  | 40-<65 years |
|  7  | 65-<80 years |
|  8  | 80+ years |
|  9  | <12 months |

For the US, cells with fewer than 10 counts are replaced with 9999 due to privacy considerations.

##Web Applet

The synthetic control applet is a resource-intensive process. To handle concurrent users, there are multiple instances, listed below. Note that as computational resources are limited, not any size of dataset can be processed. If an analysis cannot be completed using the applet, download the analysis files and run on a machine you have access to.

https://weinbergerlab.shinyapps.io/synthetic_control/

https://weinbergerlab.shinyapps.io/synthetic_control_1/

https://weinbergerlab.shinyapps.io/synthetic_control_2/
