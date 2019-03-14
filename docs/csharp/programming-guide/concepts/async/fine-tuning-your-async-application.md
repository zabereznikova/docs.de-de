---
title: Feinabstimmung der Async-Anwendung (C#)
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: 31d9fcf04780d421faa609e06e18e66e0e8b9ce7
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679164"
---
# <a name="fine-tuning-your-async-application-c"></a>Feinabstimmung der Async-Anwendung (C#)
Sie können Genauigkeit und Flexibilität Ihren asynchronen Anwendungen hinzufügen, indem Sie die Methoden und Eigenschaften verwenden, die der <xref:System.Threading.Tasks.Task>-Typ bereitstellt. Die Themen in diesem Abschnitt zeigen Beispiele, die das <xref:System.Threading.CancellationToken> und wichtige `Task`-Methoden wie <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> verwenden.  
  
 Mit `WhenAny` und `WhenAll` können Sie mehrere Aufgaben leichter starten und ihren Abschluss abwarten, indem Sie eine einzelne Aufgabe überwachen.  
  
-   `WhenAny` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn jede Aufgabe in einer Auflistung abgeschlossen ist.  
  
     Beispiele für die Verwendung von `WhenAny` finden Sie unter [Cancel Remaining Async Tasks after One Is Complete (C#) (Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#))](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) und [Start Multiple Async Tasks and Process Them As They Complete (C#) (Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#))](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
-   `WhenAll` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn alle Aufgaben in einer Auflistung abgeschlossen sind.  
  
     Weitere Informationen und ein Beispiel mit `WhenAll` finden Sie unter [Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Dieser Abschnitt enthält die folgenden Beispiele:  
  
-   [Cancel an Async Task or a List of Tasks (C#) (Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#))](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)  
  
-   [Cancel Async Tasks after a Period of Time (C#) (Asynchrone Aufgaben nach einer Zeitperiode abbrechen (C#))](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [Cancel Remaining Async Tasks after One Is Complete (C#) (Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#))](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [Start Multiple Async Tasks and Process Them As They Complete (C#) (Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#))](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.  
  
 Die Projekte erstellen eine Benutzeroberfläche mit einer Schaltfläche zum Starten und einer Schaltfläche zum Abbrechen des Prozesses, wie in der folgenden Abbildung ersichtlich. Die Schaltflächen werden mit `startButton` und `cancelButton` bezeichnet.  
  
 ![WPF-Fenster mit der Schaltfläche „Abbrechen“](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialogfeld mit der Schaltfläche „Start“ und „Anhalten“")  
  
 Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen.  
  
## <a name="see-also"></a>Siehe auch

- [Asynchrone Programmierung mit „async“ und „await“ (C#)](../../../../csharp/programming-guide/concepts/async/index.md)
