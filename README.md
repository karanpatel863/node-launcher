# Requirements
1. ~300 GB of download bandwidth
2. ~7 GB of disk space (~300 GB if you want the Bitcoin transaction index, makes for a faster LND)
3. Windows or macOS

Please submit a pull request if you want to add Linux support! Next year is the Year of Desktop Linux...


# Install 

Download and open the latest release for your operating system: 
https://github.com/PierreRochard/node-launcher/releases

# Node Launcher

1. Creates a node launcher data directory 
    * macOS: `~/Library/Application Support/Node Launcher/`
    * Windows: `%localappdata%/Node\ Launcher/`
2. Finds available ports for Bitcoin and LND, testnet and mainnet
3. When launched, Bitcoin nodes use the `datadir` directory specified in `bitcoin.conf` (or the default data directory)
4. If you don't have >300 GB of disk space free, Bitcoin nodes will fall back to pruned
5. Pruning still requires downloading data, so make sure you can handle downloading ~300 GB of data

![macos](https://raw.githubusercontent.com/PierreRochard/node-launcher/master/macos.png)

![windows](https://raw.githubusercontent.com/PierreRochard/node-launcher/master/windows.png)

# Development

0. `git clone https://github.com/PierreRochard/node-launcher && cd node-launcher`
1. Setup a Python 3.7+ virtual environment
2. `python -m pip install --index-url=http://download.qt.io/snapshots/ci/pyside/dev/latest pyside2 --trusted-host download.qt.io`
3. `pip install -r requirements.txt`
4. `python setup.py develop`
5. `python run.py`

# Testing

`pytest tests`

To include tests with network calls to GitHub:
`pytest tests --run_slow`


# Packaging

macOS: `pyinstaller run-mac.spec`

Windows: `pyinstaller run-windows.spec` (pyinstaller packaging only works on Windows 7)