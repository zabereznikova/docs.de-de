---
title: "Ablaufverfolgung und Instrumentieren von Anwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Ablaufverfolgung [.NET Framework]"
  - "Debuggen [.NET Framework], instrumentation"
  - "leistungsüberwachungsinstrumentation,"
  - "Instrumentation, Informationen über die Instrumentierung"
  - "Ablaufverfolgung [.NET Framework], zum Verfolgen"
  - "Leistung überwachen, Rückverfolgen von code"
  - "Instrumentierung für Trace-Klasse"
ms.assetid: 773b6fc4-9013-4322-b728-5dec7a72e743
caps.latest.revision: 21
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 21
---
# Ablaufverfolgung und Instrumentieren von Anwendungen
Mithilfe der Ablaufverfolgung kann die Ausführung einer Anwendung überwacht werden. Beim Entwickeln können Sie eine .NET Framework-Anwendung mit einer Ablaufverfolgungs- und Debugginginstrumentierung versehen, die sowohl beim Entwickeln als auch nach der Bereitstellung der Anwendung eingesetzt werden kann. Sie können die <xref:System.Diagnostics.Trace?displayProperty=fullName>, <xref:System.Diagnostics.Debug?displayProperty=fullName>, und <xref:System.Diagnostics.TraceSource?displayProperty=fullName> Klassen Informationen zu Fehlern und zur anwendungsausführung in Protokollen, Textdateien oder anderen Geräten für die spätere Analyse aufzeichnen.  
  
 Der Begriff *Instrumentation* bezeichnet die Fähigkeit zu überwachen oder die Leistung eines Produkts messen und Fehler zu diagnostizieren. In der Programmierung versteht man darunter die Fähigkeit eines Programms, folgende Funktionen zu bieten:  
  
-   **Codeablaufverfolgung** – erhalten informativer Meldungen über die Ausführung einer Anwendung zur Laufzeit.  
  
-   **Debuggen von** – ermitteln und Beheben von Programmierfehlern in einer Anwendung während der Entwicklungsphase. Weitere Informationen finden Sie unter [Debuggen](../Topic/Debugging%20in%20Visual%20Studio.md).  
  
-   **Leistungsindikatoren für** -Komponenten, die Sie zum Überwachen der Leistung der Anwendung ermöglichen. Weitere Informationen finden Sie unter [Leistungsindikatoren](../../../docs/framework/debug-trace-profile/performance-counters.md).  
  
-   **Ereignisprotokolle** -Komponenten, die Sie empfangen, und verfolgen Sie wichtige Ereignisse während der Ausführung der Anwendung. Weitere Informationen finden Sie unter der <xref:System.Diagnostics.EventLog> Klasse.  
  
 Das Instrumentieren einer Anwendung durch Platzieren von Ablaufverfolgungsanweisungen an strategischen Codestellen ist vor allem bei verteilten Anwendungen nützlich. Mithilfe von Ablaufverfolgungsanweisungen können Sie eine Anwendung so instrumentieren, dass nicht nur Informationen zu Fehlern angezeigt werden, sondern auch die Leistung der Anwendung überwacht wird.  
  
 Die <xref:System.Diagnostics.TraceSource> -Klasse stellt erweiterte Funktionen zur Ablaufverfolgung und kann verwendet werden, anstelle der statischen Methoden der älteren <xref:System.Diagnostics.Trace> und <xref:System.Diagnostics.Debug> Ablaufverfolgungsklassen. Die vertraute <xref:System.Diagnostics.Trace> und <xref:System.Diagnostics.Debug> Klassen werden weiterhin häufig verwendet, aber die <xref:System.Diagnostics.TraceSource> Klasse empfiehlt sich für neue Ablaufverfolgungsbefehle, z. B. <xref:System.Diagnostics.TraceSource.TraceEvent%2A> und <xref:System.Diagnostics.TraceSource.TraceData%2A>.  
  
 Die <xref:System.Diagnostics.Trace> und <xref:System.Diagnostics.Debug> Klassen sind nahezu identisch, außer die Prozeduren und Funktionen von der <xref:System.Diagnostics.Trace> -Klasse werden standardmäßig in Releasebuilds, sondern nach der kompiliert die <xref:System.Diagnostics.Debug> -Klasse sind.  
  
 Die <xref:System.Diagnostics.Trace> und <xref:System.Diagnostics.Debug> Klassen bieten die Möglichkeit, überwachen und untersuchen die Leistung der Anwendung während der Entwicklung oder nach der Bereitstellung. Beispielsweise können Sie die <xref:System.Diagnostics.Trace> Klasse, um bestimmte Typen von Aktionen in einer bereitgestellten Anwendung nachzuverfolgen, sobald sie (z. B. die Erstellung neuer Datenbankverbindungen auftreten), und können somit die Effizienz der Anwendung überwachen.  
  
## <a name="code-tracing-and-debugging"></a>Ablaufverfolgung und Debuggen von Code  
 Während der Entwicklung können Sie die Ausgabemethoden der der <xref:System.Diagnostics.Debug> Klasse, um Nachrichten von der integrierten Entwicklungsumgebung (IDE) von Visual Studio im Ausgabefenster angezeigt. Zum Beispiel:  
  
```vb  
Trace.WriteLine("Hello World!")  
Debug.WriteLine("Hello World!")  
  
```  
  
```csharp  
System.Diagnostics.Trace.WriteLine("Hello World!");  
System.Diagnostics.Debug.WriteLine("Hello World!");  
  
```  
  
 Jedes dieser Beispiele wird "Hello World!" angezeigt. im Ausgabefenster angezeigt, wenn die Anwendung im Debugger ausgeführt wird.  
  
 So können Sie Anwendungen anhand ihres Verhaltens in der Testumgebung debuggen und ihre Leistung optimieren. Debuggen Sie Ihre Anwendung im Debugbuild mit der <xref:System.Diagnostics.Debug> conditional-Attribut aktiviert, sodass Sie die gesamte Debugausgabe erhalten. Wenn Ihre Anwendung zur Freigabe bereit ist, können Sie den Releasebuild kompilieren, ohne Einschalten der <xref:System.Diagnostics.Debug> bedingte Attribut, damit der Compiler nicht den Debugcode in die endgültige ausführbare Version aufnimmt. Weitere Informationen finden Sie unter [wie: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md). Weitere Informationen zu verschiedenen Buildkonfigurationen für die Anwendung finden Sie unter [kompilieren und Erstellen von](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md).  
  
 Sie können auch verfolgen die Ausführung von Code in einer installierten Anwendung mit den Methoden der der <xref:System.Diagnostics.Trace> Klasse. Durch die Platzierung [Ablaufverfolgungsschalter](../../../docs/framework/debug-trace-profile/trace-switches.md) in Ihrem Code können Sie steuern, ob die Protokollierung erfolgt und wie umfangreich ist. Dadurch können Sie den Status der Anwendung in einer Produktionsumgebung überwachen. Dies ist vor allem bei Businessanwendungen wichtig, die aus mehreren Komponenten bestehen, die ihrerseits auf mehreren Computern ausgeführt werden. Über die Konfigurationsdatei steuern Sie die Verwendung der Schalter nach der Bereitstellung. Weitere Informationen finden Sie unter [Gewusst wie: erstellen, initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md).  
  
 Beim Entwickeln einer Anwendung, in der Ablaufverfolgung möglich sein soll, werden in der Regel Verfolgungs- und Debugmeldungen in den Anwendungscode eingetragen. Wenn Sie die Anwendung bereitstellen möchten, können Sie den Releasebuild kompilieren, ohne Einschalten der **Debuggen** conditional-Attribut. Sie können jedoch aktivieren, auf die **Trace** bedingte Attribut, damit der Compiler den Ablaufverfolgungscode in die ausführbare Datei einträgt. Weitere Informationen finden Sie unter [wie: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).  
  
### <a name="phases-of-code-tracing"></a>Phasen der Codeablaufverfolgung  
 Die Codeablaufverfolgung umfasst die folgenden drei Phasen:  
  
1.  **Instrumentation** – Verfolgungscode wird der Anwendung hinzugefügt.  
  
2.  **Tracing** – der Verfolgungscode schreibt Informationen in das angegebene Ziel.  
  
3.  **Analyse** – zum Identifizieren und verstehen Probleme in der Anwendung die Ablaufverfolgungsinformationen werden ausgewertet.  
  
 Während der Entwicklung schreiben alle Debug- und Ablaufverfolgungsausgabemethoden standardmäßig Informationen in das Ausgabefenster in Visual Studio. In einer bereitgestellten Anwendung schreiben die Methoden die Ablaufverfolgungsinformationen in die von Ihnen angegebenen Ziele. Weitere Informationen zum Angeben von ein Ausgabeziel für die Ablaufverfolgung oder Debuggen, finden Sie unter [Ablaufverfolgungslistener](../../../docs/framework/debug-trace-profile/trace-listeners.md).  
  
 Im Folgenden finden Sie einen allgemeinen Überblick über die wichtigsten Schritte, die normalerweise bei der Analyse und Behebung potenzieller Probleme in bereitgestellten Anwendungen mithilfe der Ablaufverfolgung durchzuführen sind. Weitere Informationen zur Durchführung dieser Schritte finden Sie unter dem entsprechenden Link.  
  
##### <a name="to-use-tracing-in-an-application"></a>So verwenden Sie die Ablaufverfolgung in einer Anwendung  
  
1.  Überlegen Sie, welche Ablaufverfolgungsausgabe nach der Bereitstellung der Anwendung an ihrem Einsatzort benötigt wird.  
  
2.  Erstellen Sie eine Reihe von Schaltern. Weitere Informationen finden Sie unter [Gewusst wie: Konfigurieren von Ablaufverfolgungsschaltern](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md).  
  
3.  Fügen Sie die Ablaufverfolgungsanweisungen zum Anwendungscode hinzu.  
  
4.  Bestimmen Sie, wo die Ablaufverfolgungsausgabe angezeigt werden soll, und fügen Sie die entsprechenden Listener hinzu. Weitere Informationen finden Sie unter [erstellen und Initialisieren von Ablaufverfolgungslistenern](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-listeners.md).  
  
5.  Testen und debuggen Sie die Anwendung und den darin enthaltenen Ablaufverfolgungscode.  
  
6.  Kompilieren Sie die Anwendung mit einem der folgenden Verfahren in ausführbaren Code:  
  
    -   Verwenden der **erstellen** Menü zusammen mit der **Debuggen** auf der Seite der **Eigenschaftenseiten** im Dialogfeld **Projektmappen-Explorer**. Dies gilt für die Kompilierung in Visual Studio.  
  
         \- oder –  
  
    -   Verwenden der **Ablaufverfolgung** und **Debuggen** Compiler-Direktiven für die Befehlszeile kompilieren. Weitere Informationen finden Sie unter [Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md). Dies gilt für die Kompilierung von der Befehlszeile aus.  
  
7.  Aktivieren Sie den entsprechenden Ablaufverfolgungsschalter, wenn zur Laufzeit ein Problem auftritt. Weitere Informationen finden Sie unter [Konfigurieren von Ablaufverfolgungsschaltern](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md).  
  
     Der Ablaufverfolgungscode schreibt Ablaufverfolgungsmeldungen in ein angegebenes Ziel, z. B. einen Bildschirm, eine Textdatei oder ein Ereignisprotokoll. Der Typ des Listeners, die Sie, in enthalten der **Trace.Listeners** Auflistung bestimmt das Ziel.  
  
8.  Analysieren Sie die Ablaufverfolgungsmeldungen, um das Problem in der Anwendung zu ermitteln und zu verstehen.  
  
## <a name="trace-instrumentation-and-distributed-applications"></a>Instrumentation der Ablaufverfolgung und verteilte Anwendungen  
 Beim Erstellen einer verteilten Anwendung ist es in der Regel schwierig, die Anwendung in der Weise zu testen, in der sie letzten Endes verwendet wird. Wenige Entwicklungsteams haben die Möglichkeit, alle möglichen Kombinationen aus Betriebsystemen oder Webbrowsern (einschließlich aller lokalisierten Sprachoptionen) zu testen oder die hohe Zahl von Benutzern zu simulieren, die gleichzeitig auf die Anwendung zugreifen. Unter diesen Umständen können Sie die Reaktion einer verteilten Anwendung auf hohes Datenaufkommen, verschiedene Setups und individuelles Endbenutzerverhalten nicht testen. Außerdem haben viele Teile einer verteilten Anwendung keine Benutzeroberfläche, über die Sie direkt mit diesen Teilen interagieren oder ihre Aktivitäten anzeigen lassen könnten.  
  
 Sie können jedoch für diese kompensieren, durch die Aktivierung der verteilten Anwendung, bestimmte Ereignisse für Systemadministratoren, insbesondere auftretende beschreiben, die von schief gehen *Instrumentierung* der Anwendung – d. h. durch Platzieren von ablaufverfolgungsanweisungen an strategischen Stellen im Code. Dadurch können Sie, wenn zur Laufzeit unerwartete Vorkommnisse auftreten (z. B. extrem langsame Reaktionszeit), die wahrscheinliche Ursache ermitteln.  
  
 Mit Ablaufverfolgungsanweisungen können Sie die schwierige Aufgabe vermeiden, den ursprünglichen Quellcode überprüfen, bearbeiten, neu kompilieren und den Laufzeitfehler in der Debugumgebung reproduzieren zu müssen. Beachten Sie, dass sich eine Anwendung nicht nur für die Anzeige von Fehlern, sondern auch für die Leistungsüberwachung instrumentieren lässt.  
  
## <a name="strategic-placement-of-trace-statements"></a>Strategische Platzierung von Ablaufverfolgungsanweisungen  
 Ablaufverfolgungsanweisungen, die zur Laufzeit eingesetzt werden sollen, müssen mit äußerster Sorgfalt platziert werden. Überlegen Sie, welche Ablaufverfolgungsinformationen in einer bereitgestellten Anwendung wahrscheinlich benötigt werden, damit alle Möglichkeiten der Ablaufverfolgung entsprechend abgedeckt werden. Allerdings gibt es keine allgemeingültigen Richtlinien für die strategische Platzierung der Ablaufverfolgung, da die Anwendungen, in denen sie eingesetzt wird, sehr vielfältig sind. Weitere Informationen zum Platzieren von ablaufverfolgungsanweisungen finden Sie unter [Gewusst wie: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md).  
  
## <a name="output-from-tracing"></a>Ausgabe der Ablaufverfolgung  
 Ablaufverfolgungsausgabe gesammelt werden, durch die Objekte mit dem Namen *Listener*. Bei einem Listener handelt es sich um ein Objekt, das die Ablaufverfolgungsausgabe empfängt und in ein Ausgabemedium schreibt (in der Regel ein Fenster, ein Protokoll oder eine Textdatei). Wenn ein Ablaufverfolgungslistener erstellt wird, wird es in der Regel hinzugefügt die <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=fullName> -Auflistung, sodass der gesamte Ablaufverfolgungsausgabe empfängt.  
  
 Ablaufverfolgungsinformationen werden immer geschrieben mindestens auf den Standardwert <xref:System.Diagnostics.Trace> Ausgabeziel, den <xref:System.Diagnostics.DefaultTraceListener>. Wenn aus irgendeinem Grund gelöscht wurde der <xref:System.Diagnostics.DefaultTraceListener> ohne andere Listener zur der <xref:System.Diagnostics.Trace.Listeners%2A> -Auflistung, erhalten Sie keine Ablaufverfolgungsmeldungen. Weitere Informationen finden Sie unter [Ablaufverfolgungslistener](../../../docs/framework/debug-trace-profile/trace-listeners.md).  
  
 Die sechs <xref:System.Diagnostics.Debug> Elemente und <xref:System.Diagnostics.Trace> Methoden, die Ablaufverfolgungsinformationen schreiben werden in der folgenden Tabelle aufgelistet.  
  
|Methode|Ausgabe|  
|------------|------------|  
|**Bestätigen**|Der angegebene Text oder, falls keiner angegeben ist, die Aufrufliste. Die Ausgabe wird nur geschrieben, wenn die Bedingung angegeben werden als Argument in der **Assert** -Anweisung ist **false**.|  
|**Ein Fehler auf**|Der angegebene Text oder, falls keiner angegeben ist, die Aufrufliste.|  
|**Schreiben**|Der angegebene Text.|  
|**WriteIf**|Der angegebene Text, wenn die Bedingung angegeben werden als Argument in der **WriteIf** -Anweisung erfüllt wird.|  
|**WriteLine**|Der angegebene Text und ein Wagenrücklaufzeichen.|  
|**WriteLineIf**|Der angegebene Text und ein Wagenrücklaufzeichen zurückzugeben, wenn die Bedingung angegeben werden als Argument in der **WriteLineIf** -Anweisung erfüllt wird.|  
  
 Alle Listener in der <xref:System.Diagnostics.Trace.Listeners%2A> -Auflistung empfangen die Meldungen in der obigen Tabelle beschrieben, doch können die ausgeführten Aktionen variieren, je nachdem, welche Art von Listener die Meldung empfängt. Z. B. die <xref:System.Diagnostics.DefaultTraceListener> zeigt das Dialogfeld Assertion, wenn er empfängt eine **fehl** oder Fehler bei **Assert** Benachrichtigung, aber ein <xref:System.Diagnostics.TextWriterTraceListener> lediglich die Ausgabe in seinen Stream schreibt.  
  
 Durch Implementieren eines eigenen Listeners können Sie benutzerdefinierte Ergebnisse erzielen. Ein benutzerdefinierter Ablaufverfolgungslistener könnte die Meldungen z. B. in einem Meldungsfeld anzeigen oder die Verbindung zu einer Datenbank herstellen, in der die Meldungen zu einer Tabelle hinzugefügt werden. Alle benutzerdefinierten Listener sollten die sechs oben genannten Methoden unterstützen. Weitere Informationen zum Erstellen entwicklerdefinierter Listener finden Sie unter <xref:System.Diagnostics.TraceListener> in der Referenz zu .NET Framework.  
  
> [!NOTE]
>  In [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], **Debug.Write**, **Debug.Write**, **Debug.WriteLine**, und **Debug.WriteLine** Methoden ersetzt die **Debug.Print** -Methode, die in früheren Versionen von Visual Basic verfügbar war.  
  
 Die **schreiben** und **WriteLine** -Methode schreiben immer dem Text, die Sie angeben. **Assert**, **WriteIf**, und **WriteLineIf** erfordern ein boolesches Argument, das steuert, ob den angegebenen Text geschrieben wird oder nicht, Schreiben sie nur, wenn der Ausdruck **true** (für **WriteIf** und **WriteLineIf**), oder **false** (für **Assert**). Die **fehl** -Methode schreibt immer den angegebenen Text. Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md) und der Referenz zu .NET Framework.  
  
## <a name="security-concerns"></a>Sicherheitsaspekte  
 Wenn Sie vor der Bereitstellung einer ASP.NET-Anwendung nicht die Ablaufverfolgung und das Debuggen deaktivieren, könnte die Anwendung Informationen über sich selbst offen legen, die von böswilligen Programmen missbraucht werden könnten. Weitere Informationen finden Sie unter [wie: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md), [kompilieren und erstellen](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md), und [Gewusst wie: erstellen, initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md). Das Debuggen kann auch über Internetinformationendienste (IIS) konfiguriert werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceSource>   
 [Codeverträge](../../../docs/framework/debug-trace-profile/code-contracts.md)   
 [C#, f# und Visual Basic-Projekttypen](../Topic/Debugging%20Preparation:%20C%23,%20F%23,%20and%20Visual%20Basic%20Project%20Types.md)   
 [Gewusst wie: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)   
 [Gewusst wie: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)   
 [Gewusst wie: erstellen, initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [Gewusst wie: Erstellen und Initialisieren von Ablaufverfolgungsquellen](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)   
 [Gewusst wie: Verwenden von TraceSource und Filtern für Ablaufverfolgungslistener](../../../docs/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md)   
 [Ablaufverfolgungslistener](../../../docs/framework/debug-trace-profile/trace-listeners.md)   
 [Trace-Schalter](../../../docs/framework/debug-trace-profile/trace-switches.md)