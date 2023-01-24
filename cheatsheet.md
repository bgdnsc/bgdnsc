# Cheatsheet & reinstall script :)

I'm lazy and I like my comfort zone! <br>
My goal is to have a script that I can run on a new machine and have everything setup and ready to go. <br>

## Install Chocolatey

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

## Installing Terraform

Install Terraform & define aliases for shortcuts: `TF` and `TFF`. <br>
`TF` is just a shortner, because i'm lazy. <br>
`TFF` is used to format the code. <br>

```powershell
choco install terraform
```

## Installing the functions to each PS session

```powershell
notepad $PROFILE.CurrentUserAllHosts
```

In the freshly opened notepad, dump the following code:

```powershell
New-Alias -Name "tf" -Value "terraform"
function New-CWTerraformFormat { tf fmt -recursive }
New-Alias -Name "tff" -Value New-CWTerraformFormat

```
