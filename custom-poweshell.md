## Powershell set-up

`
`Open the Powershell as ADMINISTRATOR `

```bash
Test-path $PROFILE
```

```bash
New-Item -Path $PROFILE -Type File -Force 
```

`Open Notepad :`

```bash
notepad $PROFILE 
```

`Enter the following details in the notepad file :`

```bash
function prompt {
    $path = $(Get-Location).Path
    $path = $path.ToLower() -replace '^([a-z]):', '/$1' -replace '\\', '/'
    Write-Host ""
    Write-Host $path -ForegroundColor Green
    Write-Host "> " -NoNewline -ForegroundColor Green
}
```

```bash
.$PROFILE
#If You get an error then use :
Set-ExecutionPolicy RemoteSigned 
```
