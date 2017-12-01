---
title: "Überwachung von Anwendungsdomänenressourcen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62a514f94857044af5020d36a1cfd6ce06741ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="application-domain-resource-monitoring"></a>Überwachung von Anwendungsdomänenressourcen
Von Anwendungsdomänenressourcen (ARM) überwachen kann Hosts CPU- und speicherauslastung pro Anwendungsdomäne überwachen. Dies ist nützlich für Hosts wie z. B. ASP.NET, die viele Anwendungsdomänen in einem langer Prozess verwenden. Der Host kann einer Anwendung die Anwendungsdomäne entladen, von denen sich negativ auf die Leistung des gesamten Prozesses, jedoch nur betroffen ist, wenn die problematische Anwendung identifiziert werden kann. ARM-Informationen, die verwendet werden können, um solche Entscheidungen zu unterstützen.  
  
 Z. B. möglicherweise einem Hostingdienst vieler Anwendungen unter ASP.NET-Servern. Wenn eine Anwendung im Prozess zu viel Arbeitsspeicher oder zu viel Prozessorzeit nutzen beginnt, können des Hostingdiensts ARM um die Anwendungsdomäne zu identifizieren, die das Problem verursacht.  
  
 ARM ist ausreichend einfache in live-Anwendungen verwendet. Sie können die Informationen zugreifen, mithilfe von ereignisablaufverfolgung für Windows (ETW) oder direkt über verwalteten oder systemeigenen APIs.  
  
## <a name="enabling-resource-monitoring"></a>Aktivieren der Überwachung der Ressource  
 ARM kann auf vier Arten aktiviert werden: durch eine Konfigurationsdatei anzugeben, wenn die common Language Runtime (CLR) gestartet wird, mithilfe einer nicht verwalteten hosting-API mit verwaltetem Code oder durch das Überwachen von ARM-ETW-Ereignissen.  
  
 Sobald ARM aktiviert ist, beginnt das Sammeln von Daten für alle Anwendungsdomänen im Prozess. Wenn eine Anwendungsdomäne erstellt wurde, bevor die ARM aktiviert ist, beginnt kumulierte Daten ARM aktiviert ist, nicht verwendet werden, wenn die Anwendungsdomäne erstellt wurde. Sobald er aktiviert ist, kann die ARM nicht deaktiviert werden.  
  
-   Kann ARM an CLR-Starts durch Hinzufügen der [ \<AppDomainResourceMonitoring >](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) Element auf die Konfigurationsdatei und das Festlegen der `enabled` -Attribut `true`. Der Wert `false` (Standard) bedeutet lediglich, dass ARM beim Start nicht aktiviert ist, können später mithilfe einer der anderen Mechanismen, die Aktivierung aktivieren.  
  
-   Der Host kann ARM aktivieren, indem er die [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) Hostingschnittstelle. Sobald diese Schnittstelle erfolgreich abgerufen wird, wird die ARM aktiviert.  
  
-   Verwalteter Code kann durch Festlegen der statischen ARM aktivieren (`Shared` in Visual Basic) <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> Eigenschaft `true`. Sobald die Eigenschaft festgelegt ist, wird ARM aktiviert.  
  
-   Überwachen von ETW-Ereignissen, um ARM nach dem Start zu aktivieren. ARM wird aktiviert und startet das Auslösen von Ereignissen für alle Anwendungsdomänen, wenn Sie den öffentlichen Anbieter aktivieren `Microsoft-Windows-DotNETRuntime` mithilfe der `AppDomainResourceManagementKeyword` Schlüsselwort. Sie müssen auch aktivieren, um Daten mit Anwendungsdomänen und Threads zu korrelieren, die `Microsoft-Windows-DotNETRuntimeRundown` Anbieter mit der `ThreadingKeyword` Schlüsselwort.  
  
## <a name="using-arm"></a>Verwenden ARM  
 ARM bietet die gesamte Prozessorzeit, die von einer Anwendungsdomäne und drei Arten von Informationen zur Speicherverwendung verwendet wird.  
  
-   **Gesamtprozessorzeit für eine Anwendungsdomäne, in Sekunden**: Dies wird durch Addieren der Threadzeiten, die vom Betriebssystem für alle Threads, die für die Ausführungszeit in der Anwendungsdomäne während seiner Lebensdauer gemeldet berechnet. Blockiert, oder verwenden Sie Threads im Ruhezustand nicht Prozessorzeit. Wenn ein Thread in systemeigenen Code aufruft, ist die Zeit des Threads in systemeigenem Code an, die in der Anzahl der für die Anwendungsdomäne enthalten, in dem der Aufruf erfolgte.  
  
    -   Verwaltete API: <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> Eigenschaft.  
  
    -   Hosting-API: [ICLRAppDomainResourceMonitor:: GetCurrentCpuTime](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md) Methode.  
  
    -   ETW-Ereignisse: `ThreadCreated`, `ThreadAppDomainEnter`, und `ThreadTerminated` Ereignisse. Informationen über Anbieter und Schlüsselwörter finden Sie unter "Überwachen von Ereignissen für Ressource" im [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md).  
  
-   **Insgesamt verwaltete Zuordnungen, die durch eine Anwendungsdomäne während seiner Lebensdauer in Byte vorgenommen**: gesamte speicherbelegungen immer spiegeln nicht arbeitsspeicherverwendung durch eine Anwendungsdomäne, da die zugeordneten Objekte kurzlebige sein könnten. Wenn eine Anwendung belegt und gibt die große Anzahl von Objekten frei, konnte die Kosten für die Zuordnung jedoch erheblich sein.  
  
    -   Verwaltete API: <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.  
  
    -   Hosting-API: [ICLRAppDomainResourceMonitor:: GetCurrentAllocated](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md) Methode.  
  
    -   ETW-Ereignisse: `AppDomainMemAllocated` Ereignis `Allocated` Feld.  
  
-   **Verwalteter Speicher in Bytes, auf das durch eine Anwendungsdomäne verwiesen wird und der nach der letzten vollständigen blockierenden Auflistung**: Dieser Wert ist genau nur nach einer vollständigen blockierenden Auflistung. (Dies ist im Gegensatz zur gleichzeitigen Garbage Collections, die im Hintergrund ausgeführt und die Anwendung nicht blockieren.) Z. B. die <xref:System.GC.Collect?displayProperty=nameWithType> methodenüberladung bewirkt, dass eine vollständige blockierende Garbage Collection.  
  
    -   Verwaltete API: <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.  
  
    -   Hosting-API: [ICLRAppDomainResourceMonitor:: GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) Methode `pAppDomainBytesSurvived` Parameter.  
  
    -   ETW-Ereignisse: `AppDomainMemSurvived` Ereignis `Survived` Feld.  
  
-   **Gesamtanzahl der verwalteten Speicher in Bytes, die vom Prozess verwiesen wird und der nach der letzten vollständigen blockierenden Auflistung**: der Speicher für einzelne Anwendungsdomänen an diese Nummer verglichen werden kann.  
  
    -   Verwaltete API: <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType> Eigenschaft.  
  
    -   Hosting-API: [ICLRAppDomainResourceMonitor:: GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) Methode `pTotalBytesSurvived` Parameter.  
  
    -   ETW-Ereignisse: `AppDomainMemSurvived` Ereignis `ProcessSurvived` Feld.  
  
### <a name="determining-when-a-full-blocking-collection-occurs"></a>Bestimmen, wenn eine vollständige stattfindet blockierende Garbage Collection  
 Um zu bestimmen, wenn für die Anzahl der beibehaltenen Speichers korrekt sind, müssen Sie wissen, wenn nur eine vollständigen blockierende Auflistung aufgetreten ist. Die Methode für diese Vorgehensweise hängt von der API, die Sie verwenden, um die ARM-Statistik untersuchen.  
  
#### <a name="managed-api"></a>Verwaltete API  
 Wenn Sie die Eigenschaften der verwenden der <xref:System.AppDomain> -Klasse, die Sie verwenden die <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType> Methode, um die Registrierung für die Benachrichtigung über vollständige Garbage Collections. Schwellenwert, den Sie verwenden, ist nicht wichtig,, weil Sie darauf, für den Abschluss einer Auflistung anstelle der Ansatz einer Auflistung warten. Rufen Sie dann die <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType> Methode, die blockiert, bis eine vollständige Auflistung abgeschlossen ist. Sie können einen Thread erstellen, der die Methode in einer Schleife aufgerufen und eine Analyse erforderlich ist, wenn die-Methode zurückgibt.  
  
 Alternativ können Sie rufen die <xref:System.GC.CollectionCount%2A?displayProperty=nameWithType> Methode in regelmäßigen Abständen, um festzustellen, ob die Anzahl der Garbage Collections der Generation 2 erhöht hat. Je nach das Abrufintervall möglicherweise dieses Verfahren nicht genau ein Hinweis auf das Vorkommen einer vollständigen Auflistung bereit.  
  
#### <a name="hosting-api"></a>Hosting-API  
 Wenn Sie die nicht verwaltete hosting-API verwenden, der Host muss übergeben der CLR eine Implementierung der [IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md) Schnittstelle. Die CLR ruft die [IHostGCManager:: SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) Methode, wenn die Ausführung des Threads wird, die angehalten wurden fortgesetzt, während eine Sammlung ausgeführt wird. Die CLR übergibt die Generierung der abgeschlossenen Auflistung als Parameter der Methode, damit der Host bestimmen kann, ob die Auflistung vollständig oder teilweise war. Die Implementierung der [IHostGCManager:: SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) Methode kann Abfragen für Speicher, um sicherzustellen, dass die Werte abgerufen werden, sobald sie aktualisiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [ICLRAppDomainResourceMonitor-Schnittstelle](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [\<appDomainResourceMonitoring>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)
