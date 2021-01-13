---
title: Bekannte EventCounter-APIs in .NET
description: Sehen Sie sich die von der .NET-Runtime und den .NET-Bibliotheken veröffentlichten EventCounter-APIs an.
ms.topic: reference
ms.date: 12/17/2020
ms.openlocfilehash: 8bd14c7caf004cefe73d5b0676b9fa3280840442
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "97737293"
---
# <a name="well-known-eventcounters-in-net"></a>Bekannte EventCounter-APIs in .NET

Die .NET-Runtime und die .NET-Bibliotheken implementieren und veröffentlichen einige [`EventCounter`](./event-counters.md)-APIs, mit denen verschiedene Leistungsprobleme identifiziert und diagnostiziert werden können. Dieses Dokument ist eine Referenz für die Anbieter, die zum Überwachen dieser `EventCounters`-APIs und ihrer Beschreibungen verwendet werden können.

## <a name="systemruntime-counters"></a>System.Runtime-Zähler

Die folgenden Zähler werden als Teil der .NET-Runtime (CoreCLR) veröffentlicht und in [`RuntimeEventSource.cs`](https://github.com/dotnet/coreclr/blob/master/src/System.Private.CoreLib/src/System/Diagnostics/Eventing/RuntimeEventSource.cs) verwaltet.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="% Time in GC since last GC"::: (`time-in-gc`) | Der Prozentsatz der Zeit für GC seit der letzten GC. |
| :::no-loc text="Allocation Rate"::: (`alloc-rate`) | Die Anzahl der pro Updateintervall zugeordneten Bytes |
| :::no-loc text="CPU Usage"::: (`cpu-usage`) | Der Prozentsatz der CPU-Auslastung des Prozesses in Relation zu allen CPU-Ressourcen des Systems |
| :::no-loc text="Exception Count"::: (`exception-count`) | Die Anzahl der aufgetretenen Ausnahmen. |
| :::no-loc text="GC Heap Size"::: (`gc-heap-size`) | Die Anzahl der zugeordneten Bytes basierend auf <xref:System.GC.GetTotalMemory(System.Boolean)?displayProperty=nameWithType>. |
| :::no-loc text="Gen 0 GC Count"::: (`gen-0-gc-count`) | Die Anzahl der GC-Vorgänge für Gen 0 pro Updateintervall |
| :::no-loc text="Gen 0 Size"::: (`gen-0-size`) | Die Anzahl der Bytes für Gen 0-GC. |
| :::no-loc text="Gen 1 GC Count"::: (`gen-1-gc-count`) | Die Anzahl der GC-Vorgänge für Gen 1 pro Updateintervall |
| :::no-loc text="Gen 1 Size"::: (`gen-1-size`) | Die Anzahl der Bytes für Gen 1-GC. |
| :::no-loc text="Gen 2 GC Count"::: (`gen-2-gc-count`) | Die Anzahl der GC-Vorgänge für Gen 2 pro Updateintervall |
| :::no-loc text="Gen 2 Size"::: (`gen-2-size`) | Die Anzahl der Bytes für Gen 2-GC. |
| :::no-loc text="LOH Size"::: (`loh-size`) | Die Anzahl von Bytes für den großen Objektheap |
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

## <a name="microsoftaspnetcorehosting-counters"></a>Microsoft.AspNetCore.Hosting-Leistungsindikatoren

Die folgenden Leistungsindikatoren werden als Teil von [ASP.NET Core](/aspnet/core) veröffentlicht und in [`HostingEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Hosting/Hosting/src/Internal/HostingEventSource.cs) verwaltet.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="Current Requests"::: (`current-requests`) | Die Gesamtanzahl von Anforderungen, die gestartet, aber noch nicht beendet wurden |
| :::no-loc text="Failed Requests"::: (`failed-requests`) | Die Gesamtzahl der fehlgeschlagenen Anforderungen, die während der Lebensdauer der App aufgetreten sind. |
| :::no-loc text="Request Rate"::: (`requests-per-second`) | Die Anzahl der Anforderungen pro Updateintervall |
| :::no-loc text="Total Requests"::: (`total-requests`) | Die Gesamtzahl der Anforderungen, die während der Lebensdauer der App aufgetreten sind. |

## <a name="microsoftaspnetcorehttpconnections-counters"></a>Microsoft.AspNetCore.Http.Connections-Leistungsindikatoren

Die folgenden Leistungsindikatoren werden als Teil von [ASP.NET Core SignalR](/aspnet/core/signalr/introduction) veröffentlicht und in [`HttpConnectionsEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/SignalR/common/Http.Connections/src/Internal/HttpConnectionsEventSource.cs) verwaltet.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="Average Connection Duration"::: (`connections-duration`) | Die durchschnittliche Dauer einer Verbindung in Millisekunden. |
| :::no-loc text="Current Connections"::: (`current-connections`) | Die Anzahl der aktiven Verbindungen, die gestartet, aber noch nicht beendet wurden. |
| :::no-loc text="Total Connections Started"::: (`connections-started`) | Die Gesamtzahl gestarteter Verbindungen. |
| :::no-loc text="Total Connections Stopped"::: (`connections-stopped`) | Die Gesamtzahl von Verbindungen, die beendet wurden. |
| :::no-loc text="Total Connections Timed Out"::: (`connections-timed-out`) | Die Gesamtzahl von Verbindungen, bei denen ein Timeout aufgetreten ist. |

## <a name="microsoft-aspnetcore-server-kestrel-counters"></a>Microsoft-AspNetCore-Server-Kestrel-Leistungsindikatoren

Die folgenden Leistungsindikatoren werden als Teil des [ASP.NET Core Kestrel-Webservers](/aspnet/core/fundamentals/servers/kestrel) veröffentlicht und in [`KestrelEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Servers/Kestrel/Core/src/Internal/Infrastructure/KestrelEventSource.cs) verwaltet.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="Connection Queue Length"::: (`connection-queue-length`) | Die aktuelle Länge der Verbindungswarteschlange. |
| :::no-loc text="Connection Rate"::: (`connections-per-second`) | Die Anzahl der Verbindungen mit dem Webserver pro Updateintervall |
| :::no-loc text="Current Connections"::: (`current-connections`) | Die aktuelle Anzahl aktiver Verbindungen mit dem Webserver. |
| :::no-loc text="Current TLS Handshakes"::: (`current-tls-handshakes`) | Die aktuelle Anzahl von TLS-Handshakes. |
| :::no-loc text="Current Upgraded Requests (WebSockets)"::: (`current-upgraded-requests`) | Aktuelle Anzahl aktualisierter Anforderungen (WebSockets) |
| :::no-loc text="Failed TLS Handshakes"::: (`failed-tls-handshakes`) | Die Gesamtzahl der fehlgeschlagenen TLS-Handshakes. |
| :::no-loc text="Request Queue Length"::: (`request-queue-length`) | Die aktuelle Länge der Anforderungswarteschlange. |
| :::no-loc text="TLS Handshake Rate"::: (`tls-handshakes-per-second`) | Die Anzahl der TLS-Handshakes pro Updateintervall |
| :::no-loc text="Total Connections"::: (`total-connections`) | Die Gesamtzahl von Verbindungen mit dem Webserver. |
| :::no-loc text="Total TLS Handshakes"::: (`total-tls-handshakes`) | Die Gesamtzahl von TLS-Handshakes mit dem Webserver. |

## <a name="systemnethttp-counters"></a>System.Net.Http-Zähler

Die folgenden Zähler werden vom HTTP-Stapel veröffentlicht.  Sie sind nur in .NET 5 und höher verfügbar.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="Requests Started"::: (`requests-started`) | Die Anzahl der seit dem Start des Prozesses gestarteten Anforderungen |
| :::no-loc text="Requests Started Rate"::: (`requests-started-rate`) | Die Anzahl der gestarteten Anforderungen pro Updateintervall |
| :::no-loc text="Requests Failed"::: (`requests-failed`) | Die Anzahl von Anforderungen, bei denen seit dem Start des Prozesses Fehler aufgetreten sind |
| :::no-loc text="Requests Failed Rate"::: (`requests-failed-rate`) | Die Anzahl von Anforderungen pro Updateintervall, bei denen Fehler aufgetreten sind |
| :::no-loc text="Current Requests"::: (`current-requests`) | Aktuelle Anzahl aktiver HTTP-Anforderungen, die gestartet wurden, bisher aber noch nicht abgeschlossen sind, und bei denen bisher auch kein Fehler aufgetreten ist |
| :::no-loc text="Current HTTP 1.1 Connections"::: (`http11-connections-current-total`) | Die aktuelle Anzahl von HTTP 1.1-Verbindungen, die gestartet wurden, bisher aber noch nicht abgeschlossen sind, und bei denen bisher auch kein Fehler aufgetreten ist |
| :::no-loc text="Current HTTP 2.0 Connections"::: (`http20-connections-current-total`) | Die aktuelle Anzahl von HTTP 2.0-Verbindungen, die gestartet wurden, bisher aber noch nicht abgeschlossen sind, und bei denen bisher auch kein Fehler aufgetreten ist |
| :::no-loc text="HTTP 1.1 Requests Queue Duration"::: (`http11-requests-queue-duration`) | Die durchschnittliche Zeit, die sich HTTP 1.1-Anforderungen in der Anforderungswarteschlange befinden |
| :::no-loc text="HTTP 2.0 Requests Queue Duration"::: (`http20-requests-queue-duration`) | Die durchschnittliche Zeit, die sich HTTP 2.0-Anforderungen in der Anforderungswarteschlange befinden |

## <a name="systemnetnameresolution-counters"></a>System.Net.NameResolution-Zähler

Die folgenden Zähler verfolgen Metriken im Zusammenhang mit DNS-Lookups nach. Sie sind nur in .NET 5 und höher verfügbar.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="DNS Lookups Requested"::: (`dns-lookups-requested`) | Die Anzahl der seit dem Start des Prozesses angeforderten DNS-Lookups |
| :::no-loc text="Average DNS Lookup Duration"::: (`dns-lookups-duration`) | Die durchschnittlich für ein DNS-Lookup benötigte Zeit |

## <a name="systemnetsecurity-counters"></a>System.Net.Security-Zähler

Die folgenden Zähler verfolgen Metriken im Zusammenhang mit dem Transport Layer Security-Protokoll nach.  Sie sind nur in .NET 5 und höher verfügbar.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="TLS handshakes completed"::: (`tls-handshake-rate`) | Die Anzahl der abgeschlossenen TLS-Handshakes pro Updateintervall |
| :::no-loc text="Total TLS handshakes completed"::: (`total-tls-handshakes`) | Die Gesamtanzahl der seit dem Start des Prozesses abgeschlossenen TLS-Handshakes |
| :::no-loc text="Current TLS handshakes"::: (`current-tls-handshakes`) | Die aktuelle Anzahl von TLS-Handshakes, die gestartet wurden, bisher aber noch nicht abgeschlossen sind |
| :::no-loc text="Total TLS handshakes failed"::: (`failed-tls-handshakes`) | Die Gesamtzahl von TLS-Handshakes, bei denen seit dem Start des Prozesses Fehler aufgetreten sind |
| :::no-loc text="All TLS Sessions Active"::: (`all-tls-sessions-open`) | Die Anzahl aktiver TLS-Sitzungen für alle Versionen |
| :::no-loc text="TLS 1.0 Sessions Active"::: (`tls10-sessions-open`) | Die Anzahl aktiver TLS 1.0-Sitzungen |
| :::no-loc text="TLS 1.1 Sessions Active"::: (`tls11-sessions-open`) | Die Anzahl aktiver TLS 1.1-Sitzungen |
| :::no-loc text="TLS 1.2 Sessions Active"::: (`tls12-sessions-open`) | Die Anzahl aktiver TLS 1.2-Sitzungen |
| :::no-loc text="TLS 1.3 Sessions Active"::: (`tls13-sessions-open`) | Die Anzahl aktiver TLS 1.3-Sitzungen |
| :::no-loc text="TLS Handshake Duration"::: (`all-tls-handshake-duration`) | Die durchschnittliche Dauer aller TLS-Handshakes |
| :::no-loc text="TLS 1.0 Handshake Duration"::: (`tls10-handshake-duration`) | Die durchschnittliche Dauer von TLS 1.0-Handshakes |
| :::no-loc text="TLS 1.1 Handshake Duration"::: (`tls11-handshake-duration`) | Die durchschnittliche Dauer von TLS 1.1-Handshakes |
| :::no-loc text="TLS 1.2 Handshake Duration"::: (`tls12-handshake-duration`) | Die durchschnittliche Dauer von TLS 1.2-Handshakes |
| :::no-loc text="TLS 1.3 Handshake Duration"::: (`tls13-handshake-duration`) | Die durchschnittliche Dauer von TLS 1.3-Handshakes |

## <a name="systemnetsockets-counters-available-on-net-5-and-later-versions"></a>System.Net.Sockets-Zähler (nur in .NET 5 und höher verfügbar)

Die folgenden Zähler verfolgen Metriken im Zusammenhang mit <xref:System.Net.Sockets.Socket> nach.

| Leistungsindikator | BESCHREIBUNG |
|--|--|
| :::no-loc text="Outgoing Connections Established"::: (`outgoing-connections-established`) | Die Gesamtanzahl ausgehender Verbindungen, die seit dem Start des Prozesses hergestellt wurden |
| :::no-loc text="Incoming Connections Established"::: (`incoming-connections-established`) | Die Gesamtanzahl eingehender Verbindungen, die seit dem Start des Prozesses hergestellt wurden |
| :::no-loc text="Bytes Received"::: (`bytes-received`) | Die Gesamtanzahl von Bytes, die seit dem Start des Prozesses empfangen wurden |
| :::no-loc text="Bytes Sent"::: (`bytes-sent`) | Die Gesamtanzahl von Bytes, die seit dem Start des Prozesses gesendet wurden |
| :::no-loc text="Datagrams Received"::: (`datagrams-received`) | Die Gesamtanzahl von Datagrammen, die seit dem Start des Prozesses empfangen wurden |
| :::no-loc text="Datagrams Sent"::: (`datagrams-sent`) | Die Gesamtanzahl von Datagrammen, die seit dem Start des Prozesses gesendet wurden |
