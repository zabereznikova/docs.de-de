---
title: 'Gewusst wie: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode'
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
ms.openlocfilehash: 9903a0357d1d8ceade21b590fd54c8cab517f134
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174744"
---
# <a name="how-to-add-trace-statements-to-application-code"></a><span data-ttu-id="5bcba-102">Gewusst wie: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode</span><span class="sxs-lookup"><span data-stu-id="5bcba-102">How to: Add Trace Statements to Application Code</span></span>
<span data-ttu-id="5bcba-103">Die am häufigsten für die Ablaufverfolgung verwendeten Methoden zum Schreiben von Ausgaben in Listener: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert** und **Fail**.</span><span class="sxs-lookup"><span data-stu-id="5bcba-103">The methods used most often for tracing are the methods for writing output to listeners: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert**, and **Fail**.</span></span> <span data-ttu-id="5bcba-104">Diese Methoden können in zwei Kategorien unterteilt werden: **Write**, **WriteLine** und **Fail** geben alle Ausgaben ohne Bedingungen aus, während **WriteIf**, **WriteLineIf** und **Assert** eine boolesche Bedingung testen und die Ausgabe auf Basis des Werts dieser Bedingung erstellen oder nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="5bcba-104">These methods can be divided into two categories: **Write**, **WriteLine**, and **Fail** all emit output unconditionally, whereas **WriteIf**, **WriteLineIf**, and **Assert** test a Boolean condition, and write or do not write based on the value of the condition.</span></span> <span data-ttu-id="5bcba-105">**WriteIf** und **WriteLineIf** führen zu einer Ausgabe, wenn die Bedingung `true` entspricht. **Assert** führt zu einer Ausgabe, wenn die Bedingung `false` entspricht.</span><span class="sxs-lookup"><span data-stu-id="5bcba-105">**WriteIf** and **WriteLineIf** emit output if the condition is `true`, and **Assert** emits output if the condition is `false`.</span></span>  
  
 <span data-ttu-id="5bcba-106">Berücksichtigen Sie beim Entwerfen Ihrer Ablaufverfolgungs- und Debugstrategie, wie die Ausgabe aussehen soll.</span><span class="sxs-lookup"><span data-stu-id="5bcba-106">When designing your tracing and debugging strategy, you should think about how you want the output to look.</span></span> <span data-ttu-id="5bcba-107">Mehrere **Write**-Anweisungen, die mit beziehungslosen Informationen gefüllt sind, erstellen ein Protokoll, das schwer zu lesen ist.</span><span class="sxs-lookup"><span data-stu-id="5bcba-107">Multiple **Write** statements filled with unrelated information will create a log that is difficult to read.</span></span> <span data-ttu-id="5bcba-108">Auf der anderen Seite kann möglicherweise schwer unterschieden werden, welche Informationen zusammengehören, wenn zusammengehörige Anweisungen mithilfe von **WriteLine** in separaten Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5bcba-108">On the other hand, using **WriteLine** to put related statements on separate lines may make it difficult to distinguish what information belongs together.</span></span> <span data-ttu-id="5bcba-109">Verwenden Sie im Allgemeinen mehrere **Write**-Anweisungen, wenn Sie Informationen aus mehreren Quellen zu einer einzelnen Informationsmeldung zusammenfassen möchten. Verwenden Sie die **WriteLine**-Anweisung, wenn Sie eine einzelne vollständige Meldung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="5bcba-109">In general, use multiple **Write** statements when you want to combine information from multiple sources to create a single informative message, and use the **WriteLine** statement when you want to create a single, complete message.</span></span>  
  
### <a name="to-write-a-complete-line"></a><span data-ttu-id="5bcba-110">So schreiben Sie eine vollständige Zeile</span><span class="sxs-lookup"><span data-stu-id="5bcba-110">To write a complete line</span></span>  
  
1. <span data-ttu-id="5bcba-111">Rufen Sie die <xref:System.Diagnostics.Trace.WriteLine%2A>-Methode oder <xref:System.Diagnostics.Trace.WriteLineIf%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="5bcba-111">Call the <xref:System.Diagnostics.Trace.WriteLine%2A> or <xref:System.Diagnostics.Trace.WriteLineIf%2A> method.</span></span>  
  
     <span data-ttu-id="5bcba-112">Es wird ein Wagenrücklauf am Ende der von dieser Methode zurückgegebenen Nachricht angefügt, sodass die nächste von **Write**, **WriteIf**, **WriteLine** oder **WriteLineIf** zurückgegebene Nachricht in der darauffolgenden Zeile beginnt:</span><span class="sxs-lookup"><span data-stu-id="5bcba-112">A carriage return is appended to the end of the message this method returns, so that the next message returned by **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the following line:</span></span>  
  
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
  
### <a name="to-write-a-partial-line"></a><span data-ttu-id="5bcba-113">So schreiben Sie eine Teilzeile</span><span class="sxs-lookup"><span data-stu-id="5bcba-113">To write a partial line</span></span>  
  
1. <span data-ttu-id="5bcba-114">Rufen Sie die <xref:System.Diagnostics.Trace.Write%2A>-Methode oder <xref:System.Diagnostics.Trace.WriteIf%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="5bcba-114">Call the <xref:System.Diagnostics.Trace.Write%2A> or <xref:System.Diagnostics.Trace.WriteIf%2A> method.</span></span>  
  
     <span data-ttu-id="5bcba-115">Die nächste von **Write**, **WriteIf**, **WriteLine** oder **WriteLineIf** ausgegebene Nachricht beginnt auf derselben Zeile wie die Nachricht, die von **Write**- oder **WriteIf**-Anweisungen ausgegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="5bcba-115">The next message put out by a **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the same line as the message put out by the **Write** or **WriteIf** statement:</span></span>  
  
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
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a><span data-ttu-id="5bcba-116">So überprüfen Sie, ob bestimmte Bedingungen vor oder nach dem Ausführen einer Methode vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="5bcba-116">To verify that certain conditions exist either before or after you execute a method</span></span>  
  
1. <span data-ttu-id="5bcba-117">Rufen Sie die <xref:System.Diagnostics.Trace.Assert%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="5bcba-117">Call the <xref:System.Diagnostics.Trace.Assert%2A> method.</span></span>  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="5bcba-118">Sie können **Assert** bei der Ablaufverfolgung und beim Debuggen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bcba-118">You can use **Assert** with both tracing and debugging.</span></span> <span data-ttu-id="5bcba-119">In diesem Beispiel wird die Aufrufliste an alle Listener in der **Listener**-Auflistung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="5bcba-119">This example outputs the call stack to any listener in the **Listeners** collection.</span></span> <span data-ttu-id="5bcba-120">Weitere Informationen finden Sie unter [Assertionen in verwaltetem Code](/visualstudio/debugger/assertions-in-managed-code) und <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5bcba-120">For more information, see [Assertions in Managed Code](/visualstudio/debugger/assertions-in-managed-code) and <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bcba-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5bcba-121">See also</span></span>

- <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5bcba-122">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="5bcba-122">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="5bcba-123">Gewusst wie: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern</span><span class="sxs-lookup"><span data-stu-id="5bcba-123">How to: Create, Initialize and Configure Trace Switches</span></span>](how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="5bcba-124">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="5bcba-124">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="5bcba-125">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="5bcba-125">Trace Listeners</span></span>](trace-listeners.md)
