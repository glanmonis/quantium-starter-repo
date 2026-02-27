<h1>Quantium Data Analytics Virtual Experience</h1>

<p>
This project was completed as part of the Quantium Virtual Experience Program on 
<a href="https://www.theforage.com/" target="_blank">Forage</a>.  
The experience focuses on real-world data analytics tasks including environment setup, data processing, and analysis using Python.
</p>

<hr>

<!-- ===================== TASK 1 ===================== -->

<h2>Task 1 – Development Environment Setup</h2>

<h3>Objective</h3>
<ul>
  <li>Fork and clone the starter repository</li>
  <li>Set up a Python virtual environment</li>
  <li>Install required dependencies</li>
  <li>Push the configured project to GitHub</li>
</ul>

<h3>Steps Performed</h3>

<h4>1. Clone Repository</h4>
<pre>
git clone https://github.com/your-username/quantium-starter-repo.git
cd quantium-starter-repo
</pre>

<h4>2. Create Virtual Environment</h4>
<pre>
python -m venv venv
</pre>

<h4>3. Activate Environment (Windows)</h4>
<pre>
.\venv\Scripts\Activate
</pre>

<p>After activation, the terminal shows:</p>
<pre>(venv)</pre>

<h4>4. Install Dependencies</h4>
<pre>
python -m pip install dash
python -m pip install pandas
python -m pip install "dash[testing]"
</pre>

<h4>5. Push Changes</h4>
<pre>
git add .
git commit -m "Completed Task 1 setup"
git push origin main
</pre>

<h3>Skills Gained</h3>
<ul>
  <li>Git & GitHub workflow</li>
  <li>Python virtual environment management</li>
  <li>Dependency installation using pip</li>
  <li>Professional project setup</li>
</ul>

<hr>

<!-- ===================== TASK 2 ===================== -->

<h2>Task 2 – Sales Data Processing</h2>

<h3>Objective</h3>
<ul>
    <li>Process raw CSV files into a clean dataset</li>
    <li>Combine multiple files into a single output</li>
    <li>Calculate total sales for each transaction</li>
</ul>

<h3>Input Data</h3>
<p>CSV files provided inside the <b>data/</b> folder:</p>
<ul>
    <li>daily_sales_data_0.csv</li>
    <li>daily_sales_data_1.csv</li>
    <li>daily_sales_data_2.csv</li>
</ul>

<h3>Data Processing Steps</h3>
<ol>
    <li>Read all CSV files from the data directory</li>
    <li>Removed the <b>$</b> symbol from the price column</li>
    <li>Converted price to float and quantity to integer</li>
    <li>Calculated total sales:<br>
        <code>Sales = Price × Quantity</code>
    </li>
    <li>Selected required fields:
        <ul>
            <li>Sales</li>
            <li>Date</li>
            <li>Region</li>
        </ul>
    </li>
    <li>Exported the cleaned data into a single file</li>
</ol>

<h3>Output</h3>
<p>
Generated file: <b>formatted_sales_data.csv</b>
</p>

<h3>Python Script</h3>
<pre>
import csv
import glob

output_file = "formatted_sales_data.csv"
input_files = glob.glob("data/*.csv")

with open(output_file, "w", newline="") as outfile:
    writer = csv.writer(outfile)
    writer.writerow(["Sales", "Date", "Region"])
    
    for file in input_files:
        with open(file, "r") as infile:
            reader = csv.DictReader(infile)
            
            for row in reader:
                price = float(row["price"].replace("$", ""))
                quantity = int(row["quantity"])
                sales = price * quantity
                
                writer.writerow([
                    round(sales, 2),
                    row["date"],
                    row["region"]
                ])

print("Formatted file created successfully!")
</pre>

<h3>Skills Gained</h3>
<ul>
    <li>CSV file handling in Python</li>
    <li>Data cleaning and transformation</li>
    <li>Data aggregation and processing</li>
    <li>Automation using glob</li>
</ul>

<hr>


<!-- =====================TASK 3 ===================== -->

<h2>Quantium Virtual Experience – Task 3</h2>

<p>
This task focused on visualising the sales data generated in Task 2 using a Dash web application. The objective was to determine the impact of the Pink Morsel price increase on overall sales, providing Soul Foods with a clear and simple visual insight.
</p>

<h3>Task Objective</h3>
<ul>
  <li>Create a Dash app to visualise sales data from <b>formatted_sales_data.csv</b></li>
  <li>Implement a line chart showing <b>Sales vs Date</b></li>
  <li>Sort the data chronologically to ensure accurate visualization</li>
  <li>Add a clear header for the dashboard</li>
</ul>

<h3>Steps Performed</h3>
<ol>
  <li>Imported required libraries: <b>pandas</b>, <b>Dash</b>, <b>Plotly Express</b></li>
  <li>Loaded the cleaned sales data from Task 2</li>
  <li>Converted the <b>Date</b> column to datetime type and sorted the data</li>
  <li>Created a line chart using <b>Plotly Express</b> with appropriate axis labels and title</li>
  <li>Initialized a Dash app and added a header along with the line chart to the layout</li>
  <li>Ran the app locally to visualise the data</li>
</ol>

<h3>Python Code Snippet</h3>
<pre>
import pandas as pd
from dash import Dash, html, dcc
import plotly.express as px

df = pd.read_csv("./formatted_sales_data.csv")
df["Date"] = pd.to_datetime(df["Date"])
df = df.sort_values("Date")

fig = px.line(df, x="Date", y="Sales", title="Pink Morsel Sales Over Time")

app = Dash(__name__)
app.layout = html.Div([
    html.H1("Soul Foods Sales Visualiser"),
    dcc.Graph(figure=fig)
])

if __name__ == "__main__":
    app.run(debug=True)
</pre>

<h3>Skills Gained</h3>
<ul>
  <li>Building interactive dashboards using Dash</li>
  <li>Data visualization using Plotly Express</li>
  <li>Handling and processing date-based data in pandas</li>
  <li>Sorting and presenting data for clear business insights</li>
</ul>

<h3>Screenshot</h3>
<p>Below is a small screenshot of the dashboard displaying the sales line chart:</p>
<img src="screenshot_task3.png" alt="Task 3 Dash App Screenshot" width="500">


<!-- =====================TASK 4 ===================== -->
<h2>– Task 4</h2>



<!-- =====================TASK 5 ===================== -->
<!-- =====================TASK 6 ===================== -->
