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
