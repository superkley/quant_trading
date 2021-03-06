# Start jupyter

```cmd (with admin rights)
wsl
sudo mkdir -p /mnt/d
sudo mount -t drvfs d: /mnt/d
cd /mnt/d/notebooks && jupyter lab --allow-root --ip=0.0.0.0 --no-browser
```

```
import platform;
print(platform.architecture());
```

# (Optional) Reboot WSL

# CMD (admin)
```cmd
net stop LxssManager
net start LxssManager
```

# Environment setup

```power-shell (with admin rights)
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1804 -OutFile Ubuntu.zip -UseBasicParsing
# Rename-Item ./Ubuntu.appx ./Ubuntu.zip
Expand-Archive ./Ubuntu.zip ~/wsl/Ubuntu-1804-wsl
~/wsl/Ubuntu-1804-wsl/Ubuntu1804.exe
# add ~/wsl/Ubuntu-1804-wsl to PATH
wslconfig /list
``` 

```
sudo apt-get update && apt-get upgrade
sudo apt install build-essential wget -y
sudo apt-get install python3-dev python-pip python-dev python3 python python3-pip nodejs npm graphviz
sudo apt-get install libblas3 liblapack3 liblapack-dev libblas-dev gfortran
sudo apt-get install libatlas-base-dev python-dev gfortran pkg-config libfreetype6-dev
sudo pip install --upgrade pip
sudo pip install --upgrade setuptools
sudo pip install -U cython
sudo pip install -U python-dotenv pandas numpy numba scipy scikit-learn cachetools psutil pyyaml requests python-dateutil statsmodels urllib3 beautifulsoup4 pandas-datareader xlrd python-dotenv munch openpyxl==3.0.1
sudo pip install -U ray
sudo pip install -U xgboost
sudo pip install -U tensorflow
sudo pip install -U findspark  fastparquet brotli pyarrow thrift
sudo pip install -U jupyter jupyterlab importlib seaborn matplotlib jupyter_server_proxy jupyterlab-dash
sudo pip install -U qgrid
sudo pip install -U quandl
sudo pip install -U html5lib
sudo pip install -U bs4
sudo pip install -U yfinance
sudo pip install -U investpy
sudo pip install -U requests_cache
sudo pip install -U mpl_finance
sudo pip install -U --user PyYAML
sudo jupyter labextension install jupyterlab-dash
sudo jupyter labextension install jupyter_server_proxy
sudo jupyter labextension install @jupyter-widgets/jupyterlab-manager
sudo jupyter serverextension enable --py jupyterlab --sys-prefix
sudo jupyter serverextension enable --py jupyter_server_proxy --sys-prefix
sudo jupyter labextension install qgrid
sudo pip install -U cufflinks dash dash-renderer dash-html-components dash-core-components plotly chart-studio dash-daq dash-cytoscape gunicorn dash-bootstrap-components plotly-express
sudo pip install -U joblib deap update_checker tqdm stopit dask[delayed] dask-ml scikit-mdr skrebate tpot
sudo pip install -U blaze sqlalchemy
sudo pip install -U alphalens pyfolio
sudo pip install -U holidays
# deprecated
# sudo pip install empyrical
# requires python 3.5
# sudo pip install zipline
sudo pip install graphviz featuretools
sudo pip install cvxpy pykalman cvxopt stats copulalib statistics
sudo pip install nltk
wget https://artiya4u.keybase.pub/TA-lib/ta-lib-0.4.0-src.tar.gz
tar -xvf ta-lib-0.4.0-src.tar.gz
cd ta-lib/
./configure --prefix=/usr
make
sudo make install
sudo pip install TA-Lib
sudo jupyter labextension install @jupyter-widgets/jupyterlab-manager
jupyter notebook --generate-config
jupyter notebook password
cd /mnt/c/notebooks && jupyter lab --allow-root --ip=0.0.0.0 --no-browser

```


# fix for yahoo finance
pd.core.common.is_list_like = pd.api.types.is_list_like