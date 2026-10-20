# 📚 Pre-Class: NumPy for Data Analysts

**Estimated Time:** 30–45 minutes
**Prerequisites:** Lesson 1.5 — Advanced SQL

> In Lessons 1.3–1.5 you worked with data stored in databases, querying it with SQL. From this lesson onward, you'll work with data directly in Python. NumPy is the foundation — it's the numerical computing library that Pandas (Lesson 1.7) and every machine learning library is built on top of.

---

## What is NumPy?

NumPy (Numerical Python) gives Python the ability to work with large arrays of numbers extremely fast. Where plain Python stores data in lists (one item at a time), NumPy stores it in **arrays** — grids of numbers optimised for mathematical operations.

Think of it this way: if a Python list is a column of cells in Excel, a NumPy array is the entire spreadsheet — and NumPy can do maths on every cell simultaneously, without loops.

You'll use NumPy throughout the rest of this course as the underlying engine for data manipulation and modelling.

---

**Watch [NumPy Intro Video](https://www.youtube.com/watch?v=SuI27ERy0-A)**

<img width="656" height="218" alt="M1 6" src="https://github.com/user-attachments/assets/9cbee189-e548-4a0c-94ff-49d6e87b792b" />



## 1\. What is a Jupyter Notebook?

During the lab we will work in **Jupyter notebooks**, either in VS Code or Google Colab.

A Jupyter notebook is an interactive document that can contain:

- Code cells (that you can run)  
- Text cells (explanations, instructions, notes)  
- Outputs (tables, charts, printed results)

You run each code cell independently and see the result immediately below it.  
We’ll use notebooks to experiment with NumPy and to complete hands-on exercises.

If you have never seen a notebook before, watch this short intro first:
▶️ [Jupyter Notebook Tutorial for Beginners](https://www.youtube.com/watch?v=HW29067qVWk) (the first 3 mins for a quick look, the remaining is optional)

You do **not** need to understand everything yet; just get familiar with:

- What a “cell” is
- How to run a cell
- How to see output

---

## 2. Using VS Code (desktop option, recommended)

If you prefer to work in **VS Code**, you can either run notebooks **locally** or connect VS Code to **Google Colab** as the execution environment.

### 2.1. Install required VS Code extensions

In VS Code:

1. Open the **Extensions** panel (left sidebar, square icon).  
2. Install these extensions:  
   - **Python** (by Microsoft)  
   - **Jupyter** (by Microsoft) – adds notebook support in VS Code  
   - **Colab** (VS Code extension) – lets you use Google Colab as a compute environment from VS Code

After installation, restart VS Code if prompted.

### 2.2. What is an environment, and setting up `pds`

**What is an environment?** A conda environment is an isolated Python installation with its own set of packages and versions — separate from your system Python and from other projects' environments. This course ships an `environment.yml` file that pins the exact packages (NumPy, Pandas, Jupyter, etc.) needed for the lessons. Creating an environment from it gives everyone the same versions, so code that runs for the instructor runs the same way for you — no "works on my machine" surprises, and no risk of breaking other Python projects on your computer.

**Prerequisite:** conda installed (via [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or Anaconda). If you already set this up in an earlier lesson, skip ahead.

Set up the environment:

1. Open a terminal in VS Code (**Terminal → New Terminal**), in this repo's root folder (where `environment.yml` lives).  
2. Create the environment:

```bash
conda env create -f environment.yml
```
> If there is an existing environment with the same name, run following command to replace it:
>
> ```bash
> conda env update --file environment.yml --prune
> ```
>
3. Activate it:

```bash
conda activate pds
```

4. In VS Code, select this environment as the kernel: open the notebook, click the kernel picker (top-right of the notebook), and choose **pds**.


  a) selecting the kernel in the notebook, a dropdown menu will appear at the top of the screen, select Python Environments....
<img width="1195" height="220" alt="image" src="https://github.com/user-attachments/assets/f895858b-e2d0-4b53-8fc9-5d597b6e17e1" />

  b) a list of available Python environments will show up, look for the one labeled pds
<img width="602" height="178" alt="image" src="https://github.com/user-attachments/assets/6b7ebc77-02b4-4bdb-a9a1-66d9571f7189" />


  c) once selected, the top right corner will change from "Select Kernel" to showing the Python version and the environment name (e.g., Python 3.10.x ('pds')).
<img width="1354" height="135" alt="image" src="https://github.com/user-attachments/assets/8bd3d981-7da4-49b0-9b41-7939970308ee" />




### 2.3. Test Jupyter notebooks in VS Code (local Python)

1. Open VS Code.  
     
2. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS).  
     
3. Type **Jupyter: Create New Jupyter Notebook** and select it.  
     
4. Select the **pds** kernel (top-right of the notebook) if it isn't already selected.

5. In the first cell, type:

```py
import numpy as np
np.__version__
```

6. Run the cell (click the ▶ button).  
     
7. Confirm that the output shows a NumPy version and no error.

If this works, your local Jupyter environment in VS Code is ready.


<img width="692" height="532" alt="image" src="https://github.com/user-attachments/assets/eb955c15-cf3f-4a3a-ae7b-e16b0d0bfaf7" />






### 2.4. (Optional) Use Colab as the environment in VS Code

If you installed the **Colab** extension, you can run notebooks on Colab from within VS Code:

1. Sign into your Google account in the Colab extension if prompted.  
     
2. Open a `.ipynb` notebook in VS Code.  
     
3. Use the Colab extension UI to select Colab as the kernel / compute environment (the exact command name may vary slightly depending on extension version).  
     
4. Run a test cell:

```py
import numpy as np
np.__version__
```

If this runs successfully, you are ready to use Colab’s backend while working in the VS Code interface.

**Choose Auto Connect for first time setting up**
<img width="824" height="390" alt="image" src="https://github.com/user-attachments/assets/de59f122-2e90-425d-af2f-8c15ab2d63e4" />


---


## 3\. Using Google Colab (browser option, alternative)

If you plan to use **Google Colab** in the browser:

### 3.1. Requirements

- A Google account (Gmail or Workspace)  
- Google Chrome browser

### 3.2. Install the “Open in Colab” Chrome extension

This extension lets you open GitHub-hosted notebooks in Colab with one click.

1. Open the [Open in Colab Chrome extension page](https://chromewebstore.google.com/detail/open-in-colab/iogfkhleblhcpcekbiedikdehleodpjo?hl=en-US&utm_source=ext_sidebar)
2. Click **Add to Chrome** and confirm.
3. After installation, you should see the extension icon in your Chrome toolbar.

What it does: on any GitHub notebook page, a button appears that opens the notebook directly in Colab so you can run the code immediately.

### 3.3. Test Colab

Before class:

1. Go to [https://colab.research.google.com](https://colab.research.google.com)  
     
2. Click **New notebook**.  
     
3. In the first cell, type:

```py
import numpy as np
np.__version__
```

4. Click **Run** (the ▶ button on the left of the cell) and confirm it runs without errors.

If this works, your Colab setup is ready.


---

## 4\. Choose your environment for class

For the lab, please **choose one** environment:

- **Option A – VS Code with Jupyter (recommended):**  
    
  - Python 3.x installed  
  - VS Code installed with Python and Jupyter extensions  
  - You have successfully run a notebook cell with `import numpy as np`


- **Option B – Google Colab (alternative):**  
    
  - Chrome \+ “Open in Colab” extension installed  
  - You have successfully run a Colab notebook with `import numpy as np`

You do **not** need to install NumPy separately if you use Colab; it is already included.


**select/switch to A or B environment from kernel button (in green)**
<img width="809" height="98" alt="image" src="https://github.com/user-attachments/assets/945b972d-53b9-4b07-98ca-16daf26ca227" />






---

## 5\. What you do *not* need before class

You do **not** need to:

- Know advanced Python features  
- Know linear algebra

We will build everything step by step in class, using guided exercises.

---

If you get stuck during setup, take a screenshot of the error and post it in **#questions** on Discord.
