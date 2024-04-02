# White House remarks

This repository has code for collecting and analyzing thousands of remarks delivered by former President Donald Trump and current President Joe Biden.

## Process

The remarks are retrieved from the their respective media release pages using Jupyter [notebooks](notebooks/) and Python (and its `requests` and `BeautifulSoup` libraries for collection and parsing).

### Sources

To gather the speeches, the notebooks collect metadata about each press release issued in their respective briefing/news pages:

- **Former President Trump (January 2017 - January 2021):** [White House news archive](https://trumpwhitehouse.archives.gov/news/)
- **President Biden (January 2021-present):** [White House briefing room](https://www.whitehouse.gov/briefing-room/)

### Scrapers and outputs

Each row in the metadata contains information about the release: `headline`, `url`, `category`, `news archive page`, `location` (if listed) and `date`. 

#### Categories

**Trump:** `executive orders`, `statements & releases`, `presidential memoranda`, *`remarks`*, `proclamations`, `nominations & appointments`, `press briefings`, `fact sheets`, `news clips`


**Biden:** *`speeches and remarks`*, `statements and releases`, `presidential actions`, `legislation`, `press briefings`, `disclosures`, `blog`


Then notebooks then scrape the full text of each announcement, including those that include transcripts of "remarks," which are analyzed later.

#### Breakdown of records collected

| President | Total releases | Total 'remarks' | Formats |
|:--------|-------:|--------:|---------|
| [Trump notebooks](notebooks/trump/) | 8,478 | Xy | csv, json |
| [Biden notebooks](notebooks/biden/) | 9,922 | Xy | csv, json |

 *<sup>Note: Biden release count last updated on March 24, 2024.</sup>*

---

## Use this code

### Prerequisites

Before you begin, ensure you have the following installed on your system:
- Python 3.10
- [Jupyter Lab](https://jupyter.org/install)

We recommend using a virtual environment for Python projects. For this repo, [`pipenv`](https://pipenv.pypa.io/en/latest/) is the chosen manager.

### Getting Started

Follow these steps to prepare your environment:

#### 1. **Clone the repo**

First, clone this repository to your local machine and navigate into it using your terminal:

```bash
git clone <repository-url>
cd <repository-name>
```

#### 2. **Create a virtual environment**
Inside the repository directory, initiate a virtual environment using pipenv:

```
pipenv shell
```

This command creates a virtual environment and activates it.

#### 3. Install dependencies

Install the required dependencies, including [Pandas](https://pandas.pydata.org/), [Geopandas](https://geopandas.org/en/stable/) and others, with the following command:

```
pipenv install
```

### Launching Jupyter Lab

With your environment set up and dependencies installed, you are ready to start working with the notebooks:


```
jupyter lab
```

This command launches Jupyter Lab in your browser, where you can open, edit and run the notebooks.