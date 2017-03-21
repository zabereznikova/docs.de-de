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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d5d8adde531d31aa6bf353f53bd4cfecc084f515
ms.lasthandoff: 03/13/2017

---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a>Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)
Bereitstellung und Rückgabe von Werten in einer Multithreadanwendung ist kompliziert, da der Konstruktor für die Thread-Klasse einen Verweis auf eine Prozedur übergeben werden muss, die keine Argumente akzeptiert und keinen Wert zurückgibt. Die folgenden Abschnitte zeigen sich auf einfache Weise Parameter bereitgestellt und Werte aus Prozeduren in separaten Threads zurück.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Bereitstellen von Parametern für Multithreadprozeduren  
 Die beste Möglichkeit, Parameter für ein Multithread-Methodenaufruf ist die Zielmethode in eine Klasse einschließen, und definieren Sie Felder für diese Klasse, die als Parameter für den neuen Thread verwendet werden. Der Vorteil dieses Ansatzes ist jedes Mal, wenn Sie einen neuen Thread starten möchten, können Sie eine neue Instanz der Klasse mit eigenen Parametern erstellen. Nehmen wir beispielsweise an, dass Sie eine Funktion haben, die berechnet die Fläche eines Dreiecks, wie im folgenden Code:  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 Sie können eine Klasse, umschließt Schreiben der `CalcArea` -Funktion und Felder zum Speichern von Eingabeparametern wie folgt erstellt:  
  
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
  
 Verwenden der `AreaClass`, können Sie erstellen ein `AreaClass` Objekt, und legen die `Base` und `Height` Eigenschaften, wie im folgenden Code gezeigt:  
  
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
  
 Beachten Sie, dass die `TestArea` Prozedur überprüft nicht den Wert des der `Area` Feld nach dem Aufruf der `CalcArea` Methode. Da `CalcArea` auf einem separaten Thread ausgeführt wird die `Area` Feld wird nicht unbedingt festgelegt werden, wenn Sie es sofort nach dem Aufruf von Einchecken `Thread.Start`. Im nächsten Abschnitt wird eine bessere Möglichkeit zum Zurückgeben von Werten aus Multithreadprozeduren beschrieben.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Rückgabe von Werten aus Multithreadprozeduren  
 Rückgabe von Werten aus Prozeduren, die in separaten Threads ausgeführt wird durch die Tatsache, dass die Prozeduren können keine Funktionen sein und können keine verkompliziert `ByRef` Argumente. Die einfachste Möglichkeit zum Zurückgeben von Werten ist die Verwendung der <xref:System.ComponentModel.BackgroundWorker>Komponente verwaltet die Threads nach Abschluss der Aufgabe ein Ereignis auszulösen, und die Ergebnisse mit einem Ereignishandler zu verarbeiten.</xref:System.ComponentModel.BackgroundWorker>  
  
 Das folgende Beispiel gibt einen Wert zurück, durch das Auslösen eines Ereignisses aus einer Prozedur, die auf einem separaten Thread ausgeführt wird:  
  
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
  
 Angabe von Parametern und Rückgabewerte für Threadpool-Threads mithilfe des optionalen `ByVal` Zustandsobjekt Variable, der die <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>Methode.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> Threadzeitgeber-Threads unterstützen auch ein Zustandsobjekt für diesen Zweck. Informationen über Threadpooling und Threadzeitgeber finden Sie unter [Threadpooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Threadpooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) und [Threadzeitgeber (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)   
 [Threadpooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)   
 [Threadsynchronisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)   
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Multithreadanwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Multithreading in Komponenten](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
