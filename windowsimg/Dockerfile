FROM windowsimg/apache24:latest

LABEL Description="Python" Vendor="Python Software Foundation" Version="3.10.0"

RUN powershell.exe -Command \
    $ErrorActionPreference = 'Stop'; \
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; \
    wget https://www.python.org/ftp/python/3.10.0/python-3.10.0.exe -OutFile c:\python-3.10.0.exe ; \
    Start-Process c:\python-3.10.0.exe -ArgumentList '/quiet InstallAllUsers=1 PrependPath=1' -Wait ; \
    Remove-Item c:\python-3.10.0.exe -Force

RUN ["pip", "install", "Django==3.2.9"]

CMD ["django-admin --version"]
