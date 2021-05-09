# Hunt Tips:
* Post operations w/low "RequestCount"
  * Note: Case sensitive so possible capitilization duplicates.  
* URIs that do not require auuthentication 
  * Note: They want access anytime to their webshell!  
* "GET" operations w/HTTP Status 404
* UserAgent string outliar
  * Note: Some webshells require specific UserAgent strings
* ClientID of attacker
  * Note: Identify accounts/systems needing remediation as ClientID should persist.

# Relevant CMDs:
## 0.) Log Locations:
```powershell
#Find all Exchange (2010-2016) Servers w/Client Access Server Role
Get-ExecutionServer | Where {$_.IsClientAccessServer -eq $True}

#Find where the IIS logs are stores
[adsi]"IIS://localhost/w3svc" | select LogFileDirectory | %{$_.LogFileDirectory}
```

# YouTube:
* [Hunting Webshells: Tracking TwoFace - SANS Threat Hunting Summit 2018](https://www.youtube.com/watch?v=GjquFKa4afU)

# Twitter:
* [Robert Falcone](https://twitter.com/r0bf4lc?lang=en)
* [Josh M. Bryant](https://twitter.com/fixtheexchange?lang=en)

# Other Resources:
* [Log Parser 2.2](https://www.microsoft.com/en-us/download/details.aspx?id=24659)
* [Invoke-ExchangeWebShellHunter](https://github.com/FixTheExchange/Invoke-ExchangeWebShellHunter)
  * Note: Josh Bryant's Github above! Other good forensic goodies located here.
