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
# <a name="how-to-create-and-initialize-trace-listeners"></a>Gewusst wie: Erstellen und Initialisieren von Ablaufverfolgungslistenern

Die Klassen <xref:System.Diagnostics.Debug?displayProperty=nameWithType> und <xref:System.Diagnostics.Trace?displayProperty=nameWithType> senden Nachrichten an Objekte, die Listener genannt werden, welche diese Meldungen empfangen und verarbeiten. Ein solcher Listener, der <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, wird bei Aktivierung der Ablaufverfolgung oder des Debuggens automatisch erstellt und initialisiert. Wenn die <xref:System.Diagnostics.Trace>- oder <xref:System.Diagnostics.Debug>-Ausgabe an zusätzliche Quellen geleitet werden soll, müssen Sie zusätzliche Ablaufverfolgungslistener erstellen und initialisieren.

Erstellen Sie Listener, die auf die Anforderungen Ihrer Anwendung abgestimmt sind. Wenn Sie ein Textprotokoll der gesamten Ablaufverfolgungsausgabe brauchen, erstellen Sie einen <xref:System.Diagnostics.TextWriterTraceListener>-Listener, der die gesamte Ausgabe in eine neue Textdatei schreibt, sobald er aktiviert wird. Wenn Sie die Ausgabe nur während der Anwendungsausführung anzeigen möchten, erstellen Sie einen <xref:System.Diagnostics.ConsoleTraceListener>-Listener, der die gesamte Ausgabe an ein Konsolenfenster leitet. Der <xref:System.Diagnostics.EventLogTraceListener> kann die Ablaufverfolgungsausgabe an ein Ereignisprotokoll leiten. Weitere Informationen finden Sie unter [Ablaufverfolgungslistener](trace-listeners.md).

Sie können Ablaufverfolgungslistener in einer [Anwendungskonfigurationsdatei](../configure-apps/index.md) oder im Code erstellen. Wir empfehlen die Verwendung von Anwendungskonfigurationsdateien, da Sie mit diesen Dateien Ablaufverfolgungslistener hinzufügen, ändern oder entfernen können, ohne den Code ändern zu müssen.

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a>So erstellen und verwenden Sie einen Ablaufverfolgungslistener mithilfe einer Konfigurationsdatei

1. Deklarieren Sie den Ablaufverfolgungslistener in der Anwendungskonfigurationsdatei. Wenn der Listener, den Sie erstellen, andere Objekte benötigt, deklarieren Sie diese ebenfalls. Das folgende Beispiel zeigt, wie ein Listener mit der Bezeichnung `myListener` erstellt wird, der in die Textdatei `TextWriterOutput.log` schreibt.

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

2. Verwenden Sie die <xref:System.Diagnostics.Trace>-Klasse im Code, um eine Meldung in die Ablaufverfolgungslistener zu schreiben.

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

### <a name="to-create-and-use-a-trace-listener-in-code"></a>So erstellen und verwenden Sie einen Ablaufverfolgungslistener im Code

- Fügen Sie den Ablaufverfolgungslistener der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung hinzu, und senden Sie die Ablaufverfolgungsinformationen an die Listener.

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

    \- oder –

- Wenn Sie nicht möchten, dass der Listener die Ablaufverfolgungsausgabe empfängt, fügen Sie diesen nicht zur <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung hinzu. Sie können die Ausgabe über einen Listener unabhängig von der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung durch Aufrufen der eigenen Ausgabemethoden des Listeners ausgeben. Im folgenden Beispiel wird gezeigt, wie eine Zeile in einen Listener geschrieben wird, der nicht in der <xref:System.Diagnostics.Trace.Listeners%2A>-Auflistung vorhanden ist.

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

## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgungslistener](trace-listeners.md)
- [Ablaufverfolgungsschalter](trace-switches.md)
- [Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](how-to-add-trace-statements-to-application-code.md)
- [Ablaufverfolgung und Instrumentieren von Anwendungen](tracing-and-instrumenting-applications.md)
