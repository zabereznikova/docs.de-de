---
title: Ablaufverfolgung und Instrumentieren von Anwendungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework]
- debugging [.NET Framework], instrumentation
- performance monitoring, instrumentation
- instrumentation, about instrumentation
- tracing [.NET Framework], about tracing
- performance monitoring, tracing code
- Trace class, instrumentation for .NET applications
ms.assetid: 773b6fc4-9013-4322-b728-5dec7a72e743
ms.openlocfilehash: 2dcdbaf50ed053d43fc2df2c80fe7688e7b3e51f
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542610"
---
# <a name="tracing-and-instrumenting-applications"></a>Ablaufverfolgung und Instrumentieren von Anwendungen
Die Ablaufverfolgung ist eine Möglichkeit, die Ausführung der Anwendung zu überwachen, während sie ausgeführt wird. Beim Entwickeln können Sie eine .NET Framework-Anwendung mit einer Ablaufverfolgungs- und Debugginginstrumentierung versehen, die sowohl beim Entwickeln als auch nach der Bereitstellung der Anwendung eingesetzt werden kann. Mit den Klassen <xref:System.Diagnostics.Trace?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug?displayProperty=nameWithType> und <xref:System.Diagnostics.TraceSource?displayProperty=nameWithType> können Sie Informationen zu Fehlern und zur Anwendungsausführung in Protokollen, Textdateien oder auf anderen Medien für eine spätere Analyse aufzeichnen.  
  
 Der Begriff *Instrumentierung* bezeichnet die Fähigkeit, die Leistung eines Produkts zu überwachen oder zu messen und Fehler zu diagnostizieren. In der Programmierung versteht man darunter die Fähigkeit eines Programms, folgende Funktionen zu bieten:  
  
- **Codeablaufverfolgung**: Erhalten informativer Meldungen über die Ausführung einer Anwendung zur Laufzeit.  
  
- **Debuggen**: Ermitteln und Beheben von Programmierfehlern in einer Anwendung während der Entwicklungsphase. Weitere Informationen finden Sie unter [Debuggen](/visualstudio/debugger/debugger-feature-tour).  
  
- **Leistungsindikatoren**: Komponenten zur Ermittlung der Anwendungsleistung. Weitere Informationen finden Sie unter [Performance Counters](performance-counters.md).  
  
- **Ereignisprotokolle**: Komponenten, mit denen wichtige Ereignisse während der Anwendungsausführung erhalten und nachverfolgt werden können. Weitere Informationen finden Sie im Thema zur Klasse <xref:System.Diagnostics.EventLog>.  
  
 Das Instrumentieren einer Anwendung durch Platzieren von Ablaufverfolgungsanweisungen an strategischen Codestellen ist vor allem bei verteilten Anwendungen nützlich. Mithilfe von Ablaufverfolgungsanweisungen können Sie eine Anwendung so instrumentieren, dass nicht nur Informationen zu Fehlern angezeigt werden, sondern auch die Leistung der Anwendung überwacht wird.  
  
 Die <xref:System.Diagnostics.TraceSource>-Klasse stellt erweiterte Funktionen zur Ablaufverfolgung bereit und kann anstelle der statischen Methoden der älteren Ablaufverfolgungsklassen <xref:System.Diagnostics.Trace> und <xref:System.Diagnostics.Debug> verwendet werden. Die vertrauten Klassen <xref:System.Diagnostics.Trace> und <xref:System.Diagnostics.Debug> werden weiterhin häufig verwendet, aber die <xref:System.Diagnostics.TraceSource>-Klasse wird für neue Ablaufverfolgungsbefehle, z. B. <xref:System.Diagnostics.TraceSource.TraceEvent%2A> und <xref:System.Diagnostics.TraceSource.TraceData%2A>, empfohlen.  
  
 Die <xref:System.Diagnostics.Trace>-Klasse und die <xref:System.Diagnostics.Debug>-Klasse unterscheiden sich nur in einem Punkt: Die Prozeduren und Funktionen der <xref:System.Diagnostics.Trace>-Klasse werden standardmäßig in Releasebuilds kompiliert, die der <xref:System.Diagnostics.Debug>-Klasse nicht.  
  
 Die <xref:System.Diagnostics.Trace>-Klasse und die <xref:System.Diagnostics.Debug>-Klasse ermöglichen während der Entwicklung oder nach der Bereitstellung die Überwachung und Überprüfung der Anwendungsleistung. Sie können beispielsweise die <xref:System.Diagnostics.Trace>-Klasse verwenden, um bestimmte Typen von Aktionen in einer bereitgestellten Anwendung nachzuverfolgen, während diese auftreten (z. B. die Erstellung neuer Datenbankverbindungen), und somit die Effizienz der Anwendung überwachen.  
  
## <a name="code-tracing-and-debugging"></a>Ablaufverfolgung und Debuggen von Code  
 Während der Entwicklung können Sie die Ausgabemethoden der <xref:System.Diagnostics.Debug>-Klasse verwenden, um Meldungen im Ausgabefenster der integrierten Entwicklungsumgebung (IDE) von Visual Studio anzuzeigen. Beispiel:  
  
```vb  
Trace.WriteLine("Hello World!")  
Debug.WriteLine("Hello World!")  
```  
  
```csharp  
System.Diagnostics.Trace.WriteLine("Hello World!");  
System.Diagnostics.Debug.WriteLine("Hello World!");  
```  
  
 Jedes dieser Beispiele wird „Hallo Welt!“ im Ausgabefenster anzeigen, wenn die Anwendung im Debugger ausgeführt wird.  
  
 So können Sie Anwendungen anhand ihres Verhaltens in der Testumgebung debuggen und ihre Leistung optimieren. Sie können die Anwendung im Debugbuild mit aktiviertem bedingtem <xref:System.Diagnostics.Debug>-Attribut debuggen, sodass Sie die gesamte Debugausgabe erhalten. Wenn die Anwendung zur Freigabe bereit ist, können Sie den Releasebuild kompilieren, ohne das bedingte <xref:System.Diagnostics.Debug>-Attribut zu aktivieren, damit der Compiler nicht den Debugcode in die endgültige ausführbare Version aufnimmt. Weitere Informationen finden Sie unter [Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](how-to-compile-conditionally-with-trace-and-debug.md). Weitere Informationen zu verschiedenen Buildkonfigurationen für die Anwendung finden Sie unter [Kompilieren und Erstellen](/visualstudio/ide/compiling-and-building-in-visual-studio).  
  
 Mit den Methoden der <xref:System.Diagnostics.Trace>-Klasse können Sie die Codeausführung auch in einer installierten Anwendung verfolgen. Durch die Platzierung von [Ablaufverfolgungsschaltern](trace-switches.md) in Ihrem Code können Sie steuern, ob und in welchem Umfang Ablaufverfolgung durchgeführt wird. Auf diese Weise können Sie den Status der Anwendung in einer Produktionsumgebung überwachen. Dies ist besonders wichtig in einer Geschäftsanwendung, die mehrere Komponenten auf mehreren Computern verwendet. Über die Konfigurationsdatei steuern Sie die Verwendung der Schalter nach der Bereitstellung. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](how-to-create-initialize-and-configure-trace-switches.md).  
  
 Beim Entwickeln einer Anwendung, in der Ablaufverfolgung möglich sein soll, werden in der Regel Verfolgungs- und Debugmeldungen in den Anwendungscode eingetragen. Wenn die Anwendung die Bereitstellungsphase erreicht hat, können Sie den Releasebuild kompilieren, ohne das bedingte **Debuggen**-Attribut zu aktivieren. Sie können jedoch das bedingte Attribut **Ablaufverfolgung** aktivieren, damit der Compiler den Ablaufverfolgungscode in die ausführbare Datei einträgt. Weitere Informationen finden Sie unter [Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](how-to-compile-conditionally-with-trace-and-debug.md).  
  
### <a name="phases-of-code-tracing"></a>Phasen der Codeablaufverfolgung  
 Die Codeablaufverfolgung umfasst die folgenden drei Phasen:  
  
1. **Instrumentation**: Der Verfolgungscode wird der Anwendung hinzugefügt.  
  
2. **Ablaufverfolgung**: Der Verfolgungscode schreibt Informationen in das angegebene Ziel.  
  
3. **Analyse**: Die Ablaufverfolgungsinformationen werden ausgewertet, um Probleme in der Anwendung zu ermitteln und zu verstehen.  
  
 Während der Entwicklung schreiben alle Debug- und Ablaufverfolgungsausgabemethoden standardmäßig Informationen in das Ausgabefenster in Visual Studio. In einer bereitgestellten Anwendung schreiben die Methoden die Ablaufverfolgungsinformationen in die von Ihnen angegebenen Ziele. Weitere Informationen zum Festlegen eines Ausgabeziels für die Ablaufverfolgung oder das Debuggen finden Sie unter [Ablaufverfolgungslistener](trace-listeners.md).  
  
 Im Folgenden finden Sie einen allgemeinen Überblick über die wichtigsten Schritte, die normalerweise bei der Analyse und Behebung potenzieller Probleme in bereitgestellten Anwendungen mithilfe der Ablaufverfolgung durchzuführen sind. Weitere Informationen zur Durchführung dieser Schritte finden Sie unter dem entsprechenden Link.  
  
##### <a name="to-use-tracing-in-an-application"></a>So verwenden Sie die Ablaufverfolgung in einer Anwendung  
  
1. Überlegen Sie, welche Ablaufverfolgungsausgabe nach der Bereitstellung der Anwendung an ihrem Einsatzort benötigt wird.  
  
2. Erstellen Sie eine Reihe von Schaltern. Weitere Informationen finden Sie unter [Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](how-to-create-initialize-and-configure-trace-switches.md).  
  
3. Fügen Sie die Ablaufverfolgungsanweisungen zum Anwendungscode hinzu.  
  
4. Bestimmen Sie, wo die Ablaufverfolgungsausgabe angezeigt werden soll, und fügen Sie die entsprechenden Listener hinzu. Weitere Informationen finden Sie unter [Erstellen und Initialisieren von Ablaufverfolgungslistenern](how-to-create-and-initialize-trace-listeners.md).  
  
5. Testen und debuggen Sie die Anwendung und den darin enthaltenen Ablaufverfolgungscode.  
  
6. Kompilieren Sie die Anwendung mit einem der folgenden Verfahren in ausführbaren Code:  
  
    - Verwenden Sie das Menü **Erstellen** zusammen mit der Seite **Debuggen** im Dialogfeld **Eigenschaftenseite** im **Projektmappen-Explorer**. Dies gilt für die Kompilierung in Visual Studio.  
  
         \- oder –  
  
    - Verwenden Sie für die Kompilierung der Befehlszeile die Compileranweisungen **Ablaufverfolgung** und **Debuggen**. Weitere Informationen finden Sie unter [Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](how-to-compile-conditionally-with-trace-and-debug.md). Dies gilt für die Kompilierung von der Befehlszeile aus.  
  
7. Aktivieren Sie den entsprechenden Ablaufverfolgungsschalter, wenn zur Laufzeit ein Problem auftritt. Weitere Informationen finden Sie unter [Konfigurieren von Ablaufverfolgungsschaltern](how-to-create-initialize-and-configure-trace-switches.md).  
  
     Der Ablaufverfolgungscode schreibt Ablaufverfolgungsmeldungen in ein angegebenes Ziel, z. B. einen Bildschirm, eine Textdatei oder ein Ereignisprotokoll. Der Typ des Listener, den Sie in der <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> Auflistung enthalten haben, bestimmt das Ziel.  
  
8. Analysieren Sie die Ablaufverfolgungsmeldungen, um das Problem in der Anwendung zu ermitteln und zu verstehen.  
  
## <a name="trace-instrumentation-and-distributed-applications"></a>Instrumentation der Ablaufverfolgung und verteilte Anwendungen  
 Beim Erstellen einer verteilten Anwendung ist es in der Regel schwierig, die Anwendung in der Weise zu testen, in der sie letzten Endes verwendet wird. Wenige Entwicklungsteams haben die Möglichkeit, alle möglichen Kombinationen aus Betriebsystemen oder Webbrowsern (einschließlich aller lokalisierten Sprachoptionen) zu testen oder die hohe Zahl von Benutzern zu simulieren, die gleichzeitig auf die Anwendung zugreifen. Unter diesen Umständen können Sie die Reaktion einer verteilten Anwendung auf hohes Datenaufkommen, verschiedene Setups und individuelles Endbenutzerverhalten nicht testen. Außerdem haben viele Teile einer verteilten Anwendung keine Benutzeroberfläche, über die Sie direkt mit diesen Teilen interagieren oder ihre Aktivitäten anzeigen lassen könnten.  
  
 Dieser Umstand lässt sich ausgleichen, indem verteilte Anwendungen mit Funktionalität versehen werden, um bestimmte wichtige Ereignisse, insbesondere auftretende Fehler, für die Systemadministratoren zu beschreiben. Bei dieser sogenannten *Instrumentation* werden Ablaufverfolgungsanweisungen an strategischen Stellen im Code platziert. Dadurch können Sie, wenn zur Laufzeit unerwartete Vorkommnisse auftreten (z. B. extrem langsame Reaktionszeit), die wahrscheinliche Ursache ermitteln.  
  
 Mit Ablaufverfolgungsanweisungen können Sie die schwierige Aufgabe vermeiden, den ursprünglichen Quellcode überprüfen, bearbeiten, neu kompilieren und den Laufzeitfehler in der Debugumgebung reproduzieren zu müssen. Beachten Sie, dass sich eine Anwendung nicht nur für die Anzeige von Fehlern, sondern auch für die Leistungsüberwachung instrumentieren lässt.  
  
## <a name="strategic-placement-of-trace-statements"></a>Strategische Platzierung von Ablaufverfolgungsanweisungen  
 Beim Platzieren der zur Laufzeit verwendeten Ablaufverfolgungsanweisungen ist besondere Sorgfalt erforderlich. Sie müssen überlegen, welche Ablaufverfolgungsinformationen in einer bereitgestellten Anwendung vermutlich benötigt werden, damit alle wahrscheinlichen Ablaufverfolgungsszenarien adäquat abgedeckt werden. Da die Anwendungen, in denen die Ablaufverfolgung verwendet wird, sehr stark variieren, gibt es keine allgemeinen Richtlinien für die strategische Platzierung der Ablaufverfolgung. Weitere Informationen zur Platzierung von Ablaufverfolgungsanweisungen finden Sie unter [Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](how-to-add-trace-statements-to-application-code.md).  
  
## <a name="output-from-tracing"></a>Ausgabe der Ablaufverfolgung  
 Die Ausgabe einer Ablaufverfolgung wird von als *Listener* bezeichneten Objekten aufgenommen. Bei einem Listener handelt es sich um ein Objekt, das die Ablaufverfolgungsausgabe empfängt und in ein Ausgabemedium schreibt (in der Regel ein Fenster, ein Protokoll oder eine Textdatei). Wenn ein Ablaufverfolgungslistener erstellt wird, wird er in der Regel zur <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>-Auflistung hinzugefügt, damit er die gesamte Ablaufverfolgungsausgabe empfängt.  
  
 Ablaufverfolgungsinformationen werden immer wenigstens an das standardmäßige <xref:System.Diagnostics.Trace>-Ausgabeziel, den <xref:System.Diagnostics.DefaultTraceListener>, geschrieben. Wenn Sie den <xref:System.Diagnostics.DefaultTraceListener> aus irgendeinem Grund gelöscht haben, ohne andere Listener zur <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung hinzuzufügen, erhalten Sie keine Ablaufverfolgungsmeldungen. Weitere Informationen finden Sie unter [Ablaufverfolgungslistener](trace-listeners.md).  
  
 Die sechs <xref:System.Diagnostics.Debug>-Member und <xref:System.Diagnostics.Trace>-Methoden, die Ablaufverfolgungsinformationen schreiben, sind in der folgenden Tabelle aufgeführt.  
  
|Methode|Ausgabe|  
|------------|------------|  
|`Assert`|Der angegebene Text oder, falls keiner angegeben ist, die Aufrufliste. Die Ausgabe wird nur geschrieben, wenn die als Argument in der `Assert`-Anweisung angegebene Bedingung **false**ist.|  
|`Fail`|Der angegebene Text oder, falls keiner angegeben ist, die Aufrufliste.|  
|`Write`|Der angegebene Text.|  
|`WriteIf`|Der angegebene Text, wenn die als Argument in der `WriteIf`-Anweisung angegebene Bedingung erfüllt ist.|  
|`WriteLine`|Der angegebene Text und ein Wagenrücklaufzeichen.|  
|`WriteLineIf`|Der angegebene Text und ein Wagen Rücklauf Zeichen, wenn die als Argument in der `WriteLineIf`-Anweisung angegebene Bedingung erfüllt ist.|  
  
 Alle Listener in der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung empfangen die Meldungen, die in der obigen Tabelle beschrieben sind, doch können die ausgeführten Aktionen variieren, je nachdem, welche Art von Listener die Meldung empfängt. Beispielsweise zeigt das <xref:System.Diagnostics.DefaultTraceListener> ein Dialogfeld für die Übersetzung an, wenn es eine `Fail` oder eine fehlerhafte `Assert` Benachrichtigung empfängt, aber ein <xref:System.Diagnostics.TextWriterTraceListener> schreibt die Ausgabe einfach in den Stream.  
  
 Durch Implementieren eines eigenen Listeners können Sie benutzerdefinierte Ergebnisse erzielen. Ein benutzerdefinierter Ablaufverfolgungslistener könnte die Meldungen z. B. in einem Meldungsfeld anzeigen oder die Verbindung zu einer Datenbank herstellen, in der die Meldungen zu einer Tabelle hinzugefügt werden. Alle benutzerdefinierten Listener sollten die sechs oben genannten Methoden unterstützen. Weitere Informationen zum Erstellen entwicklerdefinierter Listener finden Sie unter <xref:System.Diagnostics.TraceListener> in der Referenz zu .NET Framework.  
  
 Die Methoden `Write` und `WriteLine` schreiben immer den Text, den Sie angeben. `Assert`, `WriteIf`und `WriteLineIf` erfordern ein boolesches Argument, das steuert, ob der angegebene Text geschrieben wird. der angegebene Text wird nur geschrieben, wenn der Ausdruck **true** ist (für `WriteIf` und `WriteLineIf`) oder **false** (für `Assert`). Die `Fail`-Methode schreibt immer den angegebenen Text. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](how-to-add-trace-statements-to-application-code.md) und in der .NET Framework-Referenz.  
  
## <a name="security-concerns"></a>Sicherheitsaspekte  
 Wenn Sie vor der Bereitstellung einer ASP.NET-Anwendung nicht die Ablaufverfolgung und das Debuggen deaktivieren, könnte die Anwendung Informationen über sich selbst offen legen, die von böswilligen Programmen missbraucht werden könnten. Weitere Informationen finden Sie unter [Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](how-to-compile-conditionally-with-trace-and-debug.md), [Kompilieren und Erstellen](/visualstudio/ide/compiling-and-building-in-visual-studio) und [Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](how-to-create-initialize-and-configure-trace-switches.md). Das Debuggen kann auch über Internetinformationendienste (IIS) konfiguriert werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- [Codeverträge](code-contracts.md)
- [C#-, F#- und Visual Basic-Projekttypen](/visualstudio/debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types)
- [Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](how-to-add-trace-statements-to-application-code.md)
- [Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](how-to-compile-conditionally-with-trace-and-debug.md)
- [Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](how-to-create-initialize-and-configure-trace-switches.md)
- [Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungsquellen](how-to-create-and-initialize-trace-sources.md)
- [Vorgehensweise: Verwenden von TraceSource und Filtern für Ablaufverfolgungslistener](how-to-use-tracesource-and-filters-with-trace-listeners.md)
- [Ablaufverfolgungslistener](trace-listeners.md)
- [Ablaufverfolgungsschalter](trace-switches.md)
