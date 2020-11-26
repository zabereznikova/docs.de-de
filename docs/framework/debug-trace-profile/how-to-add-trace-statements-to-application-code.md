---
title: 'Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode'
description: Erfahren Sie, wie Sie Ablauf Verfolgungs Anweisungen zu Anwendungscode in .NET hinzufügen. Die am häufigsten für die Ablauf Verfolgung verwendeten Methoden sind die Methoden zum Schreiben der Ausgabe in Listener.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], conditional writes based on switches
- trace statements
- WriteLineIf method
- tracing [.NET Framework], adding trace statements
- Assert method, tracing code
- trace switches, conditional writes based on switches
- WriteIf method
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
ms.openlocfilehash: 6beecf39d4372a194a9110ed8942b998443934d4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244209"
---
# <a name="how-to-add-trace-statements-to-application-code"></a>Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode

Die am häufigsten für die Ablaufverfolgung verwendeten Methoden zum Schreiben von Ausgaben in Listener: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert** und **Fail**. Diese Methoden können in zwei Kategorien unterteilt werden: **Write**, **WriteLine** und **Fail** geben alle Ausgaben ohne Bedingungen aus, während **WriteIf**, **WriteLineIf** und **Assert** eine boolesche Bedingung testen und die Ausgabe auf Basis des Werts dieser Bedingung erstellen oder nicht erstellen. **WriteIf** und **WriteLineIf** führen zu einer Ausgabe, wenn die Bedingung `true` entspricht. **Assert** führt zu einer Ausgabe, wenn die Bedingung `false` entspricht.  
  
 Berücksichtigen Sie beim Entwerfen Ihrer Ablaufverfolgungs- und Debugstrategie, wie die Ausgabe aussehen soll. Mehrere **Write** -Anweisungen, die mit nicht verknüpften Informationen gefüllt sind, erstellen ein Protokoll, das schwer zu lesen ist. Die Verwendung von **Write teline** zum Platzieren verwandter Anweisungen in separaten Zeilen kann es jedoch schwierig machen, zu unterscheiden, welche Informationen zusammengehören. Verwenden Sie im Allgemeinen mehrere **Write** -Anweisungen, wenn Sie Informationen aus mehreren Quellen kombinieren möchten, um eine einzelne informative Nachricht zu erstellen, und verwenden Sie die Anweisung "Write **teline** ", wenn Sie eine einzelne vollständige Meldung erstellen möchten.  
  
### <a name="to-write-a-complete-line"></a>So schreiben Sie eine vollständige Zeile  
  
1. Rufen Sie die <xref:System.Diagnostics.Trace.WriteLine%2A>-Methode oder <xref:System.Diagnostics.Trace.WriteLineIf%2A>-Methode auf.  
  
     Es wird ein Wagenrücklauf am Ende der von dieser Methode zurückgegebenen Nachricht angefügt, sodass die nächste von **Write**, **WriteIf**, **WriteLine** oder **WriteLineIf** zurückgegebene Nachricht in der darauffolgenden Zeile beginnt:  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteLine("Error in AppendData procedure.")  
    Trace.WriteLineIf(errorFlag, "Error in AppendData procedure.")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteLine ("Error in AppendData procedure.");  
    System.Diagnostics.Trace.WriteLineIf(errorFlag,
       "Error in AppendData procedure.");  
    ```  
  
### <a name="to-write-a-partial-line"></a>So schreiben Sie eine Teilzeile  
  
1. Rufen Sie die <xref:System.Diagnostics.Trace.Write%2A>-Methode oder <xref:System.Diagnostics.Trace.WriteIf%2A>-Methode auf.  
  
     Die nächste von **Write**, **WriteIf**, **WriteLine** oder **WriteLineIf** ausgegebene Nachricht beginnt auf derselben Zeile wie die Nachricht, die von **Write**- oder **WriteIf**-Anweisungen ausgegeben wurde:  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteIf(errorFlag, "Error in AppendData procedure.")  
    Debug.WriteIf(errorFlag, "Transaction abandoned.")  
    Trace.Write("Invalid value for data request")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteIf(errorFlag,
       "Error in AppendData procedure.");  
    System.Diagnostics.Debug.WriteIf(errorFlag, "Transaction abandoned.");  
    Trace.Write("Invalid value for data request");  
    ```  
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a>So überprüfen Sie, ob bestimmte Bedingungen vor oder nach dem Ausführen einer Methode vorhanden sind  
  
1. Rufen Sie die <xref:System.Diagnostics.Trace.Assert%2A>-Methode auf.  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    > Sie können **Assert** bei der Ablaufverfolgung und beim Debuggen verwenden. In diesem Beispiel wird die Aufrufliste an alle Listener in der **Listener**-Auflistung ausgegeben. Weitere Informationen finden Sie unter [Assertionen in verwaltetem Code](/visualstudio/debugger/assertions-in-managed-code) und <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>
- [Ablaufverfolgung und Instrumentieren von Anwendungen](tracing-and-instrumenting-applications.md)
- [Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](how-to-create-initialize-and-configure-trace-switches.md)
- [Ablaufverfolgungsschalter](trace-switches.md)
- [Ablaufverfolgungslistener](trace-listeners.md)
