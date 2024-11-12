# C/NOFS-CINDI-Zonal-electric-field
README: Altitude-Wise Electric Field Analysis from C/NOFS CINDI Zonal Electric Field Data
Overview

This project performs an altitude-wise analysis of the zonal electric field (E_ZONAL) data obtained from the C/NOFS (Communication/Navigation Outage Forecasting System) 
CINDI (Coupled Ion-Neutral Dynamic Investigation) experiment. The data contains measurements of electric field values at different altitudes and geographical locations, 
which are analyzed to calculate daily average electric field values for several altitude ranges.

The analysis is divided into two parts:

    Part 1: Analyzing the electric field for two altitude ranges (410–610 km and 610–835 km).
    Part 2: Analyzing the electric field for four altitude ranges (410–510 km, 510–610 km, 610–710 km, and 710–835 km).

The data is read from a text file, processed to clean and filter based on geographical ranges, and then daily averages are computed. 
Finally, the results are visualized through plots that compare the electric field values for the different altitude ranges.

Code Overview
Part 1: Two Altitude Ranges (410–610 km and 610–835 km)

    File Path & Data Loading:
        The data is loaded from a fixed-width text file located at file_path.
        The fixed-width column sizes are predefined based on the data format.

    Data Processing:
        The EPOCH column is split into DATE and TIME columns.
        Latitude and longitude values are filtered based on predefined geographical boundaries.
        The E_ZONAL and ALTITUDE columns are cleaned and filtered to ensure valid values are kept.

    Altitude Range Segregation:
        The data is segregated into two altitude ranges:
            Range 1: 410–610 km
            Range 2: 610–835 km

    Daily Average Calculation:
        The E_ZONAL values are averaged for each day, and a relative day index is created based on the reference date (27/02/2010).

    Plotting:
        A plot is generated showing the daily averaged E_ZONAL values for the two altitude ranges.

    Saving the Plot:
        The plot is saved as a PNG file in the same directory as the input file.

Part 2: Four Altitude Ranges (410–510 km, 510–610 km, 610–710 km, 710–835 km)

    Data Processing:
        Similar to Part 1, data is loaded, processed, and filtered based on latitude and longitude.
        The E_ZONAL and ALTITUDE columns are cleaned and filtered for valid values.

    Altitude Range Segregation:
        The data is segregated into four altitude ranges:
            Range 1: 410–510 km
            Range 2: 510–610 km
            Range 3: 610–710 km
            Range 4: 710–835 km

    Daily Average Calculation:
        The E_ZONAL values are averaged for each day, and a relative day index is calculated as in Part 1.

    Plotting:
        A plot is generated showing the daily averaged E_ZONAL values for the four altitude ranges.

    Saving the Plot:
        The plot is saved as a PNG file in the same directory as the input file.

Code Breakdown
1. Data Loading and Processing

    File Path: The data file is located at a fixed path, which should be adjusted if the file is located elsewhere.
    Fixed Width Columns: The columns in the data are fixed-width, so pandas.read_fwf() is used to load the data with specified column widths.
    Filtering Latitude and Longitude: Data is filtered based on predefined geographical latitude and longitude ranges.

2. Daily Average Calculation

    E_ZONAL Averaging: The E_ZONAL values are grouped by the DATE column to calculate daily averages.
    Relative Day Calculation: The DATE column is converted into a relative day format, where day 0 corresponds to the reference date (27/02/2010).

3. Plotting

    Matplotlib: matplotlib is used to generate plots that visualize the daily averaged electric field values for the specified altitude ranges.
    Customization: The plots are customized with labels, titles, and gridlines for clarity. A legend is also added to differentiate the altitude ranges.

4. Saving the Plot

    The plot is saved as a PNG file in the same directory as the input data file using plt.savefig().

Dependencies

To run the code successfully, ensure that the following Python libraries are installed:

    pandas: For data manipulation and analysis.
    matplotlib: For plotting the data.
    datetime: For date manipulation and calculation of relative days.
    os: For handling file paths and saving the output plot.

You can install the required libraries using pip:

pip install pandas matplotlib

Output

The code generates two plots:

    Plot for Two Altitude Ranges (410–610 km and 610–835 km):
        Saved as e_zonal_altitude_ranges_plot.png in the same directory as the input file.

    Plot for Four Altitude Ranges (410–510 km, 510–610 km, 610–710 km, 710–835 km):
        Saved as e_zonal_altitude_ranges_plot_4_ranges.png in the same directory as the input file.

The plots show the daily averaged electric field values (E_ZONAL) for each altitude range, with days relative to the reference date of 27/02/2010 on the x-axis and the electric field in mV/m on the y-axis.
Future Enhancements

    Interactive Plots: Consider using libraries such as plotly to create interactive plots that allow for zooming and tooltips.
    Data Export: You could add functionality to save the daily averaged values to a CSV file for further analysis.

Conclusion

This code allows for detailed analysis of zonal electric field values from the C/NOFS CINDI data at different altitude ranges, with daily averaged results visualized through plots. The flexibility in adjusting altitude ranges and geographical filtering makes it adaptable for various data analysis needs.
