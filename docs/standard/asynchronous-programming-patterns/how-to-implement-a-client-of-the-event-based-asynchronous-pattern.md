---
title: 'Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
ms.openlocfilehash: f834ce4a0ec2208eee80ce8c3ffebfa6fdeeb5b1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289407"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters
Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine Komponente entsprechend der [Übersicht über ereignisbasierte asynchrone Muster](event-based-asynchronous-pattern-overview.md) verwenden. Das Formular für dieses Beispiel verwendet die `PrimeNumberCalculator`-Komponente, die unter [Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt](component-that-supports-the-event-based-asynchronous-pattern.md) beschrieben wird.  
  
 Wenn Sie ein Projekt mit diesem Beispiel ausführen, wird ein Formular namens „Primzahlenrechner“ mit einem Raster und zwei Schaltflächen angezeigt: **Neuen Task starten** und **Abbrechen**. Klicken Sie mehrmals hintereinander auf die Schaltfläche **Neuen Task starten**. Bei jedem Klick wird durch einen asynchronen Vorgang eine Berechnung gestartet, um festzustellen, ob es sich bei einer zufällig generierten Testzahl um eine Primzahl handelt. Das Formular zeigt in regelmäßigen Abständen den Status und inkrementelle Ergebnisse an. Jeder Vorgang ist einer eindeutige Aufgaben-ID zugewiesen. Das Ergebnis der Berechnung wird in der Spalte **Ergebnis** angezeigt. Wenn es sich bei der Testzahl nicht um eine Primzahl handelt, wird sie als **Zusammengesetzt** bezeichnet, und der erste Divisor wird angezeigt.  
  
 Alle ausstehenden Vorgänge können mit der Schaltfläche **Abbrechen** abgebrochen werden. Es kann eine Mehrfachauswahl vorgenommen werden.  
  
> [!NOTE]
> Bei den meisten Zahlen handelt es sich nicht um Primzahlen. Wenn Sie nicht nach mehreren abgeschlossenen Vorgänge eine Primzahl ermittelt haben, starten Sie einfach weitere Aufgaben, bis sie schließlich einige Primzahlen ermittelt haben.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
