---
title: Behandeln von Setup-Problemen
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 326daab1f7df5f8a4ea4f74fd8890031f243f7f5
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291513"
---
# <a name="troubleshooting-setup-issues"></a>Behandeln von Setup-Problemen
In diesem Thema wird beschrieben, wie Probleme beim Einrichten von Windows Communication Foundation (WCF) behoben werden.  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Einige Windows Communication Foundation-Registrierungsschlüssel werden nicht durch Ausführen eines MSI-Reparaturvorgangs in .NET Framework 3.0 repariert  
 Wenn Sie einen der folgenden Registrierungsschlüssel löschen:  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Die Schlüssel werden nicht neu erstellt, wenn Sie die Reparatur mithilfe des Installationsprogramms .NET Framework 3,0 ausführen, das über das Applet **Programme hinzufügen/entfernen** in der **Systemsteuerung**gestartet wurde. Um diese Schlüssel ordnungsgemäß neu zu erstellen, muss der Benutzer .NET Framework 3.0 deinstallieren und anschließend neu installieren.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>WMI Service Corruption blockiert möglicherweise die Installation des Windows Communication Foundation-WMI-Anbieters während der Installation des .NET Framework&#160;3.0-Pakets.  
 WMI Service Corruption blockiert möglicherweise die Installation des Windows Communication Foundation-WMI-Anbieters. Während der Installation kann das Windows Communication Foundation-Installationsprogramm die WCF-.mof-Datei nicht mit der mofcomp.exe-Komponente registrieren. Im Folgenden erhalten Sie eine Liste der Symptome:  
  
1. Die .NET Framework 3.0-Installation wird erfolgreich abgeschlossen, aber der WCF WMI-Anbieter wird nicht registriert.  
  
2. Im Anwendungsereignisprotokoll wird ein Fehlerereignis angezeigt, das auf Probleme bei der Registrierung des WMI-Anbieters für WCF oder beim Ausführen von mofcomp.exe verweist.  
  
3. Die Setupprotokolldatei dd_wcf_retCA* im Benutzerverzeichnis %temp% enthält Verweise auf einen Fehler bei der Registrierung des WCF WMI-Anbieters.  
  
4. Eine Ausnahme wie die folgende kann im Ereignisprotokoll oder in der Setup-Ablaufverfolgungsprotokolldatei aufgelistet sein:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Unerwartetes Ergebnis 3 beim Ausführen von "e:\windows\system32\wbem\mufcomp.exe" mit "e:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof".  
  
     oder:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: Der Typinitialisierer für ' System. Management. ManagementPath ' hat eine Ausnahme ausgelöst. ---> System. Runtime. InteropServices. COMException (0x80040154): Fehler beim Abrufen der COM-Klassenfactory für die Komponente mit der CLSID "{CF4CC405-E2C5-4ddd-B3CE-5E7582D8C9FA}" aufgrund des folgenden Fehlers: 80040154.  
  
     oder:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Die Datei oder Assembly "c:\windows\system32\wbem\muscomp.exe" oder eine ihrer Abhängigkeiten konnte nicht geladen werden. Die angegebene Datei wurde nicht gefunden.“  
  
     Dateiname: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Die folgenden Schritten müssen ausgeführt werden, um das zuvor beschriebene Problem zu lösen.  
  
1. Führen Sie [den WMI-Diagnosehilfsprogramm, Version 2,0, aus,](https://go.microsoft.com/fwlink/?LinkId=94685) um den WMI-Dienst zu reparieren. Weitere Informationen zur Verwendung dieses Tools finden Sie im [WMI-Diagnosehilfsprogramm](https://go.microsoft.com/fwlink/?LinkId=94686) Thema.  
  
 Reparieren Sie die Installation des .NET Framework 3,0 mithilfe des Applets " **Programme hinzufügen/entfernen** " in der **Systemsteuerung**, oder deinstallieren Sie die .NET Framework 3,0, und installieren Sie Sie erneut.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Durch eine Reparatur von .NET Framework&#160;3.0 nach der .NET Framework&#160;3.5-Installation werden Konfigurationselemente entfernt, die von .NET Framework&#160;3.5 in machine.config eingefügt wurden  
 Wenn Sie .NET Framework&#160;3.0 reparieren, nachdem [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installiert wurde, werden Konfigurationselemente entfernt, die von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] in die Datei machine.config eingefügt wurden. Die Datei web.config bleibt jedoch intakt. Die Problem Umgehung besteht darin, [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] nach diesem über ARP zu reparieren oder das Tool für die [Workflow Dienst Registrierung (WFServicesReg. exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) mit dem Schalter `/c` zu verwenden.  
  
 Das Tool für die [Workflow Dienst Registrierung (WFServicesReg. exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter%windir%\Microsoft.NET\Framework\v3.5\ oder%windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Korrektes Konfigurieren von IIS für WCF-/WF-Webhost nach der Installation von .NET Framework&#160;3.5  
 Wenn bei der Installation von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] keine zusätzlichen WCF-bezogenen IIS-Konfigurationseinstellungen konfiguriert werden, wird ein Fehler im Installationsprotokoll protokolliert, und der Vorgang wird fortgesetzt. Jeder Versuch, WorkflowServices-Anwendungen auszuführen, schlägt fehl, da die erforderlichen Konfigurationseinstellungen fehlen. Zum Beispiel kann das Laden eines XOML- oder RULES-Diensts fehlschlagen.  
  
 Um dieses Problem zu umgehen, verwenden Sie das Tool für die [Workflow Dienst Registrierung (WFServicesReg. exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) mit dem Schalter `/c`, um IIS-Skript Zuordnungen auf dem Computer ordnungsgemäß zu konfigurieren. Das Tool für die [Workflow Dienst Registrierung (WFServicesReg. exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter%windir%\Microsoft.NET\Framework\v3.5\ oder%windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>Der Typ "System.ServiceModel.Activation.HttpModule" in der Assembly "System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" konnte nicht geladen werden.  
 Dieser Fehler tritt auf, wenn [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] installiert ist und die WCF-HTTP-Aktivierung aktiviert ist. Um das Problem zu beheben, führen Sie die folgende Befehlszeile in der Developer-Eingabeaufforderung für Visual Studio aus:  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Siehe auch

- [Setupanweisungen](../../../docs/framework/wcf/samples/set-up-instructions.md)
