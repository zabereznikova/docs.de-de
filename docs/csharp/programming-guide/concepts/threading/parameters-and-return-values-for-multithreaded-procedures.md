---
title: "Parameter und Rückgabewerte für Multithreadprozeduren (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ba63c30c-d9f0-4962-b5c7-9d83ba851e6a
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fec0ad955439f0cd683ad56c8d6433eed2417304
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-c"></a>Parameter und Rückgabewerte für Multithreadprozeduren (C#)
Das Bereitstellen und Zurückgeben von Rückgabewerten in einer Multithreadanwendung ist kompliziert, weil der Konstruktor für die Threadklasse einen Verweis an eine Prozedur übergeben muss, die weder Argumente akzeptiert noch Werte zurückgibt. Im folgenden Abschnitt werden ein paar einfache Methoden gezeigt, um Parameter und Rückgabewerte von Prozeduren in separaten Threads bereitzustellen.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Bereitstellen von Parametern für Multithreadprozeduren  
 Die beste Möglichkeit, um Parameter für ein Multithread-Methodenaufruf bereitzustellen ist, die Zielmethode in eine Klasse zu umschließen und Felder für diese Klasse zu definieren, die als Parameter für den neuen Thread dienen. Der Vorteil dieses Ansatzes ist, dass Sie jedes Mal, wenn Sie einen neuen Thread starten möchten, eine neue Instanz der Klasse mit eigenen Parametern erstellen können. Nehmen wir z.B. an, dass Sie eine Funktion haben, die den Bereich eines Dreiecks wie im folgenden Code berechnet:  
  
```csharp  
double CalcArea(double Base, double Height)  
{  
    return 0.5 * Base * Height;  
}  
```  
  
 Sie können eine Klasse schreiben, die die `CalcArea`-Funktion umschließt und Felder erstellt, um Eingabeparameter wie folgt zu speichern:  
  
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
  
 Sie können zum Verwenden von `AreaClass` ein `AreaClass`-Objekt erstellen und die Eigenschaften `Base` und `Height` so festlegen, wie es im folgenden Code gezeigt wird:  
  
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
  
 Beachten Sie, dass die `TestArea`-Prozedur nicht den Wert des `Area`-Felds überprüft, nachdem sie die `CalcArea`-Methode aufgerufen hat. Da `CalcArea` in einem separaten Thread ausgeführt wird, besteht keine Garantie, dass das `Area`-Feld festgelegt wird, wenn Sie es sofort nach dem Aufruf von `Thread.Start` überprüfen. Im nächsten Abschnitt wird eine bessere Möglichkeit zum Zurückgeben von Werten aus Multithreadprozeduren beschrieben.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Rückgabe von Werten aus Multithreadprozeduren  
 Die Rückgabe von Werten aus Prozeduren, die in separaten Threads ausgeführt werden, wird dadurch erschwert, dass die Prozeduren weder Funktionen sein noch `ByRef`-Argumente verwenden können. Die einfachste Möglichkeit zum Zurückgeben von Werten ist, indem Sie die <xref:System.ComponentModel.BackgroundWorker>-Komponente zum Verwalten Ihrer Threads verwenden und ein Ereignis auslösen, wenn die Aufgabe erledigt ist, und das Ergebnis mit einem Ereignishandler verarbeiten.  
  
 Im folgenden Beispiel wird ein Wert durch das Auslösen eines Ereignisses von einer Prozedur zurückgegeben, die in einem separaten Thread ausgeführt wird:  
  
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
  
 Sie können Parameter und Rückgabewerte bereitstellen, indem Sie die optionale Zustandsobjektvariable `ByVal` der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>-Methode zu verwenden. Threads des Threadzeitgebers unterstützen für diesen Zweck auch ein Zustandsobjekt. Informationen über Threadpooling und Threadzeitgeber finden Sie unter [Thread Pooling (C#) (Pooling von Threads (C#))](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) und [Thread Timers (C#) (Threadzeitgeber (C#))](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (C#)](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [Thread Pooling (C#) (Pooling von Threads (C#))](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [Threadsynchronisierung (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [Ereignisse](../../../../csharp/programming-guide/events/index.md)  
 [Multithreaded Applications (C#) (Multithreadanwendungen (C#))](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Delegaten](../../../../csharp/programming-guide/delegates/index.md)  
 [Multithreading in Komponenten](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
