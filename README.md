This guide provides **command-line equivalents** (PowerShell & CMD) for each `gpedit.msc` tweak, allowing you to automate changes without opening the GUI.  

---

## **🔧 How to Apply Group Policy Changes via Command Line**  
### **1. Using `reg add` (CMD) for Registry-Based Policies**  
Many Group Policy settings modify the registry. You can apply them directly via:  
```cmd
reg add "HKLM\Software\Policies\Microsoft\Windows\..." /v "SettingName" /t REG_DWORD /d 1 /f
```  

### **2. Using `Set-ItemProperty` (PowerShell)**  
```powershell
Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\..." -Name "SettingName" -Value 1 -Force
```  

### **3. Using `gpupdate /force` to Apply Changes**  
After making changes, run:  
```cmd
gpupdate /force
```  
or in PowerShell:  
```powershell
Invoke-GPUpdate -Force
```  

---

## **🚀 Cool Group Policy Tweaks with Commands**  

### **1. Disable Annoying Windows Features**  
#### **Disable Telemetry (Diagnostic Data)**  
📍 **Registry Path:**  
`HKLM\Software\Policies\Microsoft\Windows\DataCollection`  
- **CMD:**  
  ```cmd
  reg add "HKLM\Software\Policies\Microsoft\Windows\DataCollection" /v "AllowTelemetry" /t REG_DWORD /d 0 /f
  ```  
- **PowerShell:**  
  ```powershell
  Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\DataCollection" -Name "AllowTelemetry" -Value 0 -Force
  ```  

#### **Disable Automatic Windows Updates**  
📍 **Registry Path:**  
`HKLM\Software\Policies\Microsoft\Windows\WindowsUpdate\AU`  
- **CMD:**  
  ```cmd
  reg add "HKLM\Software\Policies\Microsoft\Windows\WindowsUpdate\AU" /v "NoAutoUpdate" /t REG_DWORD /d 1 /f
  ```  
- **PowerShell:**  
  ```powershell
  Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\WindowsUpdate\AU" -Name "NoAutoUpdate" -Value 1 -Force
  ```  

#### **Disable Cortana**  
📍 **Registry Path:**  
`HKLM\Software\Policies\Microsoft\Windows\Windows Search`  
- **CMD:**  
  ```cmd
  reg add "HKLM\Software\Policies\Microsoft\Windows\Windows Search" /v "AllowCortana" /t REG_DWORD /d 0 /f
  ```  
- **PowerShell:**  
  ```powershell
  Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\Windows Search" -Name "AllowCortana" -Value 0 -Force
  ```  

---

### **2. Privacy & Security Tweaks**  
#### **Disable Tailored Experiences (Ads)**  
📍 **Registry Path:**  
`HKLM\Software\Policies\Microsoft\Windows\CloudContent`  
- **CMD:**  
  ```cmd
  reg add "HKLM\Software\Policies\Microsoft\Windows\CloudContent" /v "DisableTailoredExperiencesWithDiagnosticData" /t REG_DWORD /d 1 /f
  ```  
- **PowerShell:**  
  ```powershell
  Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\CloudContent" -Name "DisableTailoredExperiencesWithDiagnosticData" -Value 1 -Force
  ```  

#### **Disable Location Tracking**  
📍 **Registry Path:**  
`HKLM\Software\Policies\Microsoft\Windows\LocationAndSensors`  
- **CMD:**  
  ```cmd
  reg add "HKLM\Software\Policies\Microsoft\Windows\LocationAndSensors" /v "DisableLocation" /t REG_DWORD /d 1 /f
  ```  
- **PowerShell:**  
  ```powershell
  Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\LocationAndSensors" -Name "DisableLocation" -Value 1 -Force
  ```  

---

### **3. Customization Tweaks**  
#### **Disable Lock Screen Ads**  
📍 **Registry Path:**  
`HKLM\Software\Policies\Microsoft\Windows\System`  
- **CMD:**  
  ```cmd
  reg add "HKLM\Software\Policies\Microsoft\Windows\System" /v "DisableLogonBackgroundImage" /t REG_DWORD /d 1 /f
  ```  
- **PowerShell:**  
  ```powershell
  Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\System" -Name "DisableLogonBackgroundImage" -Value 1 -Force
  ```  

#### **Force Dark Mode for Apps**  
📍 **Registry Path:**  
`HKCU\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize`  
- **CMD:**  
  ```cmd
  reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize" /v "AppsUseLightTheme" /t REG_DWORD /d 0 /f
  ```  
- **PowerShell:**  
  ```powershell
  Set-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize" -Name "AppsUseLightTheme" -Value 0 -Force
  ```  

---

### **4. Performance & Startup Tweaks**  
#### **Disable Game Bar & Xbox DVR**  
📍 **Registry Path:**  
`HKLM\Software\Policies\Microsoft\Windows\GameDVR`  
- **CMD:**  
  ```cmd
  reg add "HKLM\Software\Policies\Microsoft\Windows\GameDVR" /v "AllowGameDVR" /t REG_DWORD /d 0 /f
  ```  
- **PowerShell:**  
  ```powershell
  Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\GameDVR" -Name "AllowGameDVR" -Value 0 -Force
  ```  

---

### **5. File Explorer & Taskbar Tweaks**  
#### **Disable Quick Access Recent Files**  
📍 **Registry Path:**  
`HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer`  
- **CMD:**  
  ```cmd
  reg add "HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer" /v "NoRecentDocsHistory" /t REG_DWORD /d 1 /f
  ```  
- **PowerShell:**  
  ```powershell
  Set-ItemProperty -Path "HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer" -Name "NoRecentDocsHistory" -Value 1 -Force
  ```  

---

## **🎉 Final Thoughts**  
Using **CMD (`reg add`)** or **PowerShell (`Set-ItemProperty`)**, you can automate these tweaks for faster deployment.  

### **Want a Batch/PowerShell Script to Apply All at Once?**  
Let me know, and I’ll generate one for you! 🚀  

Would you like additional tweaks or explanations? 😊
