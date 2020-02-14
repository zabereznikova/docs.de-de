---
title: 'Gewusst wie: Erstellen und Initialisieren von Ablaufverfolgungslistenern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- initializing trace listeners
- trace listeners, creating
- trace listeners, initializing
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 21726de1-61ee-4fdc-9dd0-3be49324d066
ms.openlocfilehash: ce0df0af32d6798c89c8db6761d18febc1c398bb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217444"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a><span data-ttu-id="c482e-102">Gewusst wie: Erstellen und Initialisieren von Ablaufverfolgungslistenern</span><span class="sxs-lookup"><span data-stu-id="c482e-102">How to: Create and Initialize Trace Listeners</span></span>

<span data-ttu-id="c482e-103">Die Klassen <xref:System.Diagnostics.Debug?displayProperty=nameWithType> und <xref:System.Diagnostics.Trace?displayProperty=nameWithType> senden Nachrichten an Objekte, die Listener genannt werden, welche diese Meldungen empfangen und verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c482e-103">The <xref:System.Diagnostics.Debug?displayProperty=nameWithType> and <xref:System.Diagnostics.Trace?displayProperty=nameWithType> classes send messages to objects called listeners that receive and process these messages.</span></span> <span data-ttu-id="c482e-104">Ein solcher Listener, der <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, wird bei Aktivierung der Ablaufverfolgung oder des Debuggens automatisch erstellt und initialisiert.</span><span class="sxs-lookup"><span data-stu-id="c482e-104">One such listener, the <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, is automatically created and initialized when tracing or debugging is enabled.</span></span> <span data-ttu-id="c482e-105">Wenn die <xref:System.Diagnostics.Trace>- oder <xref:System.Diagnostics.Debug>-Ausgabe an zusätzliche Quellen geleitet werden soll, müssen Sie zusätzliche Ablaufverfolgungslistener erstellen und initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c482e-105">If you want <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.Debug> output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span>

<span data-ttu-id="c482e-106">Erstellen Sie Listener, die auf die Anforderungen Ihrer Anwendung abgestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="c482e-106">The listeners you create should reflect your application's needs.</span></span> <span data-ttu-id="c482e-107">Wenn Sie ein Textprotokoll der gesamten Ablaufverfolgungsausgabe brauchen, erstellen Sie einen <xref:System.Diagnostics.TextWriterTraceListener>-Listener, der die gesamte Ausgabe in eine neue Textdatei schreibt, sobald er aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c482e-107">For example, if you want a text record of all trace output, create a <xref:System.Diagnostics.TextWriterTraceListener> listener, which writes all output to a new text file when it is enabled.</span></span> <span data-ttu-id="c482e-108">Wenn Sie die Ausgabe nur während der Anwendungsausführung anzeigen möchten, erstellen Sie einen <xref:System.Diagnostics.ConsoleTraceListener>-Listener, der die gesamte Ausgabe an ein Konsolenfenster leitet.</span><span class="sxs-lookup"><span data-stu-id="c482e-108">On the other hand, if you want to view output only during application execution, create a <xref:System.Diagnostics.ConsoleTraceListener> listener, which directs all output to a console window.</span></span> <span data-ttu-id="c482e-109">Der <xref:System.Diagnostics.EventLogTraceListener> kann die Ablaufverfolgungsausgabe an ein Ereignisprotokoll leiten.</span><span class="sxs-lookup"><span data-stu-id="c482e-109">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log.</span></span> <span data-ttu-id="c482e-110">Weitere Informationen finden Sie unter [Ablaufverfolgungslistener](trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="c482e-110">For more information, see [Trace Listeners](trace-listeners.md).</span></span>

<span data-ttu-id="c482e-111">Sie können Ablaufverfolgungslistener in einer [Anwendungskonfigurationsdatei](../configure-apps/index.md) oder im Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="c482e-111">You can create trace listeners in an [application configuration file](../configure-apps/index.md) or in your code.</span></span> <span data-ttu-id="c482e-112">Wir empfehlen die Verwendung von Anwendungskonfigurationsdateien, da Sie mit diesen Dateien Ablaufverfolgungslistener hinzufügen, ändern oder entfernen können, ohne den Code ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c482e-112">We recommend the use of application configuration files, because they let you add, modify, or remove trace listeners without having to change your code.</span></span>

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a><span data-ttu-id="c482e-113">So erstellen und verwenden Sie einen Ablaufverfolgungslistener mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c482e-113">To create and use a trace listener by using a configuration file</span></span>

1. <span data-ttu-id="c482e-114">Deklarieren Sie den Ablaufverfolgungslistener in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c482e-114">Declare your trace listener in your application configuration file.</span></span> <span data-ttu-id="c482e-115">Wenn der Listener, den Sie erstellen, andere Objekte benötigt, deklarieren Sie diese ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="c482e-115">If the listener you are creating requires any other objects, declare them as well.</span></span> <span data-ttu-id="c482e-116">Das folgende Beispiel zeigt, wie ein Listener mit der Bezeichnung `myListener` erstellt wird, der in die Textdatei `TextWriterOutput.log` schreibt.</span><span class="sxs-lookup"><span data-stu-id="c482e-116">The following example shows how to create a listener called `myListener` that writes to the text file `TextWriterOutput.log`.</span></span>

    ```xml
    <configuration>
      <system.diagnostics>
        <trace autoflush="false" indentsize="4">
          <listeners>
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener" initializeData="TextWriterOutput.log" />
            <remove name="Default" />
          </listeners>
        </trace>
      </system.diagnostics>
    </configuration>
    ```

2. <span data-ttu-id="c482e-117">Verwenden Sie die <xref:System.Diagnostics.Trace>-Klasse im Code, um eine Meldung in die Ablaufverfolgungslistener zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c482e-117">Use the <xref:System.Diagnostics.Trace> class in your code to write a message to the trace listeners.</span></span>

    ```vb
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

### <a name="to-create-and-use-a-trace-listener-in-code"></a><span data-ttu-id="c482e-118">So erstellen und verwenden Sie einen Ablaufverfolgungslistener im Code</span><span class="sxs-lookup"><span data-stu-id="c482e-118">To create and use a trace listener in code</span></span>

- <span data-ttu-id="c482e-119">Fügen Sie den Ablaufverfolgungslistener der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung hinzu, und senden Sie die Ablaufverfolgungsinformationen an die Listener.</span><span class="sxs-lookup"><span data-stu-id="c482e-119">Add the trace listener to the <xref:System.Diagnostics.Trace.Listeners%2A> collection and send trace information to the listeners.</span></span>

    ```vb
    Trace.Listeners.Add(New TextWriterTraceListener("TextWriterOutput.log", "myListener"))
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.Listeners.Add(new TextWriterTraceListener("TextWriterOutput.log", "myListener"));
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

    <span data-ttu-id="c482e-120">\- oder –</span><span class="sxs-lookup"><span data-stu-id="c482e-120">\- or -</span></span>

- <span data-ttu-id="c482e-121">Wenn Sie nicht möchten, dass der Listener die Ablaufverfolgungsausgabe empfängt, fügen Sie diesen nicht zur <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c482e-121">If you do not want your listener to receive trace output, do not add it to the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span> <span data-ttu-id="c482e-122">Sie können die Ausgabe über einen Listener unabhängig von der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung durch Aufrufen der eigenen Ausgabemethoden des Listeners ausgeben.</span><span class="sxs-lookup"><span data-stu-id="c482e-122">You can emit output through a listener independent of the <xref:System.Diagnostics.Trace.Listeners%2A> collection by calling the listener's own output methods.</span></span> <span data-ttu-id="c482e-123">Im folgenden Beispiel wird gezeigt, wie eine Zeile in einen Listener geschrieben wird, der nicht in der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c482e-123">The following example shows how to write a line to a listener that is not in the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span>

    ```vb
    Dim myListener As New TextWriterTraceListener("TextWriterOutput.log", "myListener")
    myListener.WriteLine("Test message.")
    ' You must close or flush the trace listener to empty the output buffer.
    myListener.Flush()
    ```

    ```csharp
    TextWriterTraceListener myListener = new TextWriterTraceListener("TextWriterOutput.log", "myListener");
    myListener.WriteLine("Test message.");
    // You must close or flush the trace listener to empty the output buffer.
    myListener.Flush();
    ```

## <a name="see-also"></a><span data-ttu-id="c482e-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c482e-124">See also</span></span>

- [<span data-ttu-id="c482e-125">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="c482e-125">Trace Listeners</span></span>](trace-listeners.md)
- [<span data-ttu-id="c482e-126">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="c482e-126">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="c482e-127">Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode</span><span class="sxs-lookup"><span data-stu-id="c482e-127">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="c482e-128">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="c482e-128">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
