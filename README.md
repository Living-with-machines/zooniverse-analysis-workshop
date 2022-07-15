# Zooniverse: how to download and analyse your task annotations

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Living-with-machines/zooniverse-analysis-workshop/blob/main/process-zooniverse-data.ipynb)

<!-- TODO: insert DOI -->

Materials for a [British Library, Digital Scholarship](https://bl.uk/digital) "hack and yack" workshop.

[Zooniverse](https://www.zooniverse.org/) is probably the world’s most popular crowdsourcing platform, used by dozens of cultural heritage organisations. But the resulting annotations from Zooniverse can be hard to use ‘as is’. Do you want to learn how to turn Zooniverse data into something you can use in catalogues, on web pages or in research? Then this session is for you! Zooniverse: how to download and analyse your task annotations will introduce the widely used Zooniverse platform and the services it offers, and share new developments in using the Library’s IIIF items on Zooniverse. Then we get hands-on! You’ll learn how to process your annotations to obtain a clean and readable spreadsheet for your project.


## Aims of this tutorial

* Learn how to download Zooniverse data
* Learn how to run a Jupyter notebook
* Process your zooniverse data and obtain a `.csv` file


## A note before we start.. 

The following tutorial has been created for an audience who has some (basic or advanced) knowledge of Python and Jupyter Notebooks. However it is not just limited to them. In fact we want to make sure it is accessible to everyone, even to people who don't have any prior knowledge. 
Althought it might appear a bit daunting at the beginning, the code is easy to use and you just need to learn how to go through three main simple steps:

1. Downloading Zooniverse data
2. Uploading the annotations to the Jupyter Notebook
3. Exporting the output to your local computer

To make it easier for you to recognise these three steps, just follow the :pushpin: :pushpin: :pushpin: 

If you are interested in the entire process, just follow the notebook step by step. 
We've described every steps so that you can follow each stage of the process. 
If you have any questions do note hesitate to get in touch with us. 


## Another note before we start.. 

Options for running a Jupyter Notebook might seem a bit confusing at first. You can install software like Anaconda, or use web-based solutions like Colab, a Google product that allows anybody to write and execute arbitrary Python code through the browser. Colab is especially well suited to machine learning, data analysis and education. If you want to know more about Notebooks, take a look at Daniel van Strien’s ["Introduction to Jupyter Notebooks: the weird and the wonderful"](https://github.com/Living-with-machines/Jupyter-Notebooks-The-Weird-and-Wonderful).

## :pushpin: Downloading Zooniverse data

If you have run your own Zooniverse task and want to work on your Zooniverse data, we need to start by downloading it from the platform. In the following steps we'll see how to do so. 
In the following screenshots we have used a Mac, but if you have a Windows computer, the steps should be similar since you will be using your web browser. The most important part of this first instruction of our processing of your Zooniverse data is to remember where you store the files locally (see step 6 below).

### 1. :pushpin: Log in

First, [log in to Zooniverse](https://www.zooniverse.org/accounts/sign-in) as you normally would.

### 2. :pushpin: Navigate to lab page

Next, [navigate to the Zooniverse lab page](https://www.zooniverse.org/lab). On the page, you will see the projects where you are a collaborator:

<p align="center">
<img src="images/1-zooniverse-lab.png?raw=true" alt="A screenshot of the Zooniverse lab page" style="width:800px" title="Screenshot of Zooniverse lab page" />
</p>

### 3. :pushpin: Navigate to "Data Exports"

Next, click "Data Exports" in the right-hand menu bar:

<p align="center">
<img src="images/2-data-exports.png?raw=true" alt="A screenshot that shows where in the right-hand menu bar you will find the Data Exports option" style="width:800px;" title="Screenshot of Zooniverse lab splash page" />
</p>

### 4. :pushpin: Request relevant exports

Next, you will want to press the two buttons for "Request new classification export" and "Request new subject export":

<p align="center">
<img src="images/3-data-exports-requests.png?raw=true" alt="A screenshot that shows the relevant buttons to press on the Zooniverse Data Exports page" style="width:800px;" title="Screenshot of Zooniverse Data Exports page" />
</p>

### 5. :pushpin: Await the completed download

Your export might take a little while, but you will receive an email once your request is completed:

<p align="center">
<img src="images/4-confirmation-email.png?raw=true" alt="A screenshot that shows the confirmation email received when data export request has been completed" style="width:400px;" title="Screenshot of the confirmation email" />
</p>

### 6. :pushpin: Download the relevant files

Note that clicking the link "Download from your lab data exports page" in the confirmation email will only take you back to the Data Exports page.

Once you are back to the page, you need to use the correct links on the page to download the relevant CSV files:

<img src="images/5-request-completed.png?raw=true" alt="A screenshot that shows the data export request completed on the Data Exports page" style="width:800px;" title="Screenshot of the Data Exports page with the relevant links" />

For each of those two files, right-click and choose "Save Link As..."

<p align="center">
<img src="images/6-save-link-as.png?raw=true" alt="A screenshot that shows the popup menu to save CSV file from your browser in the correct directory" style="width:400px;" title="Screenshot of the menu that shows the option Save Link As..." />
</p>

Finally, you can save the file wherever you want on your computer, but remember the correct path to the files as you will need to fill them out in the next cell! _We suggest that you save the files with the names `classifications.csv` and `subjects.csv` in your `Downloads` folder as you will easily remember where you put them if you do so._

<p align="center">
<img src="images/7-rename.png?raw=true" alt="A screenshot that shows the renaming process of the CSV file" style="width:400px;" title="Screenshot of the download file dialog" />
</p>

Now, in the first cell in our notebook, we will register the path to the classifications file (as the `classifications_file` variable) and the subject file (as the `subjects_file` variable). All that information is included in the notebook itself.

## :pushpin: Open the Jupyter Notebook

In this workshop, we will use Notebooks on Colab.

### :pushpin: Option 1: Colab

#### :pushpin: Open the Colab Notebook
To open the Colab Notebook, follow this link:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Living-with-machines/zooniverse-analysis-workshop/blob/main/process-zooniverse-data.ipynb)

#### :pushpin: Upload your annotations to the Colab Notebook
Once you are inside your Colab Notebook, you need to upload the data. On the left side of the Colab interface you will see a folder called `Sample Data`. If it is hidden you can click on the icon of the folder:

<p align="center">
<img src="images/8-colab-upload.png?raw=true" alt="A screenshot that shows where to drag the files in the colab interface" style="width:800px;" title="Screenshot of the colab interface and where to upload the files." />
</p>

Drag and drop your files in the `sample_data` folder.

Now you are ready to start processing your data. To do so let’s move to [the notebook](https://colab.research.google.com/github/Living-with-machines/zooniverse-analysis-workshop/blob/main/process-zooniverse-data.ipynb).


#### :pushpin: Run the Colab Notebook
At this point, you simply need to click on `Runtime` and `Run all` (as suggested in the following screenshot)

<p align="center">
<img src="images/10-run-all.png?raw=true" alt="A screenshot that shows how to run all the cells of a notebook in Google Colab" style="width:800px;" title="Screenshot of Colab's runtime options" />
</p>

_First_, note that if you run the Colab, you will need to select "Run anyway" in this warning that will show up in your browser:

<p align="center">
<img src="images/9-colab-warning.png?raw=true" alt="A screenshot that shows the warning message displayed by Google Colab" style="width:400px;" title="Screenshot of Colab's warning dialog" />
</p>

#### :pushpin: Export your annotations

Once your notebook has finised processing the annotations, you'll see appearing your file on the `Sample Data` folder on the left side of your notebook. If you don't see it, just hover over the folder icon and the section will expand. 

To download your annotations simply click on the three dots at the right and select download. This way you'll save a version of the processed annotations on your local machine. 

<p align="center">
<img src="images/11-download.png?raw=true" alt="A screenshot that shows how to download your processed annotations from Google Colab" style="width:400px; align:center;" title="Screenshot of Colab's download button" />
</p>

<!--
### Option 2: On your own computer

TODO: Write intro + expand list below. Note that this is a little bit more involved and requires a pre-existing installation of Jupyter Notebooks and Python on your computer. As suggested by @mialondon in PR #3

1. Terminal: Clone repository + `cd` (note what @mialondon suggested in #4 that we may need specific instructions for mac/Windows here)
2. Move your classifications + subjects into the folder (or know where they are located on your computer)
3. `jupyter notebook` command
4. Now, you are ready to start processing your data.
-->
