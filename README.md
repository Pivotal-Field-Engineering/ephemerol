# ephemerol
A Cloud Native readiness scanner that has configurable rules for Java, .NET and other cloud native application types.
[![Build Status](https://travis-ci.org/Pivotal-Field-Engineering/ephemerol.png?branch=master)](https://travis-ci.org/Pivotal-Field-Engineering/ephemerol)

Currently, ephemerol scans project source files in a zip file for the following languages:
* [Java](docs/Java.MD)
* [.NET Framework (not .NET Core)](docs/DotNet.MD)

## Requirements
Python 2.7.9

## Command Line
First grab all the dependencies:
```
pip install -r requirements.txt
```
Then you can run the following to get information on how to invoke the scanner from the command line:
```
python -m ephemerol -h
```

## Development
### Run Web Application Locally
Run the script as follows to get information on how to invoke it:
```
pip install -r requirements.txt
python ./ephemerol/ephemerol-web.py
```

### Testing
To run tests, make sure to install dependencies, then you can run all the tests with the `py.test` command at the root of the project.
```
pip install -r requirements.txt
# Then one of the following
py.test
# or
python -m pytest
```

## Deploy to Cloud Foundry
```
cd ephemerol #folder from git clone
mkdir ./ephemerol/vendor
pip --trusted-host pypi.org --trusted-host files.pythonhosted.org download --no-binary :all -d ./ephemerol/vendor -r requirements.txt
cf push
```

## Screenshots
![home page](screenshots/home.png)
![report page](screenshots/report.png)

## GUI Development
* The project is now React based, which means you will need node.js and NPM to modify the UI.
* Install npm and node.js - https://www.npmjs.com/get-npm
* No need for Bower or Gulp or other nonsense thanks to - https://github.com/facebookincubator/create-react-app

### Live Code Edit Front End
```
cd ./ephemerol/ephemoral-react
npm install
npm start
```

### Generate/Deploy optimized production GUI
* Generate production optimized react files for web server
* Deploy react files to static directory
```
npm run build
npm run deploy
```

### Delete existing flask "static" files directory (OPTIONAL)
```
npm run clean
```

## Project Core Team
#### [Chris Delashmutt/Pivotal - Project Lead](https://github.com/cdelashmutt-pivotal)
#### [James Williams/Pivotal - Committer](https://github.com/jwilliams-pivotal)

## Project Contributors
#### [John Feminella/Pivotal](https://github.com/fj)
Early adopter. Suggested we move to open source the project.

#### Dieter Flick/Pivotal
Early adopter. Provided excellent feedback on the cloud readiness index scoring algorithm.

#### [Matt Cowger/EMC](https://github.com/mcowger)
Requested that we remove pandas to reduce dependency overhead. This was an excellent idea.

