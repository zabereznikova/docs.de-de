---
title: 'Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungslistenern'
description: Erfahren Sie, wie Sie Ablaufverfolgungslistener erstellen und initialisieren, indem Sie Klassen wie System. Diagnostics. DefaultTraceListener in .NET verwenden.
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
ms.openlocfilehash: 752306124e41a7fb7458daccc8c2891631eb9616
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051206"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a><span data-ttu-id="66c3c-103">Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungslistenern</span><span class="sxs-lookup"><span data-stu-id="66c3c-103">How to: Create and Initialize Trace Listeners</span></span>

<span data-ttu-id="66c3c-104">Die Klassen <xref:System.Diagnostics.Debug?displayProperty=nameWithType> und <xref:System.Diagnostics.Trace?displayProperty=nameWithType> senden Nachrichten an Objekte, die Listener genannt werden, welche diese Meldungen empfangen und verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="66c3c-104">The <xref:System.Diagnostics.Debug?displayProperty=nameWithType> and <xref:System.Diagnostics.Trace?displayProperty=nameWithType> classes send messages to objects called listeners that receive and process these messages.</span></span> <span data-ttu-id="66c3c-105">Ein solcher Listener, der <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, wird bei Aktivierung der Ablaufverfolgung oder des Debuggens automatisch erstellt und initialisiert.</span><span class="sxs-lookup"><span data-stu-id="66c3c-105">One such listener, the <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, is automatically created and initialized when tracing or debugging is enabled.</span></span> <span data-ttu-id="66c3c-106">Wenn die <xref:System.Diagnostics.Trace>- oder <xref:System.Diagnostics.Debug>-Ausgabe an zusätzliche Quellen geleitet werden soll, müssen Sie zusätzliche Ablaufverfolgungslistener erstellen und initialisieren.</span><span class="sxs-lookup"><span data-stu-id="66c3c-106">If you want <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.Debug> output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span>

<span data-ttu-id="66c3c-107">Erstellen Sie Listener, die auf die Anforderungen Ihrer Anwendung abgestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="66c3c-107">The listeners you create should reflect your application's needs.</span></span> <span data-ttu-id="66c3c-108">Wenn Sie ein Textprotokoll der gesamten Ablaufverfolgungsausgabe brauchen, erstellen Sie einen <xref:System.Diagnostics.TextWriterTraceListener>-Listener, der die gesamte Ausgabe in eine neue Textdatei schreibt, sobald er aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="66c3c-108">For example, if you want a text record of all trace output, create a <xref:System.Diagnostics.TextWriterTraceListener> listener, which writes all output to a new text file when it is enabled.</span></span> <span data-ttu-id="66c3c-109">Wenn Sie die Ausgabe nur während der Anwendungsausführung anzeigen möchten, erstellen Sie einen <xref:System.Diagnostics.ConsoleTraceListener>-Listener, der die gesamte Ausgabe an ein Konsolenfenster leitet.</span><span class="sxs-lookup"><span data-stu-id="66c3c-109">On the other hand, if you want to view output only during application execution, create a <xref:System.Diagnostics.ConsoleTraceListener> listener, which directs all output to a console window.</span></span> <span data-ttu-id="66c3c-110">Der <xref:System.Diagnostics.EventLogTraceListener> kann die Ablaufverfolgungsausgabe an ein Ereignisprotokoll leiten.</span><span class="sxs-lookup"><span data-stu-id="66c3c-110">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log.</span></span> <span data-ttu-id="66c3c-111">Weitere Informationen finden Sie unter [Trace Listeners](trace-listeners.md)Ablaufverfolgungslistener.</span><span class="sxs-lookup"><span data-stu-id="66c3c-111">For more information, see [Trace Listeners](trace-listeners.md).</span></span>

<span data-ttu-id="66c3c-112">Sie können Ablaufverfolgungslistener in einer [Anwendungskonfigurationsdatei](../configure-apps/index.md) oder im Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="66c3c-112">You can create trace listeners in an [application configuration file](../configure-apps/index.md) or in your code.</span></span> <span data-ttu-id="66c3c-113">Wir empfehlen die Verwendung von Anwendungskonfigurationsdateien, da Sie mit diesen Dateien Ablaufverfolgungslistener hinzufügen, ändern oder entfernen können, ohne den Code ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="66c3c-113">We recommend the use of application configuration files, because they let you add, modify, or remove trace listeners without having to change your code.</span></span>

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a><span data-ttu-id="66c3c-114">So erstellen und verwenden Sie einen Ablaufverfolgungslistener mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="66c3c-114">To create and use a trace listener by using a configuration file</span></span>

1. <span data-ttu-id="66c3c-115">Deklarieren Sie den Ablaufverfolgungslistener in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="66c3c-115">Declare your trace listener in your application configuration file.</span></span> <span data-ttu-id="66c3c-116">Wenn der Listener, den Sie erstellen, andere Objekte benötigt, deklarieren Sie diese ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="66c3c-116">If the listener you are creating requires any other objects, declare them as well.</span></span> <span data-ttu-id="66c3c-117">Das folgende Beispiel zeigt, wie ein Listener mit der Bezeichnung `myListener` erstellt wird, der in die Textdatei `TextWriterOutput.log` schreibt.</span><span class="sxs-lookup"><span data-stu-id="66c3c-117">The following example shows how to create a listener called `myListener` that writes to the text file `TextWriterOutput.log`.</span></span>

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

2. <span data-ttu-id="66c3c-118">Verwenden Sie die <xref:System.Diagnostics.Trace>-Klasse im Code, um eine Meldung in die Ablaufverfolgungslistener zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="66c3c-118">Use the <xref:System.Diagnostics.Trace> class in your code to write a message to the trace listeners.</span></span>

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

### <a name="to-create-and-use-a-trace-listener-in-code"></a><span data-ttu-id="66c3c-119">So erstellen und verwenden Sie einen Ablaufverfolgungslistener im Code</span><span class="sxs-lookup"><span data-stu-id="66c3c-119">To create and use a trace listener in code</span></span>

- <span data-ttu-id="66c3c-120">Fügen Sie den Ablaufverfolgungslistener der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung hinzu, und senden Sie die Ablaufverfolgungsinformationen an die Listener.</span><span class="sxs-lookup"><span data-stu-id="66c3c-120">Add the trace listener to the <xref:System.Diagnostics.Trace.Listeners%2A> collection and send trace information to the listeners.</span></span>

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

    <span data-ttu-id="66c3c-121">\- oder -</span><span class="sxs-lookup"><span data-stu-id="66c3c-121">\- or -</span></span>

- <span data-ttu-id="66c3c-122">Wenn Sie nicht möchten, dass der Listener die Ablaufverfolgungsausgabe empfängt, fügen Sie diesen nicht zur <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="66c3c-122">If you do not want your listener to receive trace output, do not add it to the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span> <span data-ttu-id="66c3c-123">Sie können die Ausgabe über einen Listener unabhängig von der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung durch Aufrufen der eigenen Ausgabemethoden des Listeners ausgeben.</span><span class="sxs-lookup"><span data-stu-id="66c3c-123">You can emit output through a listener independent of the <xref:System.Diagnostics.Trace.Listeners%2A> collection by calling the listener's own output methods.</span></span> <span data-ttu-id="66c3c-124">Im folgenden Beispiel wird gezeigt, wie eine Zeile in einen Listener geschrieben wird, der nicht in der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="66c3c-124">The following example shows how to write a line to a listener that is not in the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="66c3c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66c3c-125">See also</span></span>

- [<span data-ttu-id="66c3c-126">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="66c3c-126">Trace Listeners</span></span>](trace-listeners.md)
- [<span data-ttu-id="66c3c-127">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="66c3c-127">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="66c3c-128">Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode</span><span class="sxs-lookup"><span data-stu-id="66c3c-128">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="66c3c-129">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="66c3c-129">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
