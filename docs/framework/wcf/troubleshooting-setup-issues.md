---
title: Behandeln von Setup-Problemen
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 2cd9ced4f0780b1a6f63e4a5833e20ac91870121
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121579"
---
# <a name="troubleshoot-setup-issues"></a>Beheben von Setup-Problemen

In diesem Artikel wird beschrieben, wie Sie Probleme bei der Einrichtung von Windows Communication Foundation (WCF) beheben können.  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Einige Windows Communication Foundation-Registrierungsschlüssel werden nicht durch Ausführen eines MSI-Reparaturvorgangs in .NET Framework 3.0 repariert  
 Wenn Sie einen der folgenden Registrierungsschlüssel löschen:  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Die Schlüssel werden nicht neu erstellt, wenn Sie die Reparatur mithilfe des Installationsprogramms .NET Framework 3.0 ausführen, das vom Applet **"Programme hinzufügen/Entfernen"** in der **Systemsteuerung**gestartet wurde. Um diese Schlüssel ordnungsgemäß neu zu erstellen, muss der Benutzer .NET Framework 3.0 deinstallieren und anschließend neu installieren.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>WMI Service Corruption blockiert möglicherweise die Installation des Windows Communication Foundation-WMI-Anbieters während der Installation des .NET Framework&#160;3.0-Pakets.  
 WMI Service Corruption blockiert möglicherweise die Installation des Windows Communication Foundation-WMI-Anbieters. Während der Installation kann das Windows Communication Foundation-Installationsprogramm die WCF-.mof-Datei nicht mit der mofcomp.exe-Komponente registrieren. Im Folgenden erhalten Sie eine Liste der Symptome:  
  
1. Die .NET Framework 3.0-Installation wird erfolgreich abgeschlossen, aber der WCF WMI-Anbieter wird nicht registriert.  
  
2. Im Anwendungsereignisprotokoll wird ein Fehlerereignis angezeigt, das auf Probleme bei der Registrierung des WMI-Anbieters für WCF oder beim Ausführen von mofcomp.exe verweist.  
  
3. Die Setupprotokolldatei dd_wcf_retCA* im Benutzerverzeichnis %temp% enthält Verweise auf einen Fehler bei der Registrierung des WCF WMI-Anbieters.  
  
4. Eine Ausnahme wie die folgende kann im Ereignisprotokoll oder in der Setup-Ablaufverfolgungsprotokolldatei aufgelistet sein:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Unerwartetes Ergebnis 3 beim Ausführen von E:\WINDOWS\system32\wbem\mofcomp.exe mit "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     oder:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: Der Typeninitialisierer für 'System.Management.ManagementPath' hat eine Ausnahme ausgelöst. ---> System.Runtime.InteropServices.COMException (0x80040154): Beim Abrufen der COM-Klassenfactory für Komponenten mit CLSID-CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA- fehlert aufgrund des folgenden Fehlers: 80040154.  
  
     oder:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Die Datei oder Assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' oder eine Abhängigkeit davon wurde nicht gefunden. Die angegebene Datei wurde nicht gefunden.  
  
     Dateiname: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Die folgenden Schritten müssen ausgeführt werden, um das zuvor beschriebene Problem zu lösen.  
  
1. Führen Sie das [WMI-Diagnoseprogramm](https://www.microsoft.com/download/details.aspx?id=7684) aus, um den WMI-Dienst zu reparieren. Weitere Informationen zur Verwendung dieses Tools finden Sie unter [WMI Diagnosis Utility](https://docs.microsoft.com/previous-versions/tn-archive/ff404265(v%3dmsdn.10)).  
  
 Reparieren Sie die Installation von .NET Framework 3.0 mithilfe des **Applets "Programme hinzufügen/entfernen"** in **der Systemsteuerung,** oder deinstallieren/neu installieren.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Durch eine Reparatur von .NET Framework&#160;3.0 nach der .NET Framework&#160;3.5-Installation werden Konfigurationselemente entfernt, die von .NET Framework&#160;3.5 in machine.config eingefügt wurden  
 Wenn Sie .NET Framework 3.0 nach der Installation von .NET Framework 3.5 reparieren, werden die von .NET Framework 3.5 in machine.config eingeführten Konfigurationselemente entfernt. Die Datei web.config bleibt jedoch intakt. Die Problemumgehung besteht darin, .NET Framework 3.5 danach über ARP zu reparieren oder das [WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) mit dem `/c` Switch zu verwenden.  
  
 [Das WorkFlow-Dienstregistrierungstool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter %windir%-Microsoft.NET-Framework-v3.5- oder %-Windir%-Microsoft.NET-Framework64-V3.5-Datei.  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Korrektes Konfigurieren von IIS für WCF-/WF-Webhost nach der Installation von .NET Framework&#160;3.5  
 Wenn die Installation von .NET Framework 3.5 keine zusätzlichen WCF-bezogenen IIS-Konfigurationseinstellungen konfiguriert, wird ein Fehler im Installationsprotokoll protokolliert und fortgesetzt. Jeder Versuch, WorkflowServices-Anwendungen auszuführen, schlägt fehl, da die erforderlichen Konfigurationseinstellungen fehlen. Zum Beispiel kann das Laden eines XOML- oder RULES-Diensts fehlschlagen.  
  
 Um dieses Problem zu umgehen, verwenden Sie das [WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) mit dem `/c` Switch, um IIS-Skriptzuordnungen auf dem Computer ordnungsgemäß zu konfigurieren. [Das WorkFlow-Dienstregistrierungstool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter %windir%-Microsoft.NET-Framework-v3.5- oder %-Windir%-Microsoft.NET-Framework64-V3.5-Datei.  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>Typ 'System.ServiceModel.Activation.HttpModule' konnte nicht aus der Assembly 'System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' geladen werden.  
 Dieser Fehler tritt auf, wenn .NET Framework 4 installiert ist und dann die WCF-HTTP-Aktivierung aktiviert ist. Um das Problem zu beheben, führen Sie die folgende Befehlszeile innerhalb der Developer-Eingabeaufforderung für Visual Studio aus:  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Siehe auch

- [Setupanweisungen](./samples/set-up-instructions.md)
