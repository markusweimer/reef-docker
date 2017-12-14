FROM microsoft/windowsservercore:10.0.14393.1715
SHELL ["powershell.exe", "-ExecutionPolicy", "Bypass", "-Command"]

RUN Invoke-WebRequest "https://aka.ms/vs/15/release/vs_community.exe" -OutFile "$env:TEMP\vs_community.exe" -UseBasicParsing
RUN & "$env:TEMP\vs_community.exe" --add Microsoft.VisualStudio.Workload.NetWeb --quiet --wait --norestart --noUpdateInstaller | Out-Default

RUN & 'C:/Program Files (x86)/Microsoft Visual Studio/2017/Community/MSBuild/15.0/Bin/MSBuild.exe' /version

CMD ["powershell"]