<h2>Quantium Virtual Experience – Task 1</h2>

<p>
This project was completed as part of the Quantium Virtual Experience Program on
<a href="https://www.theforage.com/" target="_blank"> Forage </a>.
The objective of this task was to set up a professional Python development environment and manage project dependencies.
</p>

<hr>

<h3>Task Objectives</h3>
<ul>
  <li>Fork and clone the starter repository from GitHub</li>
  <li>Set up a Python virtual environment</li>
  <li>Install required project dependencies</li>
  <li>Push the configured project to GitHub</li>
</ul>

<hr>

<h3>Steps Performed</h3>

<h4>1. Fork and Clone Repository</h4>
<p>Forked the starter repository and cloned it to the local system.</p>

<pre>
git clone https://github.com/your-username/quantium-starter-repo.git
cd quantium-starter-repo
</pre>

<h4>2. Create Virtual Environment</h4>
<p>Created a Python virtual environment to isolate project dependencies.</p>

<pre>
python -m venv venv
</pre>

<h4>3. Activate Virtual Environment (Windows)</h4>

<pre>
.\venv\Scripts\Activate
</pre>

<p>After activation, the terminal shows:</p>

<pre>
(venv)
</pre>

<h4>4. Install Required Dependencies</h4>

<pre>
python -m pip install dash
python -m pip install pandas
python -m pip install "dash[testing]"
</pre>

<h4>5. Commit and Push Changes</h4>

<pre>
git add .
git commit -m "Completed Quantium Task 1 environment setup"
git push origin main
</pre>

<hr>

<h3>Skills Gained</h3>
<ul>
  <li>Git & GitHub workflow (Fork, Clone, Commit, Push)</li>
  <li>Python Virtual Environment management</li>
  <li>Dependency management using pip</li>
  <li>Professional project environment setup</li>
</ul>

<hr>

<h3>Technologies Used</h3>
<ul>
  <li>Python</li>
  <li>Dash</li>
  <li>Pandas</li>
  <li>Virtual Environment (venv)</li>
  <li>Visual Studio Code</li>
  <li>Git & GitHub</li>
</ul>


<hr>

<h2>Task 2 – Sales Data Processing</h2>

<p>
This task is part of the 
<a href="https://www.theforage.com/" target="_blank">
Forage Data Analytics Virtual Experience
</a>.
The objective was to process raw CSV sales data and convert it into a clean, structured format for analysis.
</p>

<h3>Objective</h3>
<ul>
    <li>Combine multiple CSV files into one dataset</li>
    <li>Clean and transform raw data</li>
    <li>Calculate total sales for each transaction</li>
</ul>

<h3>Input Files</h3>
<p>The following files were provided inside the <b>data/</b> folder:</p>
<ul>
    <li>daily_sales_data_0.csv</li>
    <li>daily_sales_data_1.csv</li>
    <li>daily_sales_data_2.csv</li>
</ul>

<h3>Processing Steps Performed</h3>
<ol>
    <li>Read all CSV files from the <b>data</b> directory</li>
    <li>Removed the <b>$</b> symbol from the price column</li>
    <li>Converted <b>price</b> to float and <b>quantity</b> to integer</li>
    <li>Calculated total sales using:<br>
        <code>Sales = price × quantity</code>
    </li>
    <li>Extracted required fields:
        <ul>
            <li>Sales</li>
            <li>Date</li>
            <li>Region</li>
        </ul>
    </li>
    <li>Combined all records into a single output file</li>
</ol>

<h3>Output File</h3>
<p>
A new file was generated:<br>
<b>formatted_sales_data.csv</b>
</p>

<h3>Python Script Used</h3>

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
    <li>Python CSV handling</li>
    <li>Data cleaning and transformation</li>
    <li>File automation using glob</li>
    <li>Basic data processing for analysis</li>
</ul>

<h3>Project Repository</h3>
<p>
View the complete project here: 
<a href="YOUR_GITHUB_LINK_HERE" target="_blank">
GitHub Repository
</a>
</p>
