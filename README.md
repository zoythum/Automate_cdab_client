# Automating the execution

## Script
The `automate.py` script is intended to automate the execution process for the [cdab-client](https://github.com/esa-cdab/cdab-testsuite/wiki/Command-Line-Tools#cdab-client).

## Registering to SciHub
To ensure that the execution of the `cdab-client` works as expected a SciHub account must be provided, after the [registration](https://scihub.copernicus.eu/dhus/#/self-registration) phase is completed write the  email and password into the `config.json` file and the script will automatically produce the correct [config.yaml](https://github.com/esa-cdab/cdab-testsuite/blob/master/src/cdab-client/config.sample.yaml) for the `cdab-client`

## Installation
If Docker SDK is not installed run the following command `pip install docker`, then copy the repository, run the Docker client and the script with the command `python3 automate.py`.

## Configuration
A `config.json` file is provided and has to be placed in the same directory as the script file, the following parameters are available\
* containername: sets the name for the container that will be created
* scenarios: test scenarios to be run, the possible values are "TS01", "TS02", "TS03", "TS04", "TS05", "TS06", "TS07"
* targets: target sites where the test scenarios specified will be run, the possible values are "SciHub", "CREO", "ONDA", "MUNDI", "SOBLOO"
* email: the email registered on [SciHub](https://scihub.copernicus.eu)
* password: the password used for the registration associated with the email on `SciHub`

## Output
The results will be saved as tar files in the current directory with the following naming convention targetsite_scenario.tar and the container will be removed after the execution of the last scenario.