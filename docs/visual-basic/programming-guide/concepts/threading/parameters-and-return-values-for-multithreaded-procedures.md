---
title: Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)
ms.date: 07/20/2015
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
ms.openlocfilehash: 039e9be6f174148995a83c842a442806b9409a3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648098"
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a><span data-ttu-id="64136-102">Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64136-102">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>
<span data-ttu-id="64136-103">Das Bereitstellen und Zurückgeben von Rückgabewerten in einer Multithreadanwendung ist kompliziert, weil der Konstruktor für die Threadklasse einen Verweis an eine Prozedur übergeben muss, die weder Argumente akzeptiert noch Werte zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="64136-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="64136-104">Im folgenden Abschnitt werden ein paar einfache Methoden gezeigt, um Parameter und Rückgabewerte von Prozeduren in separaten Threads bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="64136-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="64136-105">Bereitstellen von Parametern für Multithreadprozeduren</span><span class="sxs-lookup"><span data-stu-id="64136-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="64136-106">Die beste Möglichkeit, um Parameter für ein Multithread-Methodenaufruf bereitzustellen ist, die Zielmethode in eine Klasse zu umschließen und Felder für diese Klasse zu definieren, die als Parameter für den neuen Thread dienen.</span><span class="sxs-lookup"><span data-stu-id="64136-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="64136-107">Der Vorteil dieses Ansatzes ist, dass Sie jedes Mal, wenn Sie einen neuen Thread starten möchten, eine neue Instanz der Klasse mit eigenen Parametern erstellen können.</span><span class="sxs-lookup"><span data-stu-id="64136-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="64136-108">Nehmen wir z.B. an, dass Sie eine Funktion haben, die den Bereich eines Dreiecks wie im folgenden Code berechnet:</span><span class="sxs-lookup"><span data-stu-id="64136-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 <span data-ttu-id="64136-109">Sie können eine Klasse schreiben, die die `CalcArea`-Funktion umschließt und Felder erstellt, um Eingabeparameter wie folgt zu speichern:</span><span class="sxs-lookup"><span data-stu-id="64136-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
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
  
 <span data-ttu-id="64136-110">Sie können zum Verwenden von `AreaClass` ein `AreaClass`-Objekt erstellen und die Eigenschaften `Base` und `Height` so festlegen, wie es im folgenden Code gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="64136-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
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
  
 <span data-ttu-id="64136-111">Beachten Sie, dass die `TestArea`-Prozedur nicht den Wert des `Area`-Felds überprüft, nachdem sie die `CalcArea`-Methode aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="64136-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="64136-112">Da `CalcArea` in einem separaten Thread ausgeführt wird, besteht keine Garantie, dass das `Area`-Feld festgelegt wird, wenn Sie es sofort nach dem Aufruf von `Thread.Start` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="64136-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="64136-113">Im nächsten Abschnitt wird eine bessere Möglichkeit zum Zurückgeben von Werten aus Multithreadprozeduren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64136-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="64136-114">Rückgabe von Werten aus Multithreadprozeduren</span><span class="sxs-lookup"><span data-stu-id="64136-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="64136-115">Die Rückgabe von Werten aus Prozeduren, die in separaten Threads ausgeführt werden, wird dadurch erschwert, dass die Prozeduren weder Funktionen sein noch `ByRef`-Argumente verwenden können.</span><span class="sxs-lookup"><span data-stu-id="64136-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="64136-116">Die einfachste Möglichkeit zum Zurückgeben von Werten ist, indem Sie die <xref:System.ComponentModel.BackgroundWorker>-Komponente zum Verwalten Ihrer Threads verwenden und ein Ereignis auslösen, wenn die Aufgabe erledigt ist, und das Ergebnis mit einem Ereignishandler verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="64136-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="64136-117">Im folgenden Beispiel wird ein Wert durch das Auslösen eines Ereignisses von einer Prozedur zurückgegeben, die in einem separaten Thread ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="64136-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
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
  
 <span data-ttu-id="64136-118">Sie können Parameter und Rückgabewerte bereitstellen, indem Sie die optionale Zustandsobjektvariable `ByVal` der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>-Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="64136-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="64136-119">Threads des Threadzeitgebers unterstützen für diesen Zweck auch ein Zustandsobjekt.</span><span class="sxs-lookup"><span data-stu-id="64136-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="64136-120">Informationen über Threadpooling und Threadzeitgeber finden Sie unter [Threadpooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Threadpooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) und [Threadzeitgeber (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).</span><span class="sxs-lookup"><span data-stu-id="64136-120">For information on thread pooling and thread timers, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Thread Pooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) and [Thread Timers (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64136-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64136-121">See Also</span></span>  
 [<span data-ttu-id="64136-122">Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64136-122">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [<span data-ttu-id="64136-123">Threadpooling (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64136-123">Thread Pooling (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="64136-124">Threadsynchronisierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64136-124">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="64136-125">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="64136-125">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="64136-126">Multithreadanwendungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64136-126">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="64136-127">Delegaten</span><span class="sxs-lookup"><span data-stu-id="64136-127">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="64136-128">Multithreading in Komponenten</span><span class="sxs-lookup"><span data-stu-id="64136-128">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
