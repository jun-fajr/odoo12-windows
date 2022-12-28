# Odoo 12.0 Windows Installation
Install odoo-12.0 from source on Windows
https://github.com/odoo/odoo/tree/10.0

It is recommended to have 64 bit version of operating system installed on your system.<br />
It is recommended to install 64 bit version of all software packages mentioned in installation process.<br />
It is recommended to install Python 3.6 or 3.7<br />

### Installation<br />
Download and install [Git for Windows](https://git-scm.com/download/win).<br />
Download and install [Node.js LTS](https://nodejs.org/en/download/).<br />
<br />
Launch `Command Prompt` as Administrator.
 * Install `Less.js` by `> npm install -g less less-plugin-clean-css`

Download and install [PostgreSQL](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads).<br />
add PostgreSQL's `bin` directory (default: `C:\Program Files\PostgreSQL\x.x\bin`) to your `PATH`.<br />
<br />
create a `postgres` user with a password using the `PgAdmin` GUI:<br />
 * open `PgAdmin4`,
 * expand `server` node to create a connection,
 * expand `PostgreSQL` node,
 * select **Object-> Create -> Login/Group Role**,
    * enter the username in the `Role Name` field (e.g. odoo12),
    * open the `Definition` tab and enter the password (e.g. odoo12),
    * open the `Privileges` tab and give `login` and `create database` rights,
 * click `save`.

Download and install [`Microsoft Visual C++ 2015 Redistributable`](https://www.microsoft.com/en-us/download/details.aspx?id=52685).<br />
Download and install <a href="https://www.python.org/downloads/" target="_blank">Python3</a> `version 3.6`.<br />
 * goto `Python3` installation directory (default: `C:\Users\{UserName}\AppData\Local\Programs\Python\PythonXX`.<br />
 * rename `python.exe` to `python3.exe` and `pythonw.exe` to `pythonw3.exe`.<br />
 * add `Python3` installation directory (default: `C:\Users\{UserName}\AppData\Local\Programs\Python\PythonXX`) to your `PATH`.<br />

Some of `odoo` dependencies are `non-pure Python packages` which requires `C/C++` compilation during their installation process. you can install those dependencies using one of the following approaches.
 1. Download and install already compiled dependencies in `Wheel (.whl)` format targeting your system configuration.
 2. Download and install `C/C++` compiler than install those dependencies from `source`.


If you're having `32 bit Windows architecture` or other `Python` versions (e.g. `3.4`, `3.5`) installed on your system. you can download `non-pure Python package Wheels (.whl)` targeting your system configurations from [`PyPI`](https://pypi.python.org/pypi) or [`Laboratory for Fluorescence Dynamics`](http://www.lfd.uci.edu/~gohlke/pythonlibs/). If you're having `Python 3.4` installed on system then you will require [`Microsoft Visual C++ 2010 Redistributable`](http://www.microsoft.com/download/en/details.aspx?id=26999) instead of `Microsoft Visual C++ 2015 Redistributable`. for more information visit [`WindowsCompilers`](https://wiki.python.org/moin/WindowsCompilers) article on `Python Wiki`.

For installing dependencies from `source`, download [`Visual C++ 2015 Build Tools`](http://landinghub.visualstudio.com/visual-cpp-build-tools).<br />
 * run the installer,
 * select `custom` mode for installation,
 * uncheck all optional features (e.g. `Windows 8.1 SDK`, `Windows 10 SDK`, `ATL/MFC SDK`, `.NET Framework SDK` etc.)
 * click `Install`.<br />

After `Visual C++ 2015 Build Tools` installation process completes, launch `Command Prompt` as Administrator
 * Install `pypiwin32` by `> python3 -m pip install pypiwin32`
 * Install `Pillow` by `> python3 -m pip install pillow`
 * Install `gevent` by `> python3 -m pip install gevent`
 * Install `lxml` by `> python3 -m pip install lxml`
 * Install `psutil` by `> python3 -m pip install psutil`
 * Install `psycopg2` by `> python3 -m pip install psycopg2`
 * Install `pyldap` by `> python3 -m pip install pyldap`
 * Install `reportlab` by `> python3 -m pip install reportlab`

If you're having `Python 3.4` installed on system then you will require [`Microsoft Windows SDK for Windows 7 and .NET Framework 4`](https://www.microsoft.com/en-us/download/details.aspx?id=8279) instead of `Visual C++ 2015 Build Tools`. for more information visit [`WindowsCompilers`](https://wiki.python.org/moin/WindowsCompilers) article on `Python Wiki`.

Install remaining `pure Python packages` from [`requirements.txt`] using
 * `$ python3 -m  pip install -r requirements.txt`
 * `$ python3 -m pip install -U werkzeug`

Download and install [wkhtmltopdf](https://wkhtmltopdf.org/downloads.html).<br />
Add wkhtmltopdf's `bin` directory (default: `C:\Program Files\wkhtmltopdf\bin`) to your `PATH`.<br />
<br />
Launch `Command Prompt`.<br />
Switch to (`cd`) your desired `odoo` installation directory<br />
clone `odoo` repository by `git clone https://github.com/odoo/odoo.git -b 12.0`<br />

Switch to `odoo` installation directory and run `odoo` using<br />
`$ python3 odoo-bin --addons-path=addons,custom-addons -r odoo12 -w odoo12 --xmlrpc-port=8012`<br />

<img src="https://user-images.githubusercontent.com/13750681/108304244-2c00ef00-71da-11eb-873b-4f3fe41f0cf3.png" />
