---
title: Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)
ms.date: 07/20/2015
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
ms.openlocfilehash: 545da3e89d44c29c67784b5f01812d87350030c6
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874610"
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a>Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)
Das Bereitstellen und Zurückgeben von Rückgabewerten in einer Multithreadanwendung ist kompliziert, weil der Konstruktor für die Threadklasse einen Verweis an eine Prozedur übergeben muss, die weder Argumente akzeptiert noch Werte zurückgibt. Im folgenden Abschnitt werden ein paar einfache Methoden gezeigt, um Parameter und Rückgabewerte von Prozeduren in separaten Threads bereitzustellen.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Bereitstellen von Parametern für Multithreadprozeduren  
 Die beste Möglichkeit, um Parameter für ein Multithread-Methodenaufruf bereitzustellen ist, die Zielmethode in eine Klasse zu umschließen und Felder für diese Klasse zu definieren, die als Parameter für den neuen Thread dienen. Der Vorteil dieses Ansatzes ist, dass Sie jedes Mal, wenn Sie einen neuen Thread starten möchten, eine neue Instanz der Klasse mit eigenen Parametern erstellen können. Nehmen wir z.B. an, dass Sie eine Funktion haben, die den Bereich eines Dreiecks wie im folgenden Code berechnet:  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 Sie können eine Klasse schreiben, die die `CalcArea`-Funktion umschließt und Felder erstellt, um Eingabeparameter wie folgt zu speichern:  
  
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
  
 Sie können zum Verwenden von `AreaClass` ein `AreaClass`-Objekt erstellen und die Eigenschaften `Base` und `Height` so festlegen, wie es im folgenden Code gezeigt wird:  
  
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
  
 Beachten Sie, dass die `TestArea`-Prozedur nicht den Wert des `Area`-Felds überprüft, nachdem sie die `CalcArea`-Methode aufgerufen hat. Da `CalcArea` in einem separaten Thread ausgeführt wird, besteht keine Garantie, dass das `Area`-Feld festgelegt wird, wenn Sie es sofort nach dem Aufruf von `Thread.Start` überprüfen. Im nächsten Abschnitt wird eine bessere Möglichkeit zum Zurückgeben von Werten aus Multithreadprozeduren beschrieben.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Rückgabe von Werten aus Multithreadprozeduren  
 Die Rückgabe von Werten aus Prozeduren, die in separaten Threads ausgeführt werden, wird dadurch erschwert, dass die Prozeduren weder Funktionen sein noch `ByRef`-Argumente verwenden können. Die einfachste Möglichkeit zum Zurückgeben von Werten ist, indem Sie die <xref:System.ComponentModel.BackgroundWorker>-Komponente zum Verwalten Ihrer Threads verwenden und ein Ereignis auslösen, wenn die Aufgabe erledigt ist, und das Ergebnis mit einem Ereignishandler verarbeiten.  
  
 Im folgenden Beispiel wird ein Wert durch das Auslösen eines Ereignisses von einer Prozedur zurückgegeben, die in einem separaten Thread ausgeführt wird:  
  
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
  
 Sie können Parameter und Rückgabewerte bereitstellen, indem Sie die optionale Zustandsobjektvariable `ByVal` der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>-Methode zu verwenden. Threads des Threadzeitgebers unterstützen für diesen Zweck auch ein Zustandsobjekt. Weitere Informationen über Threadpooling und Threadzeitgeber finden Sie unter [Threadpooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Pooling von Threads](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) und [Timer](../../../../standard/threading/timers.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [Threadpooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [Threadsynchronisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Multithreadanwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Multithreading in Komponenten](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
