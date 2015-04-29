# Code repository for the paper [[Bajardi et al. EPJ Data Science 2015]][unveiling]

The following IPython Notebooks contain the code that has been used to perform the data analysis of the paper "Unveiling patterns of international communities in a global city using mobile phone data" and allow to reproduce the main results.

## Contents

### IPython Notebooks

IPython notebooks are included with output, clicking on a link will open the corresponding notebook using the [nbviewer](http://nbviewer.ipython.org/) service.

- [00\_dataset\_to\_hdf5.ipynb](http://nbviewer.ipython.org/github/micheletizzoni/Bajardi-et-al-EPJDS-2015/blob/master/00_dataset_to_hdf5.ipynb)

  Parsing of the original dataset into an HDF5 store.

- [01\_dataset\_aggregation.ipynb](http://nbviewer.ipython.org/github/micheletizzoni/Bajardi-et-al-EPJDS-2015/blob/master/01_dataset_aggregation.ipynb)

  Aggregation of the dataset on wider time intervals.

- [02\_entropy\_timeseries.ipynb](http://nbviewer.ipython.org/github/micheletizzoni/Bajardi-et-al-EPJDS-2015/blob/master/02_entropy_timeseries.ipynb)

  Extraction of daily, monthly and yearly entropy time series.

- [03\_census\_rank\_comparison.ipynb](http://nbviewer.ipython.org/github/micheletizzoni/Bajardi-et-al-EPJDS-2015/blob/master/03_census_rank_comparison.ipynb)

  Correlation between mobile calls volume and foreign resident population reported by census.

- [04\_poi\_classifier.ipynb](http://nbviewer.ipython.org/github/micheletizzoni/Bajardi-et-al-EPJDS-2015/blob/master/04_poi_classifier.ipynb)

  Classifier of point of interests based on entropy and phone activity.

- [05\_persistent\_homology/](05_persistent_homology)

  - [01_entropy_activity_cell_selection.ipynb](http://nbviewer.ipython.org/github/micheletizzoni/Bajardi-et-al-EPJDS-2015/blob/master/05_persistent_homology/01_entropy_activity_cell_selection.ipynb)

  - [02_country_phom_low_entropy.ipynb](http://nbviewer.ipython.org/github/micheletizzoni/Bajardi-et-al-EPJDS-2015/blob/master/05_persistent_homology/02_country_phom_low_entropy.ipynb)

  - [03_results_phom_activity_entropy.ipynb](http://nbviewer.ipython.org/github/micheletizzoni/Bajardi-et-al-EPJDS-2015/blob/master/05_persistent_homology/03_results_phom_activity_entropy.ipynb)

### Data

- [data/countries](data/countries)

  Associations between country names and international calling codes, source: [github/mledoze](https://github.com/mledoze/countries). See the accompanying [notebook](data/countries/parse_mledoze_countries.ipynb) for the parsing procedure.

- [data/districts](data/districts)

  Census data for the city of Milan aggregate by NIL (Nuclei di Identità Locale), source: [http://dati.comune.milano.it](http://dati.comune.milano.it).

- [data/poi](data/poi)

  List of point of interests in Milan as defined by TripAdvisor, source: [http://www.tripadvisor.com/Attractions-g187849-Activities-Milan_Lombardy.html](http://www.tripadvisor.com/Attractions-g187849-Activities-Milan_Lombardy.html)

- [data/phom](data/phom)

  Remittance data used to compare clusters of countries based on persisten homology, source:[http://data.worldbank.org/indicator/BX.TRF.PWKR.DT.GD.ZS](http://data.worldbank.org/indicator/BX.TRF.PWKR.DT.GD.ZS).

## Running the IPython notebooks

In order to execute the notebooks you will need additional data and a working python environment containing the required dependencies.

### Additional Data

Download the complete dataset ["Telecommunications - SMS, Call, Internet - MI"](https://dandelion.eu/datagems/SpazioDati/telecom-sms-call-internet-mi/resource) inside the project sub-directory [data/telco](data/telco).

### Git submodules

Install the required submodules by running:

    git submodule init
    git submodule update

### Python dependencies

Python dependencies can be installed in a virtual environment using the following instructions inside the project root directory:

    virtualenv virtualenv
    . virtualenv/bin/activate 
    pip install -r requirements.txt && pip install tables

To start an IPython notebook server using the newly created virtual environment:

    . virtualenv/bin/activate
    ipython notebook

### Running the notebooks

Select a notebook using the IPython notebook interface and execute its cells. To correctly reproduce the analysis pipeline the notebooks must be executed according to the progressive numbering.


## Contributing

You can report eventual bugs or issues using the GitHub issue tracking tool.

## License

See [LICENSE.txt](LICENSE.txt).

[unveiling]: http://www.epjdatascience.com/content/4/1/3
