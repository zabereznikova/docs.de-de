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
# <a name="how-to-add-trace-statements-to-application-code"></a><span data-ttu-id="f6721-104">Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode</span><span class="sxs-lookup"><span data-stu-id="f6721-104">How to: Add Trace Statements to Application Code</span></span>

<span data-ttu-id="f6721-105">Die am häufigsten für die Ablaufverfolgung verwendeten Methoden zum Schreiben von Ausgaben in Listener: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert** und **Fail**.</span><span class="sxs-lookup"><span data-stu-id="f6721-105">The methods used most often for tracing are the methods for writing output to listeners: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert**, and **Fail**.</span></span> <span data-ttu-id="f6721-106">Diese Methoden können in zwei Kategorien unterteilt werden: **Write**, **WriteLine** und **Fail** geben alle Ausgaben ohne Bedingungen aus, während **WriteIf**, **WriteLineIf** und **Assert** eine boolesche Bedingung testen und die Ausgabe auf Basis des Werts dieser Bedingung erstellen oder nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6721-106">These methods can be divided into two categories: **Write**, **WriteLine**, and **Fail** all emit output unconditionally, whereas **WriteIf**, **WriteLineIf**, and **Assert** test a Boolean condition, and write or do not write based on the value of the condition.</span></span> <span data-ttu-id="f6721-107">**WriteIf** und **WriteLineIf** führen zu einer Ausgabe, wenn die Bedingung `true` entspricht. **Assert** führt zu einer Ausgabe, wenn die Bedingung `false` entspricht.</span><span class="sxs-lookup"><span data-stu-id="f6721-107">**WriteIf** and **WriteLineIf** emit output if the condition is `true`, and **Assert** emits output if the condition is `false`.</span></span>  
  
 <span data-ttu-id="f6721-108">Berücksichtigen Sie beim Entwerfen Ihrer Ablaufverfolgungs- und Debugstrategie, wie die Ausgabe aussehen soll.</span><span class="sxs-lookup"><span data-stu-id="f6721-108">When designing your tracing and debugging strategy, you should think about how you want the output to look.</span></span> <span data-ttu-id="f6721-109">Mehrere **Write** -Anweisungen, die mit nicht verknüpften Informationen gefüllt sind, erstellen ein Protokoll, das schwer zu lesen ist.</span><span class="sxs-lookup"><span data-stu-id="f6721-109">Multiple **Write** statements filled with unrelated information will create a log that is difficult to read.</span></span> <span data-ttu-id="f6721-110">Die Verwendung von **Write teline** zum Platzieren verwandter Anweisungen in separaten Zeilen kann es jedoch schwierig machen, zu unterscheiden, welche Informationen zusammengehören.</span><span class="sxs-lookup"><span data-stu-id="f6721-110">On the other hand, using **WriteLine** to put related statements on separate lines may make it difficult to distinguish what information belongs together.</span></span> <span data-ttu-id="f6721-111">Verwenden Sie im Allgemeinen mehrere **Write** -Anweisungen, wenn Sie Informationen aus mehreren Quellen kombinieren möchten, um eine einzelne informative Nachricht zu erstellen, und verwenden Sie die Anweisung "Write **teline** ", wenn Sie eine einzelne vollständige Meldung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f6721-111">In general, use multiple **Write** statements when you want to combine information from multiple sources to create a single informative message, and use the **WriteLine** statement when you want to create a single, complete message.</span></span>  
  
### <a name="to-write-a-complete-line"></a><span data-ttu-id="f6721-112">So schreiben Sie eine vollständige Zeile</span><span class="sxs-lookup"><span data-stu-id="f6721-112">To write a complete line</span></span>  
  
1. <span data-ttu-id="f6721-113">Rufen Sie die <xref:System.Diagnostics.Trace.WriteLine%2A>-Methode oder <xref:System.Diagnostics.Trace.WriteLineIf%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="f6721-113">Call the <xref:System.Diagnostics.Trace.WriteLine%2A> or <xref:System.Diagnostics.Trace.WriteLineIf%2A> method.</span></span>  
  
     <span data-ttu-id="f6721-114">Es wird ein Wagenrücklauf am Ende der von dieser Methode zurückgegebenen Nachricht angefügt, sodass die nächste von **Write**, **WriteIf**, **WriteLine** oder **WriteLineIf** zurückgegebene Nachricht in der darauffolgenden Zeile beginnt:</span><span class="sxs-lookup"><span data-stu-id="f6721-114">A carriage return is appended to the end of the message this method returns, so that the next message returned by **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the following line:</span></span>  
  
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
  
### <a name="to-write-a-partial-line"></a><span data-ttu-id="f6721-115">So schreiben Sie eine Teilzeile</span><span class="sxs-lookup"><span data-stu-id="f6721-115">To write a partial line</span></span>  
  
1. <span data-ttu-id="f6721-116">Rufen Sie die <xref:System.Diagnostics.Trace.Write%2A>-Methode oder <xref:System.Diagnostics.Trace.WriteIf%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="f6721-116">Call the <xref:System.Diagnostics.Trace.Write%2A> or <xref:System.Diagnostics.Trace.WriteIf%2A> method.</span></span>  
  
     <span data-ttu-id="f6721-117">Die nächste von **Write**, **WriteIf**, **WriteLine** oder **WriteLineIf** ausgegebene Nachricht beginnt auf derselben Zeile wie die Nachricht, die von **Write**- oder **WriteIf**-Anweisungen ausgegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="f6721-117">The next message put out by a **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the same line as the message put out by the **Write** or **WriteIf** statement:</span></span>  
  
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
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a><span data-ttu-id="f6721-118">So überprüfen Sie, ob bestimmte Bedingungen vor oder nach dem Ausführen einer Methode vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="f6721-118">To verify that certain conditions exist either before or after you execute a method</span></span>  
  
1. <span data-ttu-id="f6721-119">Rufen Sie die <xref:System.Diagnostics.Trace.Assert%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="f6721-119">Call the <xref:System.Diagnostics.Trace.Assert%2A> method.</span></span>  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="f6721-120">Sie können **Assert** bei der Ablaufverfolgung und beim Debuggen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6721-120">You can use **Assert** with both tracing and debugging.</span></span> <span data-ttu-id="f6721-121">In diesem Beispiel wird die Aufrufliste an alle Listener in der **Listener**-Auflistung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f6721-121">This example outputs the call stack to any listener in the **Listeners** collection.</span></span> <span data-ttu-id="f6721-122">Weitere Informationen finden Sie unter [Assertionen in verwaltetem Code](/visualstudio/debugger/assertions-in-managed-code) und <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6721-122">For more information, see [Assertions in Managed Code](/visualstudio/debugger/assertions-in-managed-code) and <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6721-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6721-123">See also</span></span>

- <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f6721-124">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f6721-124">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="f6721-125">Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern</span><span class="sxs-lookup"><span data-stu-id="f6721-125">How to: Create, Initialize and Configure Trace Switches</span></span>](how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="f6721-126">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="f6721-126">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="f6721-127">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="f6721-127">Trace Listeners</span></span>](trace-listeners.md)
