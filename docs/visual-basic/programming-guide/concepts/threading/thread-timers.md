---
title: Threadzeitgeber (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 809cba93-cc93-4e21-afda-f299f9a39818
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9ea657482d4e8e1465d9bc6ae3f94915badee512
ms.lasthandoff: 03/13/2017

---
# <a name="thread-timers-visual-basic"></a>Threadzeitgeber (Visual Basic)
Die <xref:System.Threading.Timer?displayProperty=fullName>Klasse eignet sich für eine Aufgabe in regelmäßigen Abständen in einem separaten Thread ausführen.</xref:System.Threading.Timer?displayProperty=fullName> Beispielsweise können Sie einen Threadzeitgeber ein um den Status und die Integrität einer Datenbank zu überprüfen oder wichtige Dateien zu sichern.  
  
## <a name="thread-timer-example"></a>Beispiel für Threadzeitgeber  
 Im folgenden Beispiel wird eine Aufgabe alle zwei Sekunden gestartet und wird mit einem Flag initiiert die <xref:System.IDisposable.Dispose%2A>-Methode, die der Zeitgeber wird angehalten.</xref:System.IDisposable.Dispose%2A> In diesem Beispiel wird der Status an das Ausgabefenster übermittelt.  
  
```vb  
Private Class StateObjClass  
    ' Used to hold parameters for calls to TimerTask.  
    Public SomeValue As Integer  
    Public TimerReference As System.Threading.Timer  
    Public TimerCanceled As Boolean  
End Class  
  
Public Sub RunTimer()  
    Dim StateObj As New StateObjClass  
    StateObj.TimerCanceled = False  
    StateObj.SomeValue = 1  
    Dim TimerDelegate As New System.Threading.TimerCallback(AddressOf TimerTask)  
    ' Create a timer that calls a procedure every 2 seconds.  
    ' Note: There is no Start method; the timer starts running as soon as   
    ' the instance is created.  
    Dim TimerItem As New System.Threading.Timer(TimerDelegate, StateObj,  
                                                2000, 2000)  
    ' Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem  
  
    ' Run for ten loops.  
    While StateObj.SomeValue < 10  
        ' Wait one second.  
        System.Threading.Thread.Sleep(1000)  
    End While  
  
    ' Request Dispose of the timer object.  
    StateObj.TimerCanceled = True  
End Sub  
  
Private Sub TimerTask(ByVal StateObj As Object)  
    Dim State As StateObjClass = CType(StateObj, StateObjClass)  
    ' Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(State.SomeValue)  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " & Now.ToString)  
    If State.TimerCanceled Then  
        ' Dispose Requested.  
        State.TimerReference.Dispose()  
        System.Diagnostics.Debug.WriteLine("Done  " & Now)  
    End If  
End Sub  
```  
  
 Threadzeitgeber sind besonders nützlich, wenn die <xref:System.Windows.Forms.Timer?displayProperty=fullName>Objekt ist nicht verfügbar, z. B. Wenn Sie eine Konsole Anwendung entwickeln.</xref:System.Windows.Forms.Timer?displayProperty=fullName>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading></xref:System.Threading>   
 [Multithreadanwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
