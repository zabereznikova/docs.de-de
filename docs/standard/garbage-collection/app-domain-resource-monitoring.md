---
title: Überwachung von Anwendungsdomänenressourcen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
ms.openlocfilehash: 12dfdd3ac6d75a3e2a33f93d8847c963ded912e8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286092"
---
# <a name="application-domain-resource-monitoring"></a>Überwachung von Anwendungsdomänenressourcen

Hosts mit der Ressourcenüberwachung für die Anwendungsdomäne (ARM) können die CPU- und Speicherauslastung pro Anwendungsdomäne überwachen. Dies ist nützlich für Hosts wie ASP.NET, die eine Vielzahl von Anwendungsdomänen in einem Prozess mit langer Ausführungsdauer verwenden. Der Host kann die Anwendungsdomäne einer Anwendung entladen, die sich negativ auf die Leistung des gesamten Prozesses auswirkt, jedoch nur, wenn er die problematische Anwendung ermitteln kann. Die ARM stellt Informationen bereit, die als Unterstützung bei solchen Entscheidungen herangezogen werden können.

In einem Hostingdienst werden möglicherweise viele Anwendungen auf einem ASP.NET-Server ausgeführt. Wenn eine Anwendung im Prozess zu viele Speicherressourcen verbraucht oder zu viel Prozessorzeit in Anspruch nimmt, kann der Hostingdienst mithilfe der ARM die Anwendungsdomäne ermitteln, die das Problem verursacht.

Die ARM ist für den Einsatz bei aktiven Anwendungen entsprechend einfach konzipiert. Sie können mithilfe der Ereignisablaufverfolgung für Windows (ETW) oder direkt über verwaltete oder native APIs auf die Informationen zugreifen.

## <a name="enabling-resource-monitoring"></a>Aktivieren der Ressourcenüberwachung

Die ARM kann auf vier Arten aktiviert werden: Durch Bereitstellen einer Konfigurationsdatei beim Starten der Common Language Runtime (CLR), durch eine nicht verwaltete Hosting-API, durch verwalteten Code oder durch Lauschen auf ARM-ETW-Ereignisse.

Sobald die ARM aktiviert ist, beginnt diese mit der Sammlung von Daten für alle Anwendungsdomänen im Prozess. Wenn vor der Aktivierung der ARM eine Anwendungsdomäne erstellt wurde, wird bei der Aktivierung der ARM (nicht bei der Erstellung der Anwendungsdomäne) die Sammlung kumulativer Daten gestartet. Sobald diese aktiviert ist, kann die ARM nicht deaktiviert werden.

- Sie können die ARM beim Start der CLR aktivieren, indem Sie das [\<appDomainResourceMonitoring>](../../framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)-Element zur Konfigurationsdatei hinzufügen und das `enabled`-Attribut auf `true` festlegen. Der Wert `false` (Standardeinstellung) gibt lediglich an, dass die ARM beim Start nicht aktiviert wurde. Sie können sie später durch eine der anderen Aktivierungsmethoden aktivieren.

- Der Host kann die ARM durch Anfordern der Hostingschnittstelle [ICLRAppDomainResourceMonitor](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) aktivieren. Sobald diese Schnittstelle erfolgreich abgerufen wurde, wird die ARM aktiviert.

- Verwalteter Code kann die ARM aktivieren, indem die statische (`Shared` in Visual Basic) <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>-Eigenschaft auf `true` festgelegt wird. Sobald die Eigenschaft festgelegt ist, wird die ARM aktiviert.

- Sie können die ARM nach dem Start durch Lauschen auf ETW-Ereignisse aktivieren. Wenn Sie den öffentlichen Anbieter `Microsoft-Windows-DotNETRuntime` mit dem Schlüsselwort `AppDomainResourceManagementKeyword` aktivieren, wird die ARM aktiviert, und sie beginnt mit dem Auslösen von Ereignissen für alle Anwendungsdomänen. Um Daten mit Anwendungsdomänen und -threads zu korrelieren, müssen Sie auch den Anbieter `Microsoft-Windows-DotNETRuntimeRundown` mit dem Schlüsselwort `ThreadingKeyword` aktivieren.

## <a name="using-arm"></a>Verwenden der ARM

Die ARM stellt die gesamte von einer Anwendungsdomäne in Anspruch genommene Prozessorzeit sowie drei Arten von Informationen zur Speicherauslastung bereit.

- **Gesamtprozessorzeit für eine Anwendungsdomäne in Sekunden:** Diese wird durch Addieren der Threadzeiten berechnet, die vom Betriebssystem für alle Threads gemeldet werden, die während ihrer Lebensdauer Zeit für die Ausführung in der Anwendungsdomäne aufgewendet haben. Blockierte Threads oder Threads im Ruhezustand nehmen keine Prozessorzeit in Anspruch. Wenn ein Thread nativen Code aufruft, ist die vom Thread für nativen Code aufgewendete Zeit im Wert für die Anwendungsdomäne enthalten, in der der Aufruf erfolgt ist.

  - Verwaltete API: Eigenschaft <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>

  - Hosting-API: [ICLRAppDomainResourceMonitor::GetCurrentCpuTime](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)-Methode

  - ETW-Ereignisse: Ereignisse `ThreadCreated`, `ThreadAppDomainEnter` und `ThreadTerminated`. Informationen zu Anbietern und Schlüsselwörtern finden Sie im Artikel [CLR-ETW-Ereignisse](../../framework/performance/clr-etw-events.md) unter „ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung“.

- **Gesamtanzahl der durch eine Anwendungsdomäne während ihrer Lebensdauer vorgenommenen verwalteten Zuordnungen in Byte:** Die Gesamtanzahl der Zuordnungen spiegelt nicht immer die Speicherauslastung einer Anwendungsdomäne wider, da die zugeordneten Objekte kurzlebig sein können. Wenn eine Anwendung eine große Anzahl von Objekten zuordnet und freigibt, können die Kosten für die Zuordnungen beträchtlich sein.

  - Verwaltete API: Eigenschaft <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>

  - Hosting-API: [ICLRAppDomainResourceMonitor::GetCurrentAllocated](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)-Methode

  - ETW-Ereignisse: Ereignis `AppDomainMemAllocated`, Feld `Allocated`

- **Verwalteter Speicher in Byte, auf den durch eine Anwendungsdomäne verwiesen wird und der bei der letzten vollständigen blockierenden Collection beibehalten wurde:** Dieser Wert ist erst nach einer vollständigen blockierenden Collection präzise. (Dieser Vorgang stellt das Gegenteil zu gleichzeitigen Auflistungen dar, die im Hintergrund ausgeführt werden und die Anwendung nicht blockieren.) Die Methodenüberladung <xref:System.GC.Collect?displayProperty=nameWithType> führt beispielsweise zu einer vollständigen blockierenden Auflistung.

  - Verwaltete API: Eigenschaft <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>

  - Hosting-API: [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)-Methode mit dem Parameter `pAppDomainBytesSurvived`

  - ETW-Ereignisse: Ereignis `AppDomainMemSurvived`, Feld `Survived`

- **Gesamter verwalteter Speicher in Byte, auf den vom Prozess verwiesen wird und der bei der letzten vollständigen blockierenden Collection beibehalten wurde:** Der Speicher, der für einzelne Anwendungsdomänen beibehalten wird, kann mit dieser Zahl verglichen werden.

  - Verwaltete API: Eigenschaft <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>

  - Hosting-API: [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)-Methode mit dem Parameter `pTotalBytesSurvived`

  - ETW-Ereignisse: Ereignis `AppDomainMemSurvived`, Feld `ProcessSurvived`

### <a name="determining-when-a-full-blocking-collection-occurs"></a>Ermittlung des Zeitpunkts, an dem eine vollständige blockierende Auflistung auftritt

Um zu ermitteln, wann die Menge des beibehaltenen Speichers genau ist, müssen Sie wissen, wann soeben eine vollständige blockierende Auflistung aufgetreten ist. Die hierbei angewendete Methode hängt von der API ab, die Sie zum Untersuchen der ARM-Statistik verwenden.

#### <a name="managed-api"></a>Verwaltete API

Wenn Sie die Eigenschaften der <xref:System.AppDomain>-Klasse verwenden, können Sie sich mithilfe der <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType>-Methode für Benachrichtigungen über vollständige Auflistungen registrieren. Der von Ihnen verwendete Schwellenwert ist nicht von Bedeutung, da Sie auf den Abschluss einer Auflistung warten, nicht auf den Ansatz einer Auflistung. Sie können dann die Methode <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType> aufrufen, die bis zum Abschluss einer vollständigen Auflistung blockiert ist. Sie können einen Thread erstellen, der die Methode in einer Schleife aufruft und bei der Rückgabe der Methode alle erforderlichen Analysen durchführt.

Alternativ können Sie in regelmäßigen Abständen die <xref:System.GC.CollectionCount%2A?displayProperty=nameWithType>-Methode aufrufen, um festzustellen, ob sich die Anzahl der Auflistungen der Generation 2 erhöht hat. Dieses Verfahren kann abhängig von der Abrufhäufigkeit möglicherweise keine genauen Angaben zum Auftreten einer vollständigen Auflistung bereitstellen.

#### <a name="hosting-api"></a>Hosting-API

Wenn Sie die nicht verwaltete Hosting-API verwenden, muss Ihr Host der CLR eine Implementierung der [IHostGCManager](../../framework/unmanaged-api/hosting/ihostgcmanager-interface.md)-Schnittstelle übergeben. Die CLR ruft die Methode [IHostGCManager::SuspensionEnding](../../framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) auf, wenn bei der Ausführung einer Auflistung die Ausführung der angehaltenen Threads fortgesetzt wird. Die CLR übergibt die Erzeugung der abgeschlossenen Auflistung als Parameter der Methode, damit der Host ermitteln kann, ob die Auflistung vollständig oder teilweise ausgeführt wurde. Ihre Implementierung der [IHostGCManager::SuspensionEnding](../../framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)-Methode kann den beibehaltenen Speicher abfragen, um sicherzustellen, dass die Werte direkt nach ihrer Aktualisierung abgerufen werden.

## <a name="see-also"></a>Siehe auch

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [ICLRAppDomainResourceMonitor-Schnittstelle](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [\<appDomainResourceMonitoring>](../../framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [CLR-ETW-Ereignisse](../../framework/performance/clr-etw-events.md)
