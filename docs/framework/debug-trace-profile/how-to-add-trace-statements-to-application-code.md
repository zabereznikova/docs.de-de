---
title: 'Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode'
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b39646655c175497533aa6dc358c6966acc27344
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325584"
---
# <a name="how-to-add-trace-statements-to-application-code"></a>Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode
Die für die Ablaufverfolgung am häufigsten verwendeten Methoden sind die Methoden zum Schreiben von Ausgaben in Listener: **Schreiben von**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert**, und **fehlschlagen**. Diese Methoden können in zwei Kategorien unterteilt werden: **Schreiben von**, **WriteLine**, und **fehlschlagen** alle ausgeben bedingungslos während **WriteIf**, **WriteLineIf**, und  **Assert-** eine boolesche Bedingung testen und zu schreiben bzw. Schreiben nicht basierend auf dem Wert der Bedingung. **WriteIf** und **WriteLineIf** führen zu einer Ausgabe, wenn die Bedingung `true` entspricht. **Assert** führt zu einer Ausgabe, wenn die Bedingung `false` entspricht.  
  
 Berücksichtigen Sie beim Entwerfen Ihrer Ablaufverfolgungs- und Debugstrategie, wie die Ausgabe aussehen soll. Mehrere **Write**-Anweisungen, die mit beziehungslosen Informationen gefüllt sind, erstellen ein Protokoll, das schwer zu lesen ist. Auf der anderen Seite kann möglicherweise schwer unterschieden werden, welche Informationen zusammengehören, wenn zusammengehörige Anweisungen mithilfe von **WriteLine** in separaten Zeilen angezeigt werden. Verwenden Sie im Allgemeinen mehrere **Write**-Anweisungen, wenn Sie Informationen aus mehreren Quellen zu einer einzelnen Informationsmeldung zusammenfassen möchten. Verwenden Sie die **WriteLine**-Anweisung, wenn Sie eine einzelne vollständige Meldung erstellen möchten.  
  
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
    >  Sie können **Assert** bei der Ablaufverfolgung und beim Debuggen verwenden. In diesem Beispiel wird die Aufrufliste an alle Listener in der **Listener**-Auflistung ausgegeben. Weitere Informationen finden Sie unter [Assertionen in verwaltetem Code](/visualstudio/debugger/assertions-in-managed-code) und <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>
- [Ablaufverfolgung und Instrumentieren von Anwendungen](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
- [Vorgehensweise: Erstellen, initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)
- [Ablaufverfolgungsschalter](../../../docs/framework/debug-trace-profile/trace-switches.md)
- [Trace Listeners (Ablaufverfolgungslistener)](../../../docs/framework/debug-trace-profile/trace-listeners.md)
