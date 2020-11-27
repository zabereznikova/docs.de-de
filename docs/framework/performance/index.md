---
title: .NET Framework-Leistung
description: Entwerfen und planen Sie die Leistung in ihren .net-apps. Verwenden Sie die von Microsoft bereitgestellten Tools, um die Leistung Ihrer APP zu messen und Verbesserungen vorzunehmen.
ms.date: 03/30/2017
helpviewer_keywords:
- performance [.NET Framework]
- reliability [.NET Framework]
ms.assetid: c1676cca-3f1a-41ec-b469-9029566074fc
ms.openlocfilehash: f15cd9b38285e88dac727bcfe51c8dc542a735f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277984"
---
# <a name="net-framework-performance"></a>.NET Framework-Leistung

Wenn Sie sehr leistungsfähige Apps erstellen möchten, sollten Sie ebenso leistungsorientiert entwerfen und planen, wie Sie jede andere Funktion der App entwerfen würden. Sie können die von Microsoft bereitgestellten Tools verwenden, um die Leistung der App zu messen und gegebenenfalls Verbesserungen der Arbeitsspeichernutzung, des Codedurchsatzes und der Reaktionsfähigkeit vorzunehmen. In diesem Thema werden die von Microsoft bereitgestellten Leistungsanalysetools aufgelistet sowie Links zu anderen Themen bereitgestellt, die die Leistung für bestimmte Bereiche der App-Entwicklung behandeln.  
  
## <a name="designing-and-planning-for-performance"></a>Leistungsorientiertes Entwerfen und Planen  

 Wenn Sie eine sehr leistungsfähige App entwickeln möchten, müssen Sie die Leistung beim Entwurf der App wie beim Entwurf jeder anderen Funktion berücksichtigen. Sie sollten die leistungskritischen Szenarien in der App bestimmen, Leistungsziele festlegen sowie frühzeitig und häufig die Leistung für diese App-Szenarien messen. Da jede App anders ist und unterschiedliche leistungskritische Ausführungspfade aufweist, können Sie durch die frühzeitiges Bestimmen dieser Pfade und die Konzentration Ihrer Arbeit darauf die Produktivität maximieren.  
  
 Sie müssen mit der Zielplattform nicht vollständig vertraut sein, um eine leistungsstarke App zu erstellen. Sie sollten jedoch ein Verständnis dafür entwickeln, welche Teile der Zielplattform die Leistung beeinträchtigen können. Hierzu können Sie die Leistung frühzeitig im Entwicklungsprozess messen.  
  
 Berücksichtigen Sie stets die Benutzerfreundlichkeit, um die für die Leistung entscheidenden Bereiche zu bestimmen und die Leistungsziele zu erreichen. Startzeit und Reaktionsfähigkeit sind zwei wesentliche Bereiche, die sich darauf auswirken, wie die App von Benutzern wahrgenommen wird. Wenn die App viel Arbeitsspeicher verwendet, könnte sie dem Benutzer langsam erscheinen oder andere auf dem System ausgeführte Apps beeinträchtigen. In einigen Fällen könnte auch die Windows Store- oder Windows Phone Store-Übermittlung fehlschlagen. Wenn Sie zudem bestimmen, welche Teile des Codes häufiger ausgeführt werden, können Sie sicherstellen, dass diese Teile des Codes gut optimiert sind.  
  
## <a name="analyzing-performance"></a>Analysieren der Leistung  

 Legen Sie als Teil des Gesamtentwicklungsplans Zeitpunkte während der Entwicklung fest, an denen Sie die Leistung der App messen und die Ergebnisse mit den früher festgelegten Zielen vergleichen. Messen Sie die Leistung der App in der Umgebung und mit der Hardware, von denen Sie annehmen, dass die Benutzer sie verwenden. Wenn Sie die Leistung der App frühzeitig und häufig analysieren, können Sie architekturbezogene Entscheidungen ändern, deren Korrektur später im Entwicklungszyklus aufwendig und teuer wäre. In den folgenden Abschnitten werden Leistungstools beschrieben, mit denen Sie Ihre Apps analysieren können. Außerdem wird die von diesen Tools verwendete Ereignisablaufverfolgung erläutert.  
  
### <a name="performance-tools"></a>Leistungstools  

 Im Folgenden werden einige Leistungstools aufgeführt, die Sie für .NET Framework-Apps verwenden können.  
  
|Tool|BESCHREIBUNG|  
|----------|-----------------|  
|Visual Studio-Leistungsanalyse|Verwenden Sie dieses Tool, um die CPU-Auslastung durch die .NET Framework-Apps zu analysieren, die auf Computern bereitgestellt werden, auf denen das Betriebssystem Windows ausgeführt wird.<br /><br /> Dieses Tool ist in Visual Studio im Menü **Debuggen** verfügbar, nachdem Sie ein Projekt geöffnet haben. Weitere Informationen finden Sie unter [Leistungs-Explorer](/visualstudio/profiling/performance-explorer). **Hinweis:** Verwenden Sie Windows Phone Application Analysis (siehe folgende Zeile), wenn Sie für Windows Phone entwickeln.|  
|Windows Phone Application Analysis|Verwenden Sie dieses Tool, um die CPU und den Arbeitsspeicher, die Netzwerkdatenübertragungsrate, die App-Reaktionsfähigkeit und den Akkuenergieverbrauch in Windows Phone-Apps zu analysieren.<br /><br /> Dieses Tool ist in Visual Studio für ein Windows Phone-Projekt im Menü **Debuggen** verfügbar, nachdem Sie das [Windows Phone SDK](https://go.microsoft.com/fwlink/?LinkId=265773) installiert haben. Weitere Informationen finden Sie unter [App-Profilerstellung für Windows Phone 8](/previous-versions/windows/apps/jj215908(v=vs.105)).|  
|[PerfView](https://www.microsoft.com/download/details.aspx?id=28567)|Verwenden Sie dieses Tool, um Leistungsprobleme bezüglich der CPU und des Arbeitsspeichers zu identifizieren. Dieses Tool verwendet die Ereignisablaufverfolgung für Windows (Event Tracing for Windows, ETW) und CLR-Profilerstellungs-APIs für erweiterte Überprüfungen des Arbeitsspeichers und der CPU sowie zum Bereitstellen von Informationen zur Garbage Collection und zur JIT-Kompilierung. Weitere Informationen zur Verwendung von PerfView finden Sie im Tutorial und in den Hilfedateien, die in der App enthalten sind, in [Channel 9-Videotutorials](https://channel9.msdn.com/Series/PerfView-Tutorial) und in [Blogbeiträgen](/archive/blogs/vancem/).<br /><br /> Informationen zu arbeitsspeicherspezifischen Problemen finden Sie unter [Using PerfView for Memory Investigations (Verwenden von PerfView für die Untersuchung des Arbeitsspeichers)](https://channel9.msdn.com/Series/PerfView-Tutorial/PerfView-Tutorial-9-NET-Memory-Investigation-Basics-of-GC-Heap-Snapshots).|  
|[Windows Performance Analyzer](https://www.microsoft.com/p/windows-performance-analyzer/9n0w1b2bxgnz?activetab=pivot:overviewtab)|Verwenden Sie dieses Tool, um die Gesamtsystemleistung zu bestimmen, beispielsweise die Arbeitsspeicher- und Speichernutzung der App, wenn mehrere Apps auf demselben Computer ausgeführt werden. Dieses Tool ist im Download Center als Teil des Windows Assessment and Deployment Kit (ADK) für Windows 8 verfügbar. Weitere Informationen finden Sie unter [Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer).|
  
### <a name="event-tracing-for-windows-etw"></a>Ereignisablaufverfolgung für Windows (ETW)  

 ETW ist eine Technik, mit der Sie Diagnoseinformationen zu ausgeführtem Code abrufen können und die für viele der vorgenannten Leistungstools wesentlich ist. Mit ETW werden Protokolle erstellt, wenn bestimmte Ereignisse durch .NET Framework-Apps und Windows ausgelöst werden. Mit ETW können Sie die Protokollierung dynamisch aktivieren und deaktivieren, sodass Sie eine ausführliche Ablaufverfolgung in einer Produktionsumgebung ausführen können, ohne die Anwendung neu zu starten. .NET Framework bietet Unterstützung für ETW-Ereignisse, und ETW wird von vielen Profilerstellungs- und Leistungstools verwendet, um Leistungsdaten zu generieren. Diese Tools aktivieren und deaktivieren häufig ETW-Ereignisse, sodass es hilfreich ist, wenn Sie mit diesen vertraut sind. Sie können bestimmte ETW-Ereignisse verwenden, um Leistungsdaten über bestimmte Komponenten der App zu sammeln. Weitere Informationen zur Unterstützung von ETW im .NET Framework finden Sie unter [ETW Events in the Common Language Runtime (ETW-Ereignisse in der Common Language Runtime)](etw-events-in-the-common-language-runtime.md) und [ETW Events in Task Parallel Library and PLINQ (ETW-Ereignisse in der Task Parallel Library und PLINQ)](etw-events-in-task-parallel-library-and-plinq.md).  
  
## <a name="performance-by-app-type"></a>Leistung nach App-Typ  

 Für jeden Typ von .NET Framework-App gibt es eigene bewährte Methoden, Überlegungen und Tools für die Auswertung der Leistung. Die folgende Tabelle enthält Links zu den Leistungsthemen für bestimmte .NET Framework-App-Typen.  
  
|App-Typ|Siehe|  
|--------------|---------|  
|.NET Framework-Apps für alle Plattformen|[Garbage Collection und Leistung](../../standard/garbage-collection/performance.md)<br /><br /> [Leistungstipps](performance-tips.md)|  
|Windows 8. x Store-Apps, die in C++, c# und Visual Basic geschrieben sind|[Performance best practices for Windows Store apps using C++, C#, and Visual Basic (Bewährte Methoden zur Leistungssteigerung für Windows Store-Apps mit C++, C# und Visual Basic)](/previous-versions/windows/apps/hh750313(v=win.10))|  
|Windows Presentation Foundation (WPF)|[WPF Performance Suite](/previous-versions/dotnet/netframework-4.0/aa969767(v=vs.100))|  
|ASP.NET|[ASP.NET Performance Overview (Die Leistung von ASP.NET im Überblick)](/previous-versions/aspnet/cc668225(v=vs.100))|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|BESCHREIBUNG|  
|-----------|-----------------|  
|[Caching in .NET Framework-Anwendungen](caching-in-net-framework-applications.md)|Beschreibt Techniken zum Zwischenspeichern von Daten, um die Leistung der Anwendung zu verbessern.|  
|[Verzögerte Initialisierung](lazy-initialization.md)|Beschreibt, wie Objekte bei Bedarf initialisiert werden, um die Leistung, insbesondere beim App-Start, zu verbessern.|  
|[Zuverlässigkeit](reliability.md)|Stellt Informationen zum Verhindern von asynchronen Ausnahmen in einer Serverumgebung bereit.|  
|[Schreiben großer, reaktionsfähiger .NET Framework-Apps](writing-large-responsive-apps.md)|Gibt Tipps zur Verbesserung der Leistung aus dem Umschreiben der C#- und Visual Basic-Compiler in verwalteten Code und enthält echte Beispiele aus dem C#-Compiler.|
