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

<!-- ===================== FUTURE TASKS ===================== -->

<h2>Upcoming Tasks</h2>
<p>
Additional tasks from the Quantium Virtual Experience will be added here as they are completed.
</p>
