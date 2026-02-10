<h1 align="center" style="font-size:48px">
AquaRisk : Intelligent Fluoride Risk Assessment System
</h1>

<p align="center">
An intelligent, data-driven, and scalable system for assessing groundwater fluoride risk across India using 
Machine Learning, Regression Models, and a Fuzzy Inference System (FIS). AquaRisk enables early identification 
of fluoride-vulnerable regions and supports data-backed decision-making for public health authorities and 
water resource planners.
</p>

<hr>

<h2>Project Objectives</h2>

<ul>
  <li><b>Nationwide Risk Assessment</b>: Analyzes over 16,776 groundwater samples collected from multiple Indian states and districts.</li>
  <li><b>Predictive Intelligence</b>: Applies advanced regression and classification models to estimate fluoride concentration and risk levels.</li>
  <li><b>Automated Risk Categorization</b>: Classifies regions into Safe, Moderate, and High-risk zones using optimized machine learning models.</li>
  <li><b>Explainable Insights</b>: Uses Mamdani-based Fuzzy Logic to convert numerical predictions into human-interpretable risk scores.</li>
  <li><b>Decision Support Visualization</b>: Enables spatial awareness through region-wise analysis and risk distribution.</li>
</ul>

<hr>

<h2>Dataset Architecture</h2>

<p>
The dataset consists of physicochemical and geospatial attributes that influence fluoride mobilization and 
accumulation in groundwater aquifers.
</p>

<table width="100%">
  <tr>
    <th align="left">Feature Category</th>
    <th align="left">Parameters Included</th>
  </tr>
  <tr>
    <td><b>Physicochemical</b></td>
    <td>pH, EC, TDS, Na⁺, Ca²⁺, Mg²⁺, K⁺, Cl⁻, SO₄²⁻, NO₃⁻, HCO₃⁻</td>
  </tr>
  <tr>
    <td><b>Target Variable</b></td>
    <td>Fluoride concentration (mg/L)</td>
  </tr>
  <tr>
    <td><b>Geospatial</b></td>
    <td>State and District identifiers</td>
  </tr>
</table>

<hr>

<h2>Data Preprocessing Pipeline</h2>

<ol>
  <li><b>Feature Standardization</b>: Uniform renaming of inconsistent column headers.</li>
  <li><b>Missing Value Treatment</b>: Invalid entries converted to NaN and handled using Median Imputation.</li>
  <li><b>Risk Label Assignment</b>: Classification based on WHO drinking water guidelines:
    <ul>
      <li>Safe: &lt; 1.5 mg/L</li>
      <li>Moderate Risk: 1.5 – 2.5 mg/L</li>
      <li>High Risk: &gt; 2.5 mg/L</li>
    </ul>
  </li>
  <li><b>Scaling</b>: Min–Max normalization to bring all features into a 0–1 range.</li>
  <li><b>Class Balancing</b>: SMOTE applied to handle class imbalance and ensure unbiased learning.</li>
</ol>

<hr>

<h2>Machine Learning Performance</h2>

<p>
Multiple models were evaluated to identify the most effective classifier for fluoride risk prediction.
</p>

<table width="100%">
  <tr>
    <th align="left">Model</th>
    <th align="left">Approach</th>
    <th align="left">Performance</th>
  </tr>
  <tr>
    <td><b>Random Forest</b></td>
    <td><b>Ensemble Learning</b></td>
    <td><b>93% Accuracy (Best Performer)</b></td>
  </tr>
  <tr>
    <td>XGBoost</td>
    <td>Gradient Boosting</td>
    <td>High Accuracy</td>
  </tr>
  <tr>
    <td>LightGBM</td>
    <td>Boosting</td>
    <td>Efficient at Scale</td>
  </tr>
  <tr>
    <td>ANN</td>
    <td>Neural Networks</td>
    <td>Complex Pattern Learning</td>
  </tr>
  <tr>
    <td>SVM (RBF)</td>
    <td>Kernel-based</td>
    <td>Non-linear Classification</td>
  </tr>
</table>

<h3>Regression Models (Continuous Prediction)</h3>

<table width="100%">
  <tr>
    <th align="left">Model</th>
    <th align="left">R² Score</th>
    <th align="left">RMSE</th>
  </tr>
  <tr>
    <td><b>Random Forest Regressor</b></td>
    <td><b>0.273</b></td>
    <td><b>0.684</b></td>
  </tr>
  <tr>
    <td>Linear Regression</td>
    <td>0.218</td>
    <td>0.709</td>
  </tr>
  <tr>
    <td>SVR</td>
    <td>0.174</td>
    <td>0.729</td>
  </tr>
</table>

<hr>

<h2>Fuzzy Logic Inference System (FIS)</h2>

<p>
A Mamdani-type Fuzzy Inference System is employed to manage uncertainty and translate model outputs into 
clear, interpretable fluoride risk scores.
</p>

<ul>
  <li><b>Input Linguistic Variables</b>: Very Low, Low, Normal, High, Very High.</li>
  <li><b>Output Risk Index</b>: 
    Low (&lt; 33), Medium (33–66), High (≥ 66).
  </li>
</ul>

<hr>

<h2>Limitations & Future Scope</h2>

<p><b>Current Limitations</b></p>
<ul>
  <li>Lack of seasonal and temporal groundwater variation.</li>
  <li>Focus limited to fluoride without multi-contaminant interaction.</li>
  <li>Absence of detailed hydrogeological layers.</li>
</ul>

<p><b>Future Enhancements</b></p>
<ul>
  <li>Integration of GIS-based real-time fluoride risk maps.</li>
  <li>Adoption of deep learning models for improved prediction accuracy.</li>
  <li>Explainability using SHAP/LIME for transparent AI-driven decisions.</li>
</ul>

<hr>

<h2>Installation & Usage</h2>

```bash
# Clone the repository
git clone https://github.com/Aishu9Para/AquaRisk.git

# Navigate to project directory
cd AquaRisk

# Install dependencies
pip install -r requirements.txt

# Run the application
python webapp.py
