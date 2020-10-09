---
ms.openlocfilehash: 4ffef401c07dbb27db7c0225acdc6817d95bfe11
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "91451425"
---
## <a name="available-counters"></a>Verfügbare Leistungsindikatoren

In verschiedenen .NET-Paketen werden grundlegende Metriken zu Garbage Collection (GC), Just-in-Time (JIT), Assemblys, Ausnahmen, Threading, Netzwerken und Webanforderungen mithilfe von EventCounters veröffentlicht.

### <a name="systemruntime-counters"></a>„System.Runtime“-Leistungsindikatoren

Die folgenden Leistungsindikatoren werden als Teil der .NET-Laufzeit veröffentlicht und in [`RuntimeEventSource.cs`](https://github.com/dotnet/coreclr/blob/master/src/System.Private.CoreLib/src/System/Diagnostics/Eventing/RuntimeEventSource.cs)verwaltet.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="% Time in GC since last GC"::: (`time-in-gc`) | Der Prozentsatz der Zeit für GC seit der letzten GC. |
| :::no-loc text="Allocation Rate"::: (`alloc-rate`) | Die Zuweisungsrate in Bytes. |
| :::no-loc text="CPU Usage"::: (`cpu-usage`) | Die CPU-Nutzung durch den Prozess in Prozent |
| :::no-loc text="Exception Count"::: (`exception-count`) | Die Anzahl der aufgetretenen Ausnahmen. |
| :::no-loc text="GC Heap Size"::: (`gc-heap-size`) | Die Anzahl der zugeordneten Bytes basierend auf <xref:System.GC.GetTotalMemory(System.Boolean)?displayProperty=nameWithType>. |
| :::no-loc text="Gen 0 GC Count"::: (`gen-0-gc-count`) | Die Anzahl der GC-Vorgänge für Gen 0. |
| :::no-loc text="Gen 0 Size"::: (`gen-0-size`) | Die Anzahl der Bytes für Gen 0-GC. |
| :::no-loc text="Gen 1 GC Count"::: (`gen-1-gc-count`) | Die Anzahl der Vorkommen von GC für Gen 1. |
| :::no-loc text="Gen 1 Size"::: (`gen-1-size`) | Die Anzahl der Bytes für Gen 1-GC. |
| :::no-loc text="Gen 2 GC Count"::: (`gen-2-gc-count`) | Die Anzahl der GC-Vorgänge für Gen 2. |
| :::no-loc text="Gen 2 Size"::: (`gen-2-size`) | Die Anzahl der Bytes für Gen 2-GC. |
| :::no-loc text="LOH Size"::: (`loh-size`) | Die Anzahl der Bytes für Gen 3-GC. |
| :::no-loc text="POH Size"::: (`poh-size`) | Die Byteanzahl für den angehefteten Objektheap (ab .NET 5 verfügbar) |
| :::no-loc text="GC Fragmentation"::: (`gc-fragmentation`) | Die Fragmentierung des GC-Heap (ab .NET 5 verfügbar) |
| :::no-loc text="Monitor Lock Contention Count"::: (`monitor-lock-contention-count`) | Die Anzahl der Konflikte beim Versuch, die Sperre des Monitors aufzuheben (basierend auf <xref:System.Threading.Monitor.LockContentionCount?displayProperty=nameWithType>). |
| :::no-loc text="Number of Active Timers"::: (`active-timer-count`) | Die Anzahl der derzeit aktiven <xref:System.Threading.Timer>-Instanzen, basierend auf <xref:System.Threading.Timer.ActiveCount?displayProperty=nameWithType>. |
| :::no-loc text="Number of Assemblies Loaded"::: (`assembly-count`) | Die Anzahl der <xref:System.Reflection.Assembly>-Instanzen, die zu einem bestimmten Zeitpunkt in einen Prozess geladen wurden. |
| :::no-loc text="ThreadPool Completed Work Item Count"::: (`threadpool-completed-items-count`) | Die Anzahl der Arbeitselemente, die bisher in <xref:System.Threading.ThreadPool> verarbeitet wurden. |
| :::no-loc text="ThreadPool Queue Length"::: (`threadpool-queue-length`) | Die Anzahl der Arbeitselemente, die derzeit für die Verarbeitung in <xref:System.Threading.ThreadPool> in die Warteschlange eingereiht wurden. |
| :::no-loc text="ThreadPool Thread Count"::: (`threadpool-thread-count`) | Die Anzahl der derzeit in <xref:System.Threading.ThreadPool> vorhandenen Threads im Threadpool, basierend auf <xref:System.Threading.ThreadPool.ThreadCount?displayProperty=nameWithType>. |
| :::no-loc text="Working Set"::: (`working-set`) | Die Größe des physischen Speichers, der dem Prozesskontext zu einem bestimmten Zeitpunkt zugeordnet ist, basierend auf <xref:System.Environment.WorkingSet?displayProperty=nameWithType>. |
| :::no-loc text="IL Bytes Jitted"::: (`il-bytes-jitted`) | Die Gesamtgröße der JIT-kompilierten ILs in Byte (ab .NET 5 verfügbar) |
| :::no-loc text="Method Jitted Count"::: (`method-jitted-count`) | Die Gesamtgröße der JIT-kompilierten Methoden (ab .NET 5 verfügbar) |

### <a name="microsoftaspnetcorehosting-counters"></a>Microsoft.AspNetCore.Hosting-Leistungsindikatoren

Die folgenden Leistungsindikatoren werden als Teil von [ASP.NET Core](/aspnet/core) veröffentlicht und in [`HostingEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Hosting/Hosting/src/Internal/HostingEventSource.cs) verwaltet.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="Current Requests"::: (`current-requests`) | Die Gesamtzahl der Anforderungen, die gestartet, aber noch nicht beendet wurden. |
| :::no-loc text="Failed Requests"::: (`failed-requests`) | Die Gesamtzahl der fehlgeschlagenen Anforderungen, die während der Lebensdauer der App aufgetreten sind. |
| :::no-loc text="Request Rate"::: (`requests-per-second`) | Die Anzahl der pro Sekunde auftretenden Anforderungen. |
| :::no-loc text="Total Requests"::: (`total-requests`) | Die Gesamtzahl der Anforderungen, die während der Lebensdauer der App aufgetreten sind. |

### <a name="microsoftaspnetcorehttpconnections-counters"></a>Microsoft.AspNetCore.Http.Connections-Leistungsindikatoren

Die folgenden Leistungsindikatoren werden als Teil von [ASP.NET Core SignalR](/aspnet/core/signalr/introduction) veröffentlicht und in [`HttpConnectionsEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/SignalR/common/Http.Connections/src/Internal/HttpConnectionsEventSource.cs) verwaltet.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="Average Connection Duration"::: (`connections-duration`) | Die durchschnittliche Dauer einer Verbindung in Millisekunden. |
| :::no-loc text="Current Connections"::: (`current-connections`) | Die Anzahl der aktiven Verbindungen, die gestartet, aber noch nicht beendet wurden. |
| :::no-loc text="Total Connections Started"::: (`connections-started`) | Die Gesamtzahl gestarteter Verbindungen. |
| :::no-loc text="Total Connections Stopped"::: (`connections-stopped`) | Die Gesamtzahl von Verbindungen, die beendet wurden. |
| :::no-loc text="Total Connections Timed Out"::: (`connections-timed-out`) | Die Gesamtzahl von Verbindungen, bei denen ein Timeout aufgetreten ist. |

### <a name="microsoft-aspnetcore-server-kestrel-counters"></a>Microsoft-AspNetCore-Server-Kestrel-Leistungsindikatoren

Die folgenden Leistungsindikatoren werden als Teil des [ASP.NET Core Kestrel-Webservers](/aspnet/core/fundamentals/servers/kestrel) veröffentlicht und in [`KestrelEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Servers/Kestrel/Core/src/Internal/Infrastructure/KestrelEventSource.cs) verwaltet.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="Connection Queue Length"::: (`connection-queue-length`) | Die aktuelle Länge der Verbindungswarteschlange. |
| :::no-loc text="Connection Rate"::: (`connections-per-second`) | Die Anzahl der Verbindungen mit dem Webserver pro Sekunde. |
| :::no-loc text="Current Connections"::: (`current-connections`) | Die aktuelle Anzahl aktiver Verbindungen mit dem Webserver. |
| :::no-loc text="Current TLS Handshakes"::: (`current-tls-handshakes`) | Die aktuelle Anzahl von TLS-Handshakes. |
| :::no-loc text="Current Upgraded Requests (WebSockets)"::: (`current-upgraded-requests`) | Aktuelle Anzahl aktualisierter Anforderungen (WebSockets) |
| :::no-loc text="Failed TLS Handshakes"::: (`failed-tls-handshakes`) | Die Gesamtzahl der fehlgeschlagenen TLS-Handshakes. |
| :::no-loc text="Request Queue Length"::: (`request-queue-length`) | Die aktuelle Länge der Anforderungswarteschlange. |
| :::no-loc text="TLS Handshake Rate"::: (`tls-handshakes-per-second`) | Die Anzahl von TLS-Handshakes pro Sekunde. |
| :::no-loc text="Total Connections"::: (`total-connections`) | Die Gesamtzahl von Verbindungen mit dem Webserver. |
| :::no-loc text="Total TLS Handshakes"::: (`total-tls-handshakes`) | Die Gesamtzahl von TLS-Handshakes mit dem Webserver. |
