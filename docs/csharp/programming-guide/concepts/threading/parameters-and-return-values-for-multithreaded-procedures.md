---
title: Parameter und Rückgabewerte für Multithreadprozeduren (C#)
ms.date: 07/20/2015
ms.assetid: ba63c30c-d9f0-4962-b5c7-9d83ba851e6a
ms.openlocfilehash: e27f8e67ff03260e1d13fa633064efc2059e6bdf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340215"
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-c"></a><span data-ttu-id="73c0b-102">Parameter und Rückgabewerte für Multithreadprozeduren (C#)</span><span class="sxs-lookup"><span data-stu-id="73c0b-102">Parameters and Return Values for Multithreaded Procedures (C#)</span></span>
<span data-ttu-id="73c0b-103">Das Bereitstellen und Zurückgeben von Rückgabewerten in einer Multithreadanwendung ist kompliziert, weil der Konstruktor für die Threadklasse einen Verweis an eine Prozedur übergeben muss, die weder Argumente akzeptiert noch Werte zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="73c0b-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="73c0b-104">Im folgenden Abschnitt werden ein paar einfache Methoden gezeigt, um Parameter und Rückgabewerte von Prozeduren in separaten Threads bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="73c0b-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="73c0b-105">Bereitstellen von Parametern für Multithreadprozeduren</span><span class="sxs-lookup"><span data-stu-id="73c0b-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="73c0b-106">Die beste Möglichkeit, um Parameter für ein Multithread-Methodenaufruf bereitzustellen ist, die Zielmethode in eine Klasse zu umschließen und Felder für diese Klasse zu definieren, die als Parameter für den neuen Thread dienen.</span><span class="sxs-lookup"><span data-stu-id="73c0b-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="73c0b-107">Der Vorteil dieses Ansatzes ist, dass Sie jedes Mal, wenn Sie einen neuen Thread starten möchten, eine neue Instanz der Klasse mit eigenen Parametern erstellen können.</span><span class="sxs-lookup"><span data-stu-id="73c0b-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="73c0b-108">Nehmen wir z.B. an, dass Sie eine Funktion haben, die den Bereich eines Dreiecks wie im folgenden Code berechnet:</span><span class="sxs-lookup"><span data-stu-id="73c0b-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```csharp  
double CalcArea(double Base, double Height)  
{  
    return 0.5 * Base * Height;  
}  
```  
  
 <span data-ttu-id="73c0b-109">Sie können eine Klasse schreiben, die die `CalcArea`-Funktion umschließt und Felder erstellt, um Eingabeparameter wie folgt zu speichern:</span><span class="sxs-lookup"><span data-stu-id="73c0b-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
```csharp  
class AreaClass  
{  
    public double Base;  
    public double Height;  
    public double Area;  
    public void CalcArea()  
    {  
        Area = 0.5 * Base * Height;  
        MessageBox.Show("The area is: " + Area.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="73c0b-110">Sie können zum Verwenden von `AreaClass` ein `AreaClass`-Objekt erstellen und die Eigenschaften `Base` und `Height` so festlegen, wie es im folgenden Code gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="73c0b-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
```csharp  
protected void TestArea()  
{  
    AreaClass AreaObject = new AreaClass();  
  
    System.Threading.Thread Thread =  
        new System.Threading.Thread(AreaObject.CalcArea);  
    AreaObject.Base = 30;  
    AreaObject.Height = 40;  
    Thread.Start();  
}  
```  
  
 <span data-ttu-id="73c0b-111">Beachten Sie, dass die `TestArea`-Prozedur nicht den Wert des `Area`-Felds überprüft, nachdem sie die `CalcArea`-Methode aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="73c0b-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="73c0b-112">Da `CalcArea` in einem separaten Thread ausgeführt wird, besteht keine Garantie, dass das `Area`-Feld festgelegt wird, wenn Sie es sofort nach dem Aufruf von `Thread.Start` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="73c0b-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="73c0b-113">Im nächsten Abschnitt wird eine bessere Möglichkeit zum Zurückgeben von Werten aus Multithreadprozeduren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="73c0b-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="73c0b-114">Rückgabe von Werten aus Multithreadprozeduren</span><span class="sxs-lookup"><span data-stu-id="73c0b-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="73c0b-115">Die Rückgabe von Werten aus Prozeduren, die in separaten Threads ausgeführt werden, wird dadurch erschwert, dass die Prozeduren weder Funktionen sein noch `ByRef`-Argumente verwenden können.</span><span class="sxs-lookup"><span data-stu-id="73c0b-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="73c0b-116">Die einfachste Möglichkeit zum Zurückgeben von Werten ist, indem Sie die <xref:System.ComponentModel.BackgroundWorker>-Komponente zum Verwalten Ihrer Threads verwenden und ein Ereignis auslösen, wenn die Aufgabe erledigt ist, und das Ergebnis mit einem Ereignishandler verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="73c0b-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="73c0b-117">Im folgenden Beispiel wird ein Wert durch das Auslösen eines Ereignisses von einer Prozedur zurückgegeben, die in einem separaten Thread ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="73c0b-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
```csharp  
class AreaClass2  
{  
    public double Base;  
    public double Height;  
    public double CalcArea()  
    {  
        // Calculate the area of a triangle.  
        return 0.5 * Base * Height;  
    }  
}  
  
private System.ComponentModel.BackgroundWorker BackgroundWorker1  
    = new System.ComponentModel.BackgroundWorker();  
  
private void TestArea2()  
{  
    InitializeBackgroundWorker();  
  
    AreaClass2 AreaObject2 = new AreaClass2();  
    AreaObject2.Base = 30;  
    AreaObject2.Height = 40;  
  
    // Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2);  
}  
  
private void InitializeBackgroundWorker()  
{  
    // Attach event handlers to the BackgroundWorker object.  
    BackgroundWorker1.DoWork +=  
        new System.ComponentModel.DoWorkEventHandler(BackgroundWorker1_DoWork);  
    BackgroundWorker1.RunWorkerCompleted +=  
        new System.ComponentModel.RunWorkerCompletedEventHandler(BackgroundWorker1_RunWorkerCompleted);  
}  
  
private void BackgroundWorker1_DoWork(  
    object sender,  
    System.ComponentModel.DoWorkEventArgs e)  
{  
    AreaClass2 AreaObject2 = (AreaClass2)e.Argument;  
    // Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea();  
}  
  
private void BackgroundWorker1_RunWorkerCompleted(  
    object sender,  
    System.ComponentModel.RunWorkerCompletedEventArgs e)  
{  
    // Access the result through the Result property.  
    double Area = (double)e.Result;  
    MessageBox.Show("The area is: " + Area.ToString());  
}  
```  
  
 <span data-ttu-id="73c0b-118">Sie können Parameter und Rückgabewerte bereitstellen, indem Sie die optionale Zustandsobjektvariable `ByVal` der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>-Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="73c0b-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="73c0b-119">Threads des Threadzeitgebers unterstützen für diesen Zweck auch ein Zustandsobjekt.</span><span class="sxs-lookup"><span data-stu-id="73c0b-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="73c0b-120">Informationen über Threadpooling und Threadzeitgeber finden Sie unter [Thread Pooling (C#) (Pooling von Threads (C#))](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) und [Thread Timers (C#) (Threadzeitgeber (C#))](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).</span><span class="sxs-lookup"><span data-stu-id="73c0b-120">For information on thread pooling and thread timers, see [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) and [Thread Timers (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c0b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73c0b-121">See Also</span></span>  
 [<span data-ttu-id="73c0b-122">Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (C#)</span><span class="sxs-lookup"><span data-stu-id="73c0b-122">Walkthrough: Multithreading with the BackgroundWorker Component (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [<span data-ttu-id="73c0b-123">Thread Pooling (C#) (Pooling von Threads (C#))</span><span class="sxs-lookup"><span data-stu-id="73c0b-123">Thread Pooling (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="73c0b-124">Threadsynchronisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="73c0b-124">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="73c0b-125">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="73c0b-125">Events</span></span>](../../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="73c0b-126">Multithreaded Applications (C#) (Multithreadanwendungen (C#))</span><span class="sxs-lookup"><span data-stu-id="73c0b-126">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="73c0b-127">Delegaten</span><span class="sxs-lookup"><span data-stu-id="73c0b-127">Delegates</span></span>](../../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="73c0b-128">Multithreading in Komponenten</span><span class="sxs-lookup"><span data-stu-id="73c0b-128">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
