# Zooniverse: how to download and analyse your task annotations

<!-- TODO: insert DOI -->

Materials for a British Library, Digital Scholarship "hack and yack" workshop.

Zooniverse is probably the world’s most popular crowdsourcing platform, used by dozens of cultural heritage organisations. But the resulting annotations from Zooniverse can be hard to use ‘as is’. Do you want to learn how to turn Zooniverse data into something you can use in catalogues, on web pages or in research? Then this session is for you! Zooniverse: how to download and analyse your task annotations will introduce the widely used Zooniverse platform and the services it offers, and share new developments in using the Library’s IIIF items on Zooniverse. Then we get hands-on! You’ll learn how to process your annotations to obtain a clean and readable spreadsheet for your project.

If you are new to Jupyter Notebooks, may we suggest Daniel van Strien's ["Introduction to Jupyter Notebooks: the weird and the wonderful"](https://github.com/Living-with-machines/Jupyter-Notebooks-The-Weird-and-Wonderful).

<!-- Suggested by @mialondon in PR #3:
## How to open Notebooks from GitHub
[Note that we'll need to provide instructions for running Notebooks in a way that you can also work with local data files]
-->

## Aims

* Learn how to download Zooniverse data
* Learn how to run a Jupyter notebook
* Process your zooniverse data and obtain a .CSV file

## Downloading Zooniverse data

### 1. Log in

First, [log in to Zooniverse](https://www.zooniverse.org/accounts/sign-in) as you normally would.

### 2. Navigate to lab page

Next, [navigate to the Zooniverse lab page](https://www.zooniverse.org/lab). On the page, you will see the projects where you are a collaborator:

<img src="images/annotations-json-to-csv/1-zooniverse-lab.png?raw=true" alt="A screenshot of the Zooniverse lab page" style="max-width:75%;" title="Screenshot of Zooniverse lab page" />

### 3. Navigate to "Data Exports"

Next, click "Data Exports" in the right-hand menu bar:

<img src="images/annotations-json-to-csv/2-data-exports.png?raw=true" alt="A screenshot that shows where in the right-hand menu bar you will find the Data Exports option" style="max-width:75%;" title="Screenshot of Zooniverse lab splash page" />

### 4. Request relevant exports

Next, you will want to press the two buttons for "Request new classification export" and "Request new subject export":

<img src="images/annotations-json-to-csv/3-data-exports-requests.png?raw=true" alt="A screenshot that shows the relevant buttons to press on the Zooniverse Data Exports page" style="max-width:75%;" title="Screenshot of Zooniverse Data Exports page" />

### 5. Await the completed download

Your export might take a little while, but you will receive an email once your request is completed:

<img src="images/annotations-json-to-csv/4-confirmation-email.png?raw=true" alt="A screenshot that shows the confirmation email received when data export request has been completed" style="max-width:75%;" title="Screenshot of the confirmation email" />

### 6. Download the relevant files

Note that clicking the link "Download from your lab data exports page" in the confirmation email will only take you back to the Data Exports page.

Once you are back to the page, you need to use the correct links on the page to download the relevant CSV files:

<img src="images/annotations-json-to-csv/5-request-completed.png?raw=true" alt="A screenshot that shows the data export request completed on the Data Exports page" style="max-width:75%;" title="Screenshot of the Data Exports page with the relevant links" />

For each of those two files, right-click and choose "Save Link As..."

<img src="images/annotations-json-to-csv/6-save-link-as.png?raw=true" alt="A screenshot that shows the popup menu to save CSV file from your browser in the correct directory" style="max-width:30%;" title="Screenshot of the menu that shows the option Save Link As..." />

Finally, you can save the file wherever you want on your computer, but remember the correct path to the files as you will need to fill them out in the next cell! _We suggest that you save the files with the names `classifications.csv` and `subjects.csv` in your `Downloads` folder._

<img src="images/annotations-json-to-csv/7-rename.png?raw=true" alt="A screenshot that shows the renaming process of the CSV file" style="max-width:30%;" title="Screenshot of the download file dialog" />

Now, in the following cell, which is a Notebook cell registering your variable, we need you to fill in the path to the classifications file (as the `classifications_file` variable) and the subject file (as the `subjects_file` variable).

As an example, if you saved the `classifications.csv` and `subjects.csv` files in the `Downloads` folder above (like in the screenshot), you might want to change the lines below to:

Now let's head over to the real notebook: //// TODO: add link////

## Open the Jupyter Notebook on Colab

Running a Jupyter Notebook might seem a bit confusing at the beginning. For this reason we have saved a version in Colab, a Google product that allows anybody to write and execute arbitrary Python code through the browser, and is especially well suited to machine learning, data analysis and education.

If you want to know more about Notebooks and set up alternative systems, like installing Anaconda and running the Notebook on your machine, we suggest to look at Daniel van Strien's tutorial ["Introduction to Jupyter Notebooks: the weird and the wonderful"](https://github.com/Living-with-machines/Jupyter-Notebooks-The-Weird-and-Wonderful).

However, for the purposes of this workshop, we will work on Colab.

To open the Colab Notebook follow this link: //// TODO: add link ////

### 1. Upload the annotations

First, we need to upload the data.
On the left side of the Colab interface you might see there is a folder called `Sample Data`.
If it is hidden you can click on the icon of the folder.

<img src="images/annotations-json-to-csv/8-colab-upload.png?raw=true" alt="A screenshot that shows where to drag the files in the colab interface" style="max-width:75%;" title="Screenshot of the colab interface and where to upload the files." />

Drag and drop your files in the `sample_data` folder.

Now you are ready to start processing your data. To do so let's move to the notebook.
