---
title: "Behandeln und Auslösen von Ausnahmen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: c3b47e61da914ebbe1106fcf45465a13b0521bb4
ms.lasthandoff: 04/08/2017

---
# <a name="handling-and-throwing-exceptions"></a>Behandeln und Auslösen von Ausnahmen
<a name="top"></a>Anwendungen müssen in der Lage sein, Fehler zu behandeln, die während der Ausführung konsistent auftreten. Die Common Language Runtime (CLR) verfügt über ein Modell zur einheitlichen Fehlerbenachrichtigung für Anwendungen. Alle Vorgänge in .NET Framework geben  Fehler durch Auslösen von Ausnahmen an.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Ausnahmen in .NET Framework](#exceptions_in_the_net_framework)  
  
-   [Ausnahmen vs.  herkömmliche Fehlerbehandlungsmethoden](#exceptions_vs_traditional_errorhandling_methods)  
  
-   [Verwalten von Ausnahmen durch die Laufzeit](#how_the_runtime_manages_exceptions)  
  
-   [Filtern von Laufzeitausnahmen](#filtering_runtime_exceptions)  
  
-   [Verwandte Themen](#related_topics)  
  
-   [Referenz](#reference)  
  
<a name="exceptions_in_the_net_framework"></a>   
## <a name="exceptions-in-the-net-framework"></a>Ausnahmen in .NET Framework  
 Bei einer Ausnahme handelt es sich um einen Fehlerzustand oder unerwartetes Verhalten beim Ausführen eines Programms. Ausnahmen können durch Fehler in Ihrem oder aufgerufenem Code (z. B. bei freigegebenen Bibliotheken), nicht verfügbare Betriebssystemressourcen, unerwartete, von der CLR (Common Language Runtime) festgestellte Fehlerzustände (z. B. durch nicht überprüfbaren Code) und andere Ereignisse ausgelöst werden. Anwendungen können in einigen, aber nicht allen Fällen wiederhergestellt werden. Obwohl bei den meisten Anwendungsausnahmen eine Wiederherstellung möglich ist, ist dies beim Großteil der Laufzeitausnahmen nicht der Fall.  
  
 In .NET Framework stellt eine Ausnahme ein Objekt dar, das von der <xref:System.Exception?displayProperty=fullName>-Klasse erbt. Eine Ausnahme wird in einem Codebereich ausgelöst, in dem ein Fehler aufgetreten ist. Die Ausnahme bleibt solange im Stapel, bis sie durch die Anwendung behandelt oder das Programm beendet wird.  
  
 [Zurück zum Anfang](#top)  
  
<a name="exceptions_vs_traditional_errorhandling_methods"></a>   
## <a name="exceptions-vs-traditional-error-handling-methods"></a>Ausnahmen vs. herkömmliche Fehlerbehandlungsmethoden  
 Herkömmliche Modelle der Fehlerbehandlung in Sprachen beruhten bisher entweder auf eigenen sprachenabhängigen Methoden der Fehlererkennung und -behandlung oder auf dem Fehlerbehandlungsmechanismus des Betriebssystems. Die Laufzeit implementiert eine Ausnahmebehandlung mit folgenden Merkmalen:  
  
-   Behandelt Ausnahmen ohne Berücksichtigung der Sprache, die die Ausnahme generiert oder behandelt.  
  
-   Eine besondere Sprachsyntax ist für die Ausnahmebehandlung nicht erforderlich, trotzdem kann jede Sprache ihre eigene Syntax definieren.  
  
-   Ausnahmen können prozess- und sogar computerübergreifend ausgelöst werden.  
  
 Ausnahmen bieten verschiedene Vorteile gegenüber anderen Methoden zur Fehlerbenachrichtigung, z. B. Rückgabecodes. Fehler können nicht unerkannt bleiben. Ungültige Werte werden im System nicht mehr weitergegeben. Sie müssen keine Rückgabecodes überprüfen. Der Ausnahmebehandlungscode kann leicht erweitert werden, um die Programmzuverlässigkeit zu erhöhen. Und schließlich ist die Ausnahmebehandlung der Laufzeit schneller als die auf Windows basierende C++-Fehlerbehandlung.  
  
 Da Ausführungsthreads üblicherweise verwaltete und nicht verwaltete Codeblöcke abarbeiten, können Ausnahmen durch die Laufzeit entweder in verwaltetem oder nicht verwaltetem Code ausgelöst und abgefangen werden. Nicht verwalteter Code kann sowohl SEH-Ausnahmen im C++-Format als auch COM-basierte HRESULTS enthalten.  
  
<a name="how_the_runtime_manages_exceptions"></a>   
## <a name="how-the-runtime-manages-exceptions"></a>Verwalten von Ausnahmen durch die Laufzeit  
 Die Laufzeit verwendet ein auf Ausnahmeobjekten und geschützten Codeblöcken basierendes Modell der Ausnahmebehandlung. Ein <xref:System.Exception>-Objekt wird zur Darstellung einer auftretenden Ausnahme erstellt.  
  
 Durch die Laufzeit wird eine Tabelle mit Ausnahmeinformationen für jede ausführbare Datei erstellt. Jeder Methode einer ausführbaren Datei wird in dieser Tabelle ein (ggf. leeres) Array mit Informationen zur Ausnahmebehandlung zugeordnet. Jeder Eintrag in diesem Array beschreibt einen geschützten Codeblock, alle mit diesem Code verknüpften Ausnahmefilter und alle Ausnahmehandler (`catch`-Anweisungen). Die Ausnahmetabelle ist sehr effizient und führt nicht zu Leistungseinbußen bei der Prozessorzeit oder Speichernutzung, wenn eine Ausnahme nicht auftritt. Nur bei Auftreten einer Ausnahme werden Systemressourcen in Anspruch genommen.  
  
 Die Ausnahmetabelle enthält vier Typen von Ausnahmehandlern für geschützte Blöcke:  
  
-   Ein `finally`-Handler wird immer ausgeführt, wenn der Block durch die normale Ablaufsteuerung oder eine unbehandelte Ausnahme beendet wird.  
  
-   Ein fault-Handler wird immer beim Auftreten einer Ausnahme ausgeführt, aber nicht nach Abschluss der normalen Ablaufsteuerung.  
  
-   Ein typgefilterter Handler behandelt alle Ausnahmen einer angegebenen Klasse oder einer davon abgeleiteten Klasse.  
  
-   Ein benutzergefilterter Handler führt benutzerdefinierten Code aus, um zu entscheiden, ob die Ausnahme vom zugeordneten Handler behandelt oder dem nächsten geschützten Block übergeben wird.  
  
 Jede Sprache implementiert diese Ausnahmehandler entsprechend ihrer Spezifikationen. Visual Basic bietet zum Beispiel Zugriff auf den benutzergefilterten Handler über einen Variablenvergleich in der `catch`-Anweisung (mit dem `When`-Schlüsselwort). In C# dagegen kann dieser Handler nicht implementiert werden.  
  
 Tritt eine Ausnahme auf, führt die Laufzeit die beiden folgenden Schritte durch:  
  
1.  Die Laufzeit durchsucht das Array nach dem ersten geschützten Block, der folgende Eigenschaften besitzt:  
  
    -   Schützt einen Bereich, der die gerade ausgeführte Anweisung enthält.  
  
    -   Enthält einen Ausnahmehandler oder einen Filter zur Ausnahmebehandlung.  
  
2.  Im Fall einer Übereinstimmung wird von der Laufzeit ein <xref:System.Exception>-Objekt erstellt, das die Ausnahme beschreibt. Daraufhin werden alle `finally`- oder fault-Anweisungen zwischen der Anweisung, bei der die Ausnahme auftrat, und derjenigen, die sie behandelt, ausgeführt. Die Reihenfolge der Ausnahmehandler ist wichtig: Der innerste Ausnahmehandler wird zuerst ausgewertet. Beachten Sie außerdem, dass Ausnahmehandler auf lokale Variablen und lokalen Arbeitsspeicher der Routine zugreifen können, durch die die Ausnahme abgefangen wurde, aber alle Zwischenwerte zum Zeitpunkt des Auslösens der Ausnahme verloren gehen.  
  
     Enthält die aktuelle Methode keine Übereinstimmungen, durchsucht die Laufzeit jeden Aufrufer der aktuellen Methode und verfährt so weiter für den ganzen Stapel. Gibt es bei keinem Aufrufer eine Übereinstimmung, wird dem Debugger der Zugriff auf die Ausnahme gestattet. Wenn die Ausnahme durch den Debugger nicht behandelt wird, löst die CLR das <xref:System.AppDomain.UnhandledException?displayProperty=fullName>-Ereignis aus. Sind keine Listener für dieses Ereignis vorhanden, gibt die Laufzeit eine Stapelüberwachung aus und beendet die Anwendung.  
  
 [Zurück zum Anfang](#top)  
  
<a name="filtering_runtime_exceptions"></a>   
## <a name="filtering-runtime-exceptions"></a>Filtern von Laufzeitausnahmen  
 Sie können die abgefangenen Ausnahmen filtern und entweder nach Typ oder nach benutzerdefinierten Kriterien behandeln.  
  
 Typgefilterte Handler verwalten einen bestimmten Ausnahmetyp (oder davon abgeleitete Klassen). Das folgende Beispiel zeigt einen typgefilterten Handler, der für das Erfassen einer bestimmten Ausnahme konzipiert ist, in diesem Fall <xref:System.IO.FileNotFoundException>.  
  
 [!code-cpp[CatchException#5](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception3.cpp#5)]
 [!code-csharp[CatchException#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception3.cs#5)]
 [!code-vb[CatchException#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception3.vb#5)]  
  
 Benutzergefilterte Handler fangen und behandeln Ausnahmen gemäß benutzerdefinierten Ausnahmeanforderungen. Weitere Informationen über das Filtern von Ausnahmen mit dieser Methode finden Sie unter [Verwenden spezifischer Ausnahmen in einem Catch-Block](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md).  
  
 [Zurück zum Anfang](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Exception-Klasse und Exception-Eigenschaften](../../../docs/standard/exceptions/exception-class-and-properties.md)|Beschreibt die Elemente eines Ausnahmeobjekts.|  
|[Ausnahmenhierarchie](../../../docs/standard/exceptions/exception-hierarchy.md)|Beschreibt die grundlegendsten Ausnahmen.|  
|[Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)|Erläutert das Behandeln von Ausnahmen mit den catch-, throw- und finally-Anweisungen.|  
|[Bewährte Methoden für Ausnahmen](../../../docs/standard/exceptions/best-practices-for-exceptions.md)|Beschreibt empfohlene Methoden zur Ausnahmebehandlung.|  
|[Behandeln von COM-Interop-Ausnahmen](../../../docs/standard/exceptions/handling-com-interop-exceptions.md)|Erläutert die Behandlung von Ausnahmen, die in nicht verwaltetem Code ausgelöst und abgefangen wurden.|  
|[Gewusst wie: Zuordnen von HRESULTs und Ausnahmen](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)|Erläutert die Zuordnung von Ausnahmen bei Übergängen zwischen verwaltetem und nicht verwaltetem Code.|  
  
<a name="reference"></a>   
## <a name="reference"></a>Verweis  
 <xref:System.Exception?displayProperty=fullName>  
  
 <xref:System.ApplicationException?displayProperty=fullName>  
  
 <xref:System.SystemException?displayProperty=fullName>
