---
title: Behandeln von Setup-Problemen
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 69242ec745f2a5b945ae64eb558070dbf0d39c10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791533"
---
# <a name="troubleshooting-setup-issues"></a>Behandeln von Setup-Problemen
In diesem Thema wird beschrieben, wie Windows Communication Foundation (WCF) richten Sie Probleme behandeln werden.  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Einige Windows Communication Foundation-Registrierungsschlüssel werden nicht durch Ausführen eines MSI-Reparaturvorgangs in .NET Framework 3.0 repariert  
 Wenn Sie einen der folgenden Registrierungsschlüssel löschen:  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Die Schlüssel werden nicht neu erstellt, wenn das Ausführen von Repair, mit dem .NET Framework 3.0-Installationsprogramm aus gestartet der **Programme hinzufügen/entfernen** -Applet in **Systemsteuerung**. Um diese Schlüssel ordnungsgemäß neu zu erstellen, muss der Benutzer .NET Framework 3.0 deinstallieren und anschließend neu installieren.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>WMI Service Corruption blockiert möglicherweise die Installation des Windows Communication Foundation-WMI-Anbieters während der Installation des .NET Framework&amp;#160;3.0-Pakets.  
 WMI Service Corruption blockiert möglicherweise die Installation des Windows Communication Foundation-WMI-Anbieters. Während der Installation kann das Windows Communication Foundation-Installationsprogramm die WCF-.mof-Datei nicht mit der mofcomp.exe-Komponente registrieren. Im Folgenden erhalten Sie eine Liste der Symptome:  
  
1. Die .NET Framework 3.0-Installation wird erfolgreich abgeschlossen, aber der WCF WMI-Anbieter wird nicht registriert.  
  
2. Im Anwendungsereignisprotokoll wird ein Fehlerereignis angezeigt, das auf Probleme bei der Registrierung des WMI-Anbieters für WCF oder beim Ausführen von mofcomp.exe verweist.  
  
3. Die Setupprotokolldatei dd_wcf_retCA* im Benutzerverzeichnis %temp% enthält Verweise auf einen Fehler bei der Registrierung des WCF WMI-Anbieters.  
  
4. Eine Ausnahme wie die folgende kann im Ereignisprotokoll oder in der Setup-Ablaufverfolgungsprotokolldatei aufgelistet sein:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Unerwartetes Ergebnis 3 Ausführen von E:\WINDOWS\system32\wbem\mofcomp.exe mit "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication foundation\servicemodel. MOF"  
  
     oder:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: Die typeninitialisierung für 'System.Management.ManagementPath' hat eine Ausnahme ausgelöst. ---> System.Runtime.InteropServices.COMException (0 x 80040154): Abrufen der COM-Klassenfactory für die Komponente mit CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} konnte aufgrund des folgenden Fehlers: 80040154.  
  
     oder:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Datei oder Assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' oder eine ihrer Abhängigkeiten konnte nicht geladen werden. Die angegebene Datei wurde nicht gefunden.“  
  
     Dateiname: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Die folgenden Schritten müssen ausgeführt werden, um das zuvor beschriebene Problem zu lösen.  
  
1. Führen Sie [Diagnoseprogramm für WMI, Version 2.0](https://go.microsoft.com/fwlink/?LinkId=94685) den WMI-Dienst zu reparieren. Weitere Informationen zur Verwendung dieses Tools finden Sie unter den [WMI-Diagnoseprogramm](https://go.microsoft.com/fwlink/?LinkId=94686) Thema.  
  
 Reparieren Sie die .NET Framework 3.0-Installation mithilfe der **Programme hinzufügen/entfernen** Applet befindet sich in **Systemsteuerung**, oder .NET Framework 3.0 deinstallieren und neu installieren.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Durch eine Reparatur von .NET Framework&amp;#160;3.0 nach der .NET Framework&amp;#160;3.5-Installation werden Konfigurationselemente entfernt, die von .NET Framework&amp;#160;3.5 in machine.config eingefügt wurden  
 Wenn Sie .NET Framework&amp;#160;3.0 reparieren, nachdem [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installiert wurde, werden Konfigurationselemente entfernt, die von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] in die Datei machine.config eingefügt wurden. Die Datei web.config bleibt jedoch intakt. Die problemumgehung besteht darin, reparieren Sie [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] danach über ARP, oder verwenden Sie die [Registrierungstool für Workflowdienste (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) mit der `/c` wechseln.  
  
 [Registrierungstool für Workflowdienste (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter dem Ordner %windir%\Microsoft.NET\framework\v3.5\ oder %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Korrektes Konfigurieren von IIS für WCF-/WF-Webhost nach der Installation von .NET Framework&amp;#160;3.5  
 Wenn [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] Installation schlägt fehl, so konfigurieren Sie zusätzliche WCF-bezogene IIS-Konfigurationseinstellungen, protokolliert einen Fehler im Installationsprotokoll und wird fortgesetzt. Jeder Versuch, WorkflowServices-Anwendungen auszuführen, schlägt fehl, da die erforderlichen Konfigurationseinstellungen fehlen. Zum Beispiel kann das Laden eines XOML- oder RULES-Diensts fehlschlagen.  
  
 Zur Umgehung dieses Problems verwenden die [Registrierungstool für Workflowdienste (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) mit der `/c` wechseln Sie zur IIS-Skriptzuordnungen auf dem Computer ordnungsgemäß zu konfigurieren. [Registrierungstool für Workflowdienste (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter dem Ordner %windir%\Microsoft.NET\framework\v3.5\ oder %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>Der Typ "System.ServiceModel.Activation.HttpModule" in der Assembly "System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" konnte nicht geladen werden.  
 Dieser Fehler tritt auf, wenn [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] installiert ist, und klicken Sie dann die WCF-HTTP-Aktivierung aktiviert ist. So beheben Sie das Problem, führen Sie die folgende Befehlszeile in der Developer-Eingabeaufforderung für Visual Studio  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Siehe auch

- [Setupanweisungen](../../../docs/framework/wcf/samples/set-up-instructions.md)
