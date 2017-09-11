---
title: "Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6d1eb53454b6e0d964be15df2e320ce189e7d875
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a><span data-ttu-id="55adb-102">Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55adb-102">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>
<span data-ttu-id="55adb-103">Bereitstellung und Rückgabe von Werten in einer Multithreadanwendung ist kompliziert, da der Konstruktor für die Thread-Klasse einen Verweis auf eine Prozedur übergeben werden muss, die keine Argumente akzeptiert und keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="55adb-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="55adb-104">Die folgenden Abschnitte zeigen sich auf einfache Weise Parameter bereitgestellt und Werte aus Prozeduren in separaten Threads zurück.</span><span class="sxs-lookup"><span data-stu-id="55adb-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="55adb-105">Bereitstellen von Parametern für Multithreadprozeduren</span><span class="sxs-lookup"><span data-stu-id="55adb-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="55adb-106">Die beste Möglichkeit, Parameter für ein Multithread-Methodenaufruf ist die Zielmethode in eine Klasse einschließen, und definieren Sie Felder für diese Klasse, die als Parameter für den neuen Thread verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55adb-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="55adb-107">Der Vorteil dieses Ansatzes ist jedes Mal, wenn Sie einen neuen Thread starten möchten, können Sie eine neue Instanz der Klasse mit eigenen Parametern erstellen.</span><span class="sxs-lookup"><span data-stu-id="55adb-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="55adb-108">Nehmen wir beispielsweise an, dass Sie eine Funktion haben, die berechnet die Fläche eines Dreiecks, wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="55adb-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 <span data-ttu-id="55adb-109">Sie können eine Klasse, umschließt Schreiben der `CalcArea` -Funktion und Felder zum Speichern von Eingabeparametern wie folgt erstellt:</span><span class="sxs-lookup"><span data-stu-id="55adb-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
```vb  
Class AreaClass  
    Public Base As Double  
    Public Height As Double  
    Public Area As Double  
    Sub CalcArea()  
        Area = 0.5 * Base * Height  
        MessageBox.Show("The area is: " & Area.ToString)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="55adb-110">Verwenden der `AreaClass`, können Sie erstellen ein `AreaClass` Objekt, und legen die `Base` und `Height` Eigenschaften, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="55adb-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
```vb  
Protected Sub TestArea()  
    Dim AreaObject As New AreaClass  
    Dim Thread As New System.Threading.Thread(  
                        AddressOf AreaObject.CalcArea)  
    AreaObject.Base = 30  
    AreaObject.Height = 40  
    Thread.Start()  
End Sub  
```  
  
 <span data-ttu-id="55adb-111">Beachten Sie, dass die `TestArea` Prozedur überprüft nicht den Wert des der `Area` Feld nach dem Aufruf der `CalcArea` Methode.</span><span class="sxs-lookup"><span data-stu-id="55adb-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="55adb-112">Da `CalcArea` auf einem separaten Thread ausgeführt wird die `Area` Feld wird nicht unbedingt festgelegt werden, wenn Sie es sofort nach dem Aufruf von Einchecken `Thread.Start`.</span><span class="sxs-lookup"><span data-stu-id="55adb-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="55adb-113">Im nächsten Abschnitt wird eine bessere Möglichkeit zum Zurückgeben von Werten aus Multithreadprozeduren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55adb-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="55adb-114">Rückgabe von Werten aus Multithreadprozeduren</span><span class="sxs-lookup"><span data-stu-id="55adb-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="55adb-115">Rückgabe von Werten aus Prozeduren, die in separaten Threads ausgeführt wird durch die Tatsache, dass die Prozeduren können keine Funktionen sein und können keine verkompliziert `ByRef` Argumente.</span><span class="sxs-lookup"><span data-stu-id="55adb-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="55adb-116">Die einfachste Möglichkeit zum Zurückgeben von Werten ist die Verwendung der <xref:System.ComponentModel.BackgroundWorker>Komponente verwaltet die Threads nach Abschluss der Aufgabe ein Ereignis auszulösen, und die Ergebnisse mit einem Ereignishandler zu verarbeiten.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="55adb-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="55adb-117">Das folgende Beispiel gibt einen Wert zurück, durch das Auslösen eines Ereignisses aus einer Prozedur, die auf einem separaten Thread ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="55adb-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
```vb  
Private Class AreaClass2  
    Public Base As Double  
    Public Height As Double  
    Function CalcArea() As Double  
        ' Calculate the area of a triangle.  
        Return 0.5 * Base * Height  
    End Function  
End Class  
  
Private WithEvents BackgroundWorker1 As New System.ComponentModel.BackgroundWorker  
  
Private Sub TestArea2()  
    Dim AreaObject2 As New AreaClass2  
    AreaObject2.Base = 30  
    AreaObject2.Height = 40  
  
    ' Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2)  
End Sub  
  
' This method runs on the background thread when it starts.  
Private Sub BackgroundWorker1_DoWork(  
    ByVal sender As Object,   
    ByVal e As System.ComponentModel.DoWorkEventArgs  
    ) Handles BackgroundWorker1.DoWork  
  
    Dim AreaObject2 As AreaClass2 = CType(e.Argument, AreaClass2)  
    ' Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea()  
End Sub  
  
' This method runs on the main thread when the background thread finishes.  
Private Sub BackgroundWorker1_RunWorkerCompleted(  
    ByVal sender As Object,  
    ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
    ) Handles BackgroundWorker1.RunWorkerCompleted  
  
    ' Access the result through the Result property.  
    Dim Area As Double = CDbl(e.Result)  
    MessageBox.Show("The area is: " & Area.ToString)  
End Sub  
```  
  
 <span data-ttu-id="55adb-118">Angabe von Parametern und Rückgabewerte für Threadpool-Threads mithilfe des optionalen `ByVal` Zustandsobjekt Variable, der die <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>Methode.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="55adb-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="55adb-119">Threadzeitgeber-Threads unterstützen auch ein Zustandsobjekt für diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="55adb-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="55adb-120">Informationen über Threadpooling und Threadzeitgeber finden Sie unter [Threadpooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Threadpooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) und [Threadzeitgeber (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).</span><span class="sxs-lookup"><span data-stu-id="55adb-120">For information on thread pooling and thread timers, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Thread Pooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) and [Thread Timers (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55adb-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55adb-121">See Also</span></span>  
 <span data-ttu-id="55adb-122">[Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span><span class="sxs-lookup"><span data-stu-id="55adb-122">[Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span></span>  
<span data-ttu-id="55adb-123"> [Threadpooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span><span class="sxs-lookup"><span data-stu-id="55adb-123"> [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span></span>  
<span data-ttu-id="55adb-124"> [Threadsynchronisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="55adb-124"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span></span>  
<span data-ttu-id="55adb-125"> [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="55adb-125"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="55adb-126"> [Multithreadanwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="55adb-126"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="55adb-127"> [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="55adb-127"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="55adb-128"> [Multithreading in Komponenten](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)</span><span class="sxs-lookup"><span data-stu-id="55adb-128"> [Multithreading in Components](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)</span></span>
