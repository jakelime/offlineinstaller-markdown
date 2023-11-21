# offlineinstaller-markdown

offline installer for critical python packages

Built for `win10` or `win11`

## Instructions

1. Create requirements using `venv`

   ```powershell
   python -m venv venv
   .\venv\Scripts\activate
   pip install --no-index --find-links .\downloadedfiles-pip -r reqpip.txt
   python.exe -m pip install --upgrade pip
   pip install .. .. ..
   pip freeze > requirements.txt # might generate some weird paths
   pip list --format=freeze > requirements.txt
   ```

1. Download as offline packages

   ```powershell
   pip download -r requirements.txt
   pip download -d .\downloadedfiles -r requirements.txt
   ```

1. On the offline system, use `pip install --no-index --find-links /path/to/download/dir/ -r requirements.txt`

   ```powershell
   git clone https://github.com/jakelime/offlineinstaller-markdown.git
   cd offlineinstaller-markdown
   pip install --no-index --find-links .\downloadedfiles -r requirements.txt
   pip install --no-index --find-links . -r requirements.txt
   ```
