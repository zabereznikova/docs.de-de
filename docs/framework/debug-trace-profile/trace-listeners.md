---
title: Ablaufverfolgungslistener
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Listener object types
- listeners
- Trace class, listeners
- trace listeners, about trace listeners
- Listeners collection
- trace listeners
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 444b0d33-67ea-4c36-9e94-79c50f839025
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5657e55856845404c5f8f063bd69d51614a234c9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614287"
---
# <a name="trace-listeners"></a><span data-ttu-id="e970b-102">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="e970b-102">Trace Listeners</span></span>
<span data-ttu-id="e970b-103">Wenn Sie mit **Trace**, **Debug** und <xref:System.Diagnostics.TraceSource> arbeiten, müssen Sie einen Mechanismus zum Sammeln und Aufzeichnen der gesendeten Meldungen einrichten.</span><span class="sxs-lookup"><span data-stu-id="e970b-103">When using **Trace**, **Debug** and <xref:System.Diagnostics.TraceSource>, you must have a mechanism for collecting and recording the messages that are sent.</span></span> <span data-ttu-id="e970b-104">Ablaufverfolgungsmeldungen werden von *Listenern* empfangen.</span><span class="sxs-lookup"><span data-stu-id="e970b-104">Trace messages are received by *listeners*.</span></span> <span data-ttu-id="e970b-105">Der Zweck eines Listeners ist das Sammeln, Speichern und Weiterleiten von Ablaufverfolgungsmeldungen.</span><span class="sxs-lookup"><span data-stu-id="e970b-105">The purpose of a listener is to collect, store, and route tracing messages.</span></span> <span data-ttu-id="e970b-106">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel, beispielsweise ein Protokoll, ein Fenster oder eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="e970b-106">Listeners direct the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="e970b-107">Listener stehen für die Klassen **Debug**, **Trace** und <xref:System.Diagnostics.TraceSource> zur Verfügung, von denen jede ihre Ausgabe an eine Vielzahl von Listenerobjekten senden kann.</span><span class="sxs-lookup"><span data-stu-id="e970b-107">Listeners are available to the **Debug**, **Trace**, and <xref:System.Diagnostics.TraceSource> classes, each of which can send its output to a variety of listener objects.</span></span> <span data-ttu-id="e970b-108">Im Folgenden werden die häufig verwendeten vordefinierten Listener aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e970b-108">The following are the commonly used predefined listeners:</span></span>  
  
- <span data-ttu-id="e970b-109">Ein <xref:System.Diagnostics.TextWriterTraceListener> leitet die Ausgabe zu einer Instanz der <xref:System.IO.TextWriter>-Klasse oder zu einer beliebigen <xref:System.IO.Stream>-Klasse um.</span><span class="sxs-lookup"><span data-stu-id="e970b-109">A <xref:System.Diagnostics.TextWriterTraceListener> redirects output to an instance of the <xref:System.IO.TextWriter> class or to anything that is a <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="e970b-110">Das Schreiben in die Konsole oder in eine Datei ist auch möglich, da diese <xref:System.IO.Stream>-Klassen sind.</span><span class="sxs-lookup"><span data-stu-id="e970b-110">It can also write to the console or to a file, because these are <xref:System.IO.Stream> classes.</span></span>  
  
- <span data-ttu-id="e970b-111">Ein <xref:System.Diagnostics.EventLogTraceListener> leitet die Ausgabe zu einem Ereignisprotokoll um.</span><span class="sxs-lookup"><span data-stu-id="e970b-111">An <xref:System.Diagnostics.EventLogTraceListener> redirects output to an event log.</span></span>  
  
- <span data-ttu-id="e970b-112">Ein <xref:System.Diagnostics.DefaultTraceListener> gibt die Nachrichten **Write** und **WriteLine** an die **OutputDebugString**- und die **Debugger.Log**-Methode aus.</span><span class="sxs-lookup"><span data-stu-id="e970b-112">A <xref:System.Diagnostics.DefaultTraceListener> emits **Write** and **WriteLine** messages to the **OutputDebugString** and to the **Debugger.Log** method.</span></span> <span data-ttu-id="e970b-113">Dies führt in Visual Studio dazu, dass die Debugging-Meldungen im Ausgabefenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e970b-113">In Visual Studio, this causes the debugging messages to appear in the Output window.</span></span> <span data-ttu-id="e970b-114">**Fail** und fehlgeschlagene **Assert**-Meldungen werden auch an die **OutputDebugString**-Windows-API und die **Debugger.Log**-Methode ausgegeben, und darüber hinaus wird auch ein Meldungsfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e970b-114">**Fail** and failed **Assert** messages also emit to the **OutputDebugString** Windows API and the **Debugger.Log** method, and also cause a message box to be displayed.</span></span> <span data-ttu-id="e970b-115">Dieses Verhalten ist das Standardverhalten für Meldungen von **Debug** und **Trace**, da **DefaultTraceListener** automatisch in jeder `Listeners`-Auflistung enthalten ist und es sich dabei um den einzigen automatisch eingebundenen Listener handelt.</span><span class="sxs-lookup"><span data-stu-id="e970b-115">This behavior is the default behavior for **Debug** and **Trace** messages, because **DefaultTraceListener** is automatically included in every `Listeners` collection and is the only listener automatically included.</span></span>  
  
- <span data-ttu-id="e970b-116">Ein <xref:System.Diagnostics.ConsoleTraceListener> leitet eine Ablaufverfolgungs- oder Debuggingausgabe an die Standardausgabe oder den Standardfehlerstream weiter.</span><span class="sxs-lookup"><span data-stu-id="e970b-116">A <xref:System.Diagnostics.ConsoleTraceListener> directs tracing or debugging output to either the standard output or the standard error stream.</span></span>  
  
- <span data-ttu-id="e970b-117">Ein <xref:System.Diagnostics.DelimitedListTraceListener> leitet eine Ablaufverfolgungs- oder Debuggingausgabe an einen Textwriter, z. B. einen Streamwriter, oder an einen Stream, z. B. einen Dateistream, weiter.</span><span class="sxs-lookup"><span data-stu-id="e970b-117">A <xref:System.Diagnostics.DelimitedListTraceListener> directs tracing or debugging output to a text writer, such as a stream writer, or to a stream, such as a file stream.</span></span> <span data-ttu-id="e970b-118">Die Ablaufverfolgungsausgabe liegt in einem Textformat mit Trennzeichen vor, das das durch die <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>-Eigenschaft angegebene Trennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e970b-118">The trace output is in a delimited text format that uses the delimiter specified by the <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> property.</span></span>  
  
- <span data-ttu-id="e970b-119">Ein <xref:System.Diagnostics.XmlWriterTraceListener> leitet die Ablaufverfolgungs- oder Debuggingausgabe als XML-codierte Daten an einen <xref:System.IO.TextWriter> oder einen <xref:System.IO.Stream>, wie z. B. einen <xref:System.IO.FileStream>, weiter.</span><span class="sxs-lookup"><span data-stu-id="e970b-119">An <xref:System.Diagnostics.XmlWriterTraceListener> directs tracing or debugging output as XML-encoded data to a <xref:System.IO.TextWriter> or to a <xref:System.IO.Stream>, such as a <xref:System.IO.FileStream>.</span></span>  
  
 <span data-ttu-id="e970b-120">Wenn neben <xref:System.Diagnostics.DefaultTraceListener> jeder Listener die Ausgabe von **Debug**, **Trace** und <xref:System.Diagnostics.TraceSource> empfangen soll, müssen Sie diese der `Listeners`-Auflistung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e970b-120">If you want any listener besides the <xref:System.Diagnostics.DefaultTraceListener> to receive **Debug**, **Trace** and <xref:System.Diagnostics.TraceSource> output, you must add it to the `Listeners` collection.</span></span> <span data-ttu-id="e970b-121">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungslistenern](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) und [Vorgehensweise: Verwenden von TraceSource und Filtern für Ablaufverfolgungslistener](../../../docs/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="e970b-121">For more information, see [How to: Create and Initialize Trace Listeners](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) and [How to: Use TraceSource and Filters with Trace Listeners](../../../docs/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span> <span data-ttu-id="e970b-122">Alle Listener in der **Listeners**-Auflistung erhalten die gleichen Meldungen aus den Ablaufverfolgungsausgabemethoden.</span><span class="sxs-lookup"><span data-stu-id="e970b-122">Any listener in the **Listeners** collection gets the same messages from the trace output methods.</span></span> <span data-ttu-id="e970b-123">Nehmen wir beispielsweise an, dass Sie zwei Listener einrichten: **TextWriterTraceListener** und **EventLogTraceListener**.</span><span class="sxs-lookup"><span data-stu-id="e970b-123">For example, suppose you set up two listeners: a **TextWriterTraceListener** and an **EventLogTraceListener**.</span></span> <span data-ttu-id="e970b-124">Jeder Listener empfängt die gleiche Meldung.</span><span class="sxs-lookup"><span data-stu-id="e970b-124">Each listener receives the same message.</span></span> <span data-ttu-id="e970b-125">Der Listener **TextWriterTraceListener** leitet seine Ausgabe an einen Datenstrom weiter, und der Listener **EventLogTraceListener** leitet seine Ausgabe an ein Ereignisprotokoll weiter.</span><span class="sxs-lookup"><span data-stu-id="e970b-125">The **TextWriterTraceListener** would direct its output to a stream, and the **EventLogTraceListener** would direct its output to an event log.</span></span>  
  
 <span data-ttu-id="e970b-126">Das folgende Beispiel zeigt, wie die Ausgabe an die **Listeners**-Auflistung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="e970b-126">The following example shows how to send output to the **Listeners** collection.</span></span>  
  
```vb  
' Use this example when debugging.  
Debug.WriteLine("Error in Widget 42")  
' Use this example when tracing.  
Trace.WriteLine("Error in Widget 42")  
```  
  
```csharp  
// Use this example when debugging.  
System.Diagnostics.Debug.WriteLine("Error in Widget 42");  
// Use this example when tracing.  
System.Diagnostics.Trace.WriteLine("Error in Widget 42");  
```  
  
 <span data-ttu-id="e970b-127">„Debug“ und „Trace“ nutzen die gleiche **Listeners**-Auflistung. Wenn Sie also der **Debug.Listeners**-Auflistung in Ihrer Anwendung ein Listenerobjekt hinzufügen, wird dieses auch der **Trace.Listeners**-Auflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e970b-127">Debug and trace share the same **Listeners** collection, so if you add a listener object to a **Debug.Listeners** collection in your application, it gets added to the **Trace.Listeners** collection as well.</span></span>  
  
 <span data-ttu-id="e970b-128">Das folgende Beispiel zeigt, wie ein Listener verwendet wird, um Ablaufverfolgungsinformationen an eine Konsole zu senden:</span><span class="sxs-lookup"><span data-stu-id="e970b-128">The following example shows how to use a listener to send tracing information to a console:</span></span>  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a><span data-ttu-id="e970b-129">Entwicklerdefinierte Listener</span><span class="sxs-lookup"><span data-stu-id="e970b-129">Developer-Defined Listeners</span></span>  
 <span data-ttu-id="e970b-130">Sie können eigene Listener durch Erben von der **TraceListener**-Basisklasse definieren und die dazugehörigen Methoden mit benutzerdefinierten Methoden überschreiben.</span><span class="sxs-lookup"><span data-stu-id="e970b-130">You can define your own listeners by inheriting from the **TraceListener** base class and overriding its methods with your customized methods.</span></span> <span data-ttu-id="e970b-131">Weitere Informationen zum Erstellen entwicklerdefinierter Listener finden Sie unter <xref:System.Diagnostics.TraceListener> in der Referenz zu .NET Framework. </span><span class="sxs-lookup"><span data-stu-id="e970b-131">For more information on creating developer-defined listeners, see <xref:System.Diagnostics.TraceListener> in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e970b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e970b-132">See also</span></span>

- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="e970b-133">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="e970b-133">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="e970b-134">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="e970b-134">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)
