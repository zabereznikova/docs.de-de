---
title: Feinabstimmung der Async-Anwendung (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: 34aa79da671f11dc53ac2b0306730d510fb09515
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fine-tuning-your-async-application-visual-basic"></a>Feinabstimmung der Async-Anwendung (Visual Basic)
Sie können Genauigkeit und Flexibilität Ihren asynchronen Anwendungen hinzufügen, indem Sie die Methoden und Eigenschaften verwenden, die der <xref:System.Threading.Tasks.Task>-Typ bereitstellt. Die Themen in diesem Abschnitt zeigen Beispiele, die das <xref:System.Threading.CancellationToken> und wichtige `Task`-Methoden wie <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> verwenden.  
  
 Mit `WhenAny` und `WhenAll` können Sie mehrere Aufgaben leichter starten und ihren Abschluss abwarten, indem Sie eine einzelne Aufgabe überwachen.  
  
-   `WhenAny` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn jede Aufgabe in einer Auflistung abgeschlossen ist.  
  
     Für Beispiele, in denen `WhenAny`, finden Sie unter ["Abbrechen" Verbleibende asynchrone Aufgaben nach einem Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)und [mehrere asynchrone Aufgaben starten und verarbeiten Sie Sie als sie vollständige (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
-   `WhenAll` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn alle Aufgaben in einer Auflistung abgeschlossen sind.  
  
     Weitere Informationen und ein Beispiel, verwendet `WhenAll`, finden Sie unter [wie: Erweitern der asynchronen Walkthrough mithilfe von "Task.WhenAll" (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Dieser Abschnitt enthält die folgenden Beispiele:  
  
-   [Brechen Sie eine asynchrone Aufgabe oder eine Liste von Aufgaben (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).  
  
-   ["Abbrechen" asynchrone Aufgaben nach einer Zeitperiode (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   ["Abbrechen" Verbleibende asynchrone Aufgaben nach einer vollständigen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [Mehrere asynchrone Aufgaben starten und Abschließen von (Visual Basic) zu verarbeiten](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.  
  
 Die Projekte erstellen eine Benutzeroberfläche mit einer Schaltfläche zum Starten und einer Schaltfläche zum Abbrechen des Prozesses, wie in der folgenden Abbildung ersichtlich. Die Schaltflächen werden mit `startButton` und `cancelButton` bezeichnet.  
  
 ![WPF-Fenster mit Schaltfläche „Abbrechen“](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Abbruch")  
  
 Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Async-Beispiel: Feinabstimmung der Anwendung)](http://go.microsoft.com/fwlink/?LinkId=255046) herunterladen.  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
