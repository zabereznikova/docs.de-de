---
title: Behandeln von Setup-Problemen
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: fb687e9975ab9ac763030f10d54c7744dc02c9e0
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720451"
---
# <a name="troubleshoot-setup-issues"></a>Beheben von Setup-Problemen

In diesem Artikel wird beschrieben, wie Sie Probleme bei der Windows Communication Foundation (WCF) beheben.  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Einige Windows Communication Foundation-Registrierungsschlüssel werden nicht durch Ausführen eines MSI-Reparaturvorgangs in .NET Framework 3.0 repariert  
 Wenn Sie einen der folgenden Registrierungsschlüssel löschen:  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Die Schlüssel werden nicht neu erstellt, wenn Sie die Reparatur mithilfe des Installationsprogramms .NET Framework 3,0 ausführen, das über das Applet **Programme hinzufügen/entfernen** in der **Systemsteuerung**gestartet wurde. Um diese Schlüssel ordnungsgemäß neu zu erstellen, muss der Benutzer .NET Framework 3.0 deinstallieren und anschließend neu installieren.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-wmi-provider"></a>WMI-Dienst Beschädigung blockiert die Installation des WMI-Anbieters

 WMI-Dienst Beschädigung blockiert möglicherweise die Installation des Windows Communication Foundation WMI-Anbieters bei der Installation des Pakets .NET Framework 3,0. Während der Installation kann der Windows Communication Foundation Installer die Datei "WCF *. MOF* " nicht mithilfe der *mofcomp.exe* Komponente registrieren. Im Folgenden erhalten Sie eine Liste der Symptome:  
  
1. Die .NET Framework 3.0-Installation wird erfolgreich abgeschlossen, aber der WCF WMI-Anbieter wird nicht registriert.  
  
2. Im Anwendungsereignisprotokoll wird ein Fehlerereignis angezeigt, das auf Probleme bei der Registrierung des WMI-Anbieters für WCF oder beim Ausführen von mofcomp.exe verweist.  
  
3. Die Setupprotokolldatei dd_wcf_retCA* im Benutzerverzeichnis %temp% enthält Verweise auf einen Fehler bei der Registrierung des WCF WMI-Anbieters.  
  
4. Eine Ausnahme wie die folgende kann im Ereignisprotokoll oder in der Setup-Ablaufverfolgungsprotokolldatei aufgelistet sein:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Unerwartetes Ergebnis 3 beim Ausführen von E:\WINDOWS\system32\wbem\mofcomp.exe mit "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     oder:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: Der Typeninitialisierer für 'System.Management.ManagementPath' hat eine Ausnahme ausgelöst. ---> System. Runtime. InteropServices. COMException (0x80040154): die COM-Klassenfactory für die Komponente mit CLSID {CF4CC405-E2C5-4ddd-B3CE-5E7582D8C9FA} konnte aufgrund des folgenden Fehlers nicht abgerufen werden: 80040154.  
  
     oder:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Die Datei oder Assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' oder eine Abhängigkeit davon wurde nicht gefunden. Die angegebene Datei wurde nicht gefunden.  
  
     Dateiname: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Die folgenden Schritten müssen ausgeführt werden, um das zuvor beschriebene Problem zu lösen.  
  
1. Führen Sie den WMI-Diagnosehilfsprogramm aus, um den WMI-Dienst zu reparieren. Weitere Informationen zur Verwendung dieses Tools finden Sie unter [WMI-Diagnosehilfsprogramm](/previous-versions/tn-archive/ff404265(v%3dmsdn.10)).  
  
 Reparieren Sie die Installation des .NET Framework 3,0 mithilfe des Applets " **Programme hinzufügen/entfernen** " in der **Systemsteuerung**, oder deinstallieren Sie die .NET Framework 3,0, und installieren Sie Sie erneut.  
  
## <a name="repair-net-framework-30-after-net-framework-35-installation"></a>Reparieren von .NET Framework 3,0 nach .NET Framework 3,5-Installation

 Wenn Sie nach der Installation .NET Framework 3,5 eine Reparatur von .NET Framework 3,0 ausführen, werden die von .NET Framework 3,5 in *machine.config* eingeführten Konfigurationselemente entfernt. Die *web.config* Datei bleibt jedoch intakt. Die Problem Umgehung besteht darin, .NET Framework 3,5 nach diesem über ARP zu reparieren oder das Tool für die [Workflow Dienst Registrierung (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) mit dem Switch zu verwenden `/c` .  
  
 Das Tool für die [Workflow Dienst Registrierung (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter%windir%\Microsoft.NET\Framework\v3.5\ oder%windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Korrektes Konfigurieren von IIS für WCF-/WF-Webhost nach der Installation von .NET Framework&#160;3.5  
 Wenn bei .NET Framework 3,5-Installation keine zusätzlichen WCF-bezogenen IIS-Konfigurationseinstellungen konfiguriert werden können, wird im Installationsprotokoll ein Fehler protokolliert und der Vorgang fortgesetzt. Jeder Versuch, WorkflowServices-Anwendungen auszuführen, schlägt fehl, da die erforderlichen Konfigurationseinstellungen fehlen. Zum Beispiel kann das Laden eines XOML- oder RULES-Diensts fehlschlagen.  
  
 Um dieses Problem zu umgehen, verwenden Sie das [Workflow Service Registration-Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) mit dem- `/c` Schalter, um IIS-Skript Zuordnungen auf dem Computer ordnungsgemäß zu konfigurieren. Das Tool für die [Workflow Dienst Registrierung (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter%windir%\Microsoft.NET\Framework\v3.5\ oder%windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule"></a>Der Typ "System. Service Model. Activation. HttpModule" konnte nicht geladen werden.

**Der Typ "System. Service Model. Activation. HttpModule" konnte nicht aus der Assembly "System. Service Model, Version 3.0.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089" geladen werden.**

 Dieser Fehler tritt auf, wenn .NET Framework 4 installiert ist und die WCF-HTTP-Aktivierung aktiviert ist. Um das Problem zu beheben, führen Sie den folgenden Befehl in der Developer-Eingabeaufforderung für Visual Studio aus:  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Setupanweisungen](./samples/set-up-instructions.md)
