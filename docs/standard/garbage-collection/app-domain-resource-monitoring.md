---
title: "Application Domain Resource Monitoring | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "monitoring managed memory use by application domain"
  - "application domains, memory use"
  - "memory use, monitoring"
  - "application domains, resource monitoring"
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Application Domain Resource Monitoring
Die Überwachung von Anwendungsdomänenressourcen \(Application Domain Resource Monitoring, ARM\) ermöglicht Hosts das Überwachen der CPU\- und Speicherauslastung durch eine Anwendungsdomäne.  Dies ist nützlich für Hosts wie z. B. ASP.NET, die viele Anwendungsdomänen in einem Prozess mit langer Laufzeit verwenden.  Der Host kann die Anwendungsdomäne einer Anwendung entladen, die die Leistung des ganzen Prozesses beeinträchtigt, sofern die problematische Anwendung identifiziert werden kann.  ARM stellt Informationen bereit, die dabei helfen können, solche Entscheidungen zu treffen.  
  
 Ein Hostingdienst kann z. B. viele Anwendungen umfassen, die auf einem ASP.NET\-Server ausgeführt werden.  Wenn eine Anwendung im Prozess beginnt, zu viel Speicher oder zu viel Prozessorzeit zu belegen, kann der Hostingdienst die Anwendungsdomäne, die das Problem verursacht, mithilfe von ARM identifizieren.  
  
 ARM ist nicht sehr komplex und kann daher in Liveanwendungen verwendet werden.  Sie können mithilfe der Ereignisablaufverfolgung für Windows \(ETW\) oder direkt durch verwaltete oder systemeigene APIs auf die Informationen zugreifen.  
  
## Aktivieren der Ressourcenüberwachung  
 ARM kann auf vier Arten aktiviert werden: durch Angeben einer Konfigurationsdatei beim Start der Common Language Runtime \(CLR\), mit einer nicht verwalteten Hosting\-API, mit verwaltetem Code oder durch Lauschen auf ARM\-ETW\-Ereignisse.  
  
 Sobald ARM aktiviert ist, wird mit dem Sammeln von Daten zu allen Anwendungsdomänen im Prozess begonnen.  Wenn eine Anwendungsdomäne vor der Aktivierung von ARM erstellt wurde, liegen kumulierte Daten erst ab dem Zeitpunkt der ARM\-Aktivierung und nicht ab dem Zeitpunkt der Erstellung der Anwendungsdomäne vor. Sobald ARM aktiviert wurde, kann es nicht deaktiviert werden.  
  
-   Sie können ARM beim CLR\-Start aktivieren, indem Sie das [\<AppDomainResourceMonitoring\>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)\-Element der Konfigurationsdatei hinzufügen, und das Attribut `enabled` auf `true` festlegen.  Der Wert `false` \(die Standardeinstellung\) bedeutet nur, dass ARM nicht beim Start aktiviert wird; Sie können ARM später mit einem der anderen Aktivierungsmechanismen aktivieren.  
  
-   Der Host kann ARM aktivieren, indem er die [ICLRAppDomainResourceMonitor](../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)\-Hostingschnittstelle anfordert.  Sobald diese Schnittstelle erfolgreich angefordert wurde, wird ARM aktiviert.  
  
-   In verwaltetem Code kann ARM aktiviert werden, indem die statische \(`Shared` in Visual Basic\) <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>\-Eigenschaft auf `true` festgelegt wird.  Sobald die Eigenschaft festgelegt ist, wird ARM aktiviert.  
  
-   Sie können ARM nach dem Start aktivieren, indem Sie auf ETW\-Ereignisse lauschen.  ARM wird aktiviert und fängt an, Ereignisse für alle Anwendungsdomänen auszulösen, wenn Sie den öffentlichen Anbieter `Microsoft-Windows-DotNETRuntime` mit dem `AppDomainResourceManagementKeyword`\-Schlüsselwort aktivieren.  Um Daten mit Anwendungsdomänen und Threads zu korrelieren, müssen Sie auch den `Microsoft-Windows-DotNETRuntimeRundown`\-Anbieter mit dem `ThreadingKeyword`\-Schlüsselwort aktivieren.  
  
## Verwenden von ARM  
 ARM gibt die gesamte Prozessorzeit an, die von einer Anwendungsdomäne verwendet wird, und stellt drei Arten von Informationen zur Speicherauslastung bereit.  
  
-   **Gesamtprozessorzeit für eine Anwendungsdomäne \(in Sekunden\)**: Dieser Wert wird berechnet, indem die vom Betriebssystem gemeldeten Threadzeiten für alle Threads, die während ihrer Lebensdauer in der Anwendungsdomäne ausgeführt wurden, addiert werden.  Blockierte Threads oder Threads im Ruhezustand verwenden keine Prozessorzeit.  Wenn ein Thread im systemeigenen Code aufgerufen wird, wird die Ausführungszeit dieses Threads im systemeigenen Code zur Zeit für die Anwendungsdomäne addiert, von der aus der Thread aufgerufen wurde.  
  
    -   Verwaltete API: <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=fullName>\-Eigenschaft.  
  
    -   Hosting\-API: [ICLRAppDomainResourceMonitor::GetCurrentCpuTime](../Topic/ICLRAppDomainResourceMonitor::GetCurrentCpuTime%20Method.md)\-Methode.  
  
    -   ETW\-Ereignisse: `ThreadCreated`, `ThreadAppDomainEnter` und `ThreadTerminated`\-Ereignisse.  Informationen zu Anbietern und Schlüsselwörtern finden Sie in "Überwachen von Ereignissen für Anwendungsdomänenressourcen" in [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md).  
  
-   **Insgesamt von einer Anwendungsdomäne während ihrer Lebensdauer vorgenommene Speicherbelegungen \(in Bytes\)**: Der Wert für die gesamten Speicherbelegungen spiegelt nicht immer die Speicherauslastung einer Anwendungsdomäne wider, da die zugeordneten Objekte kurzlebig sein können.  Wenn eine Anwendung jedoch eine große Anzahl von Objekten zuordnet und freigibt, können die Kosten für die Speicherbelegungen beträchtlich sein.  
  
    -   Verwaltete API: <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=fullName>\-Eigenschaft.  
  
    -   Hosting\-API: [ICLRAppDomainResourceMonitor::GetCurrentAllocated](../Topic/ICLRAppDomainResourceMonitor::GetCurrentAllocated%20Method.md)\-Methode.  
  
    -   ETW\-Ereignisse: `AppDomainMemAllocated`\-Ereignis, `Allocated`\-Feld.  
  
-   **Verwalteter Speicher \(in Bytes\), auf den von einer Anwendungsdomäne verwiesen wird und der nach der letzten vollständigen, blockierenden Garbage Collection verbleibt**: Dieser Wert ist nur nach einer vollständigen, blockierenden Garbage Collection genau. \(Diese unterscheidet sich von gleichzeitigen Garbage Collections, die im Hintergrund stattfinden und die Anwendung nicht blockieren.\) Beispielweise verursacht die <xref:System.GC.Collect?displayProperty=fullName>\-Methodenüberladung eine vollständige blockierende Garbage Collection.  
  
    -   Verwaltete API: <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=fullName>\-Eigenschaft.  
  
    -   Hosting\-API: [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../Topic/ICLRAppDomainResourceMonitor::GetCurrentSurvived%20Method.md)\-Methode, `pAppDomainBytesSurvived`\-Parameter.  
  
    -   ETW\-Ereignisse: `AppDomainMemSurvived`\-Ereignis, `Survived`\-Feld.  
  
-   **Gesamter verwalteter Speicher \(in Bytes\), auf den vom Prozess verwiesen wird und der nach der letzten vollständigen, blockierenden Garbage Collection verbleibt**: Der verbleibende Speicher für einzelne Anwendungsdomänen kann mit diesem Wert verglichen werden.  
  
    -   Verwaltete API: <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=fullName>\-Eigenschaft.  
  
    -   Hosting\-API: [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../Topic/ICLRAppDomainResourceMonitor::GetCurrentSurvived%20Method.md)\-Methode, `pTotalBytesSurvived`\-Parameter.  
  
    -   ETW\-Ereignisse: `AppDomainMemSurvived`\-Ereignis, `ProcessSurvived`\-Feld.  
  
### Bestimmen, wann eine vollständige, blockierende Garbage Collection stattfindet  
 Um zu bestimmen, ob die Werte für den verbliebenen Speicher genau sind, müssen Sie wissen, wann gerade eine vollständige, blockierende Garbage Collection stattgefunden hat.  Wie Sie hierzu vorgehen, hängt von der API ab, mit der Sie die ARM\-Statistik untersuchen.  
  
#### Verwaltete API  
 Wenn Sie die Eigenschaften der <xref:System.AppDomain>\-Klasse verwenden, können Sie sich mithilfe der <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=fullName>\-Methode für eine Benachrichtigung über vollständige Garbage Collections registrieren.  Der verwendete Schwellenwert ist nicht wichtig, da Sie ja auf den Abschluss einer Garbage Collection warten und der Ansatz für eine Garbage Collection hierbei nicht relevant ist.  Sie können dann die <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=fullName>\-Methode aufrufen, die blockiert, bis eine vollständige Garbage Collection abgeschlossen wurde.  Sie können einen Thread erstellen, der die Methode in einer Schleife aufruft und alle notwendigen Analysen durchführt, wann immer die Methode zurückkehrt.  
  
 Alternativ können Sie die <xref:System.GC.CollectionCount%2A?displayProperty=fullName>\-Methode aufrufen, um in regelmäßigen Abständen zu prüfen, ob die Anzahl von Generation 2\-Garbage Collections zugenommen hat.  Diese Technik kann möglicherweise das Vorkommen einer vollständigen Garbage Collection nicht genau anzeigen. Dies hängt von der Abrufhäufigkeit ab.  
  
#### Hosting\-API  
 Wenn Sie die nicht verwaltete Hosting\-API verwenden, muss der Host der CLR eine Implementierung der [IHostGCManager](../../../ocs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)\-Schnittstelle übergeben.  Die CLR ruft die [IHostGCManager::SuspensionEnding](../Topic/IHostGCManager::SuspensionEnding%20Method.md)\-Methode auf, wenn die Ausführung der Threads, die während der Garbage Collection angehalten wurden, fortgesetzt wird.  Die CLR übergibt die Generation der abgeschlossenen Garbage Collection als Parameter der Methode, sodass der Host bestimmen kann, ob eine vollständige oder partielle Garbage Collection stattgefunden hat.  Die Implementierung der [IHostGCManager::SuspensionEnding](../Topic/IHostGCManager::SuspensionEnding%20Method.md)\-Methode kann den verbleibenden Speicher abfragen, um sicherzustellen, dass die Werte abgerufen werden, sobald sie aktualisiert wurden.  
  
## Siehe auch  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>   
 [ICLRAppDomainResourceMonitor\-Schnittstelle](../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)   
 [\<AppDomainResourceMonitoring\>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)   
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)