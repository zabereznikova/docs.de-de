---
title: Behandeln von Setup-Problemen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 13f6bd17e1295ea72f25710d7ae5e2803c94aad1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="troubleshooting-setup-issues"></a>Behandeln von Setup-Problemen
In diesem Thema wird beschrieben, wie [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Setupprobleme behoben werden.  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Einige Windows Communication Foundation-Registrierungsschlüssel werden nicht durch Ausführen eines MSI-Reparaturvorgangs in .NET Framework 3.0 repariert  
 Wenn Sie einen der folgenden Registrierungsschlüssel löschen:  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Die Schlüssel werden nicht neu erstellt, wenn Sie eine Reparatur ausführen, mit dem .NET Framework 3.0-Installer aus gestartet der **Programme hinzufügen/entfernen** -Applet in **Systemsteuerung**. Um diese Schlüssel ordnungsgemäß neu zu erstellen, muss der Benutzer .NET Framework 3.0 deinstallieren und anschließend neu installieren.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>WMI Service Corruption blockiert möglicherweise die Installation des Windows Communication Foundation-WMI-Anbieters während der Installation des .NET Framework&#160;3.0-Pakets.  
 WMI Service Corruption blockiert möglicherweise die Installation des Windows Communication Foundation-WMI-Anbieters. Während der Installation kann das Windows Communication Foundation-Installationsprogramm die WCF-.mof-Datei nicht mit der mofcomp.exe-Komponente registrieren. Im Folgenden erhalten Sie eine Liste der Symptome:  
  
1.  Die .NET Framework 3.0-Installation wird erfolgreich abgeschlossen, aber der WCF WMI-Anbieter wird nicht registriert.  
  
2.  Im Anwendungsereignisprotokoll wird ein Fehlerereignis angezeigt, das auf Probleme bei der Registrierung des WMI-Anbieters für WCF oder beim Ausführen von mofcomp.exe verweist.  
  
3.  Die Setupprotokolldatei dd_wcf_retCA* im Benutzerverzeichnis %temp% enthält Verweise auf einen Fehler bei der Registrierung des WCF WMI-Anbieters.  
  
4.  Eine Ausnahme wie die folgende kann im Ereignisprotokoll oder in der Setup-Ablaufverfolgungsprotokolldatei aufgelistet sein:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Unerwartetes Ergebnis 3 beim Ausführen von E:\WINDOWS\system32\wbem\mofcomp.exe mit "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     oder:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: Der Typeninitialisierer für 'System.Management.ManagementPath' hat eine Ausnahme ausgelöst. ---> System.Runtime.InteropServices.COMException (0x80040154): Die COM-Klassenfactory für die Komponente mit CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} konnte aufgrund des folgenden Fehlers nicht abgerufen werden: 80040154.  
  
     oder:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Die Datei oder Assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' oder eine Abhängigkeit davon wurde nicht gefunden. Die angegebene Datei wurde nicht gefunden.  
  
     Dateiname: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Die folgenden Schritten müssen ausgeführt werden, um das zuvor beschriebene Problem zu lösen.  
  
1.  Führen Sie [das Diagnoseprogramm für WMI, Version 2.0](http://go.microsoft.com/fwlink/?LinkId=94685) , den WMI-Dienst zu reparieren. [!INCLUDE[crabout](../../../includes/crabout-md.md)]mit diesem Tool finden Sie unter der [Diagnoseprogramm für WMI](http://go.microsoft.com/fwlink/?LinkId=94686) Thema.  
  
 Reparieren Sie die .NET Framework 3.0-Installation mithilfe der **Programme hinzufügen/entfernen** Applet befindet sich im **Systemsteuerung**, oder deinstallieren/Neuinstallieren von .NET Framework 3.0.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Durch eine Reparatur von .NET Framework&#160;3.0 nach der .NET Framework&#160;3.5-Installation werden Konfigurationselemente entfernt, die von .NET Framework&#160;3.5 in machine.config eingefügt wurden  
 Wenn Sie .NET Framework&#160;3.0 reparieren, nachdem [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installiert wurde, werden Konfigurationselemente entfernt, die von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] in die Datei machine.config eingefügt wurden. Die Datei web.config bleibt jedoch intakt. Die problemumgehung besteht darin zu reparieren [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] hiernach via ARP- oder Verwendung der [Registrierungstool für Workflowdienste (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) mit der `/c` wechseln.  
  
 [Registrierungstool für Workflowdienste (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter %windir%\Microsoft.NET\framework\v3.5\ oder %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Korrektes Konfigurieren von IIS für WCF-/WF-Webhost nach der Installation von .NET Framework&#160;3.5  
 Wenn im Rahmen der [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Installation zusätzliche auf [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bezogene IIS-Konfigurationseinstellungen nicht konfiguriert werden können, wird im Installationsprotokoll ein Fehler protokolliert und dann fortgefahren. Jeder Versuch, WorkflowServices-Anwendungen auszuführen, schlägt fehl, da die erforderlichen Konfigurationseinstellungen fehlen. Zum Beispiel kann das Laden eines XOML- oder RULES-Diensts fehlschlagen.  
  
 Zur Umgehung dieses Problems verwenden die [Registrierungstool für Workflowdienste (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) mit dem `/c` Switch so konfigurieren Sie IIS Skript Zuordnungen ordnungsgemäß auf dem Computer. [Registrierungstool für Workflowdienste (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) finden Sie unter %windir%\Microsoft.NET\framework\v3.5\ oder %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>Der Typ "System.ServiceModel.Activation.HttpModule" in der Assembly "System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" konnte nicht geladen werden.  
 Dieser Fehler tritt auf, wenn [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] installiert ist und die [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-HTTP-Aktivierung aktiviert wird. Um das Problem zu beheben, führen Sie die folgende Befehlszeile in der [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]-Eingabeaufforderung aus:  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Setupanweisungen](../../../docs/framework/wcf/samples/set-up-instructions.md)
