---
title: 'Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters
Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine Komponente, die entspricht der [Übersicht über ereignisbasierte asynchrone Muster](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md). Das Formular für dieses Beispiel verwendet die `PrimeNumberCalculator` Komponente, die in beschriebenen [wie: implementieren eine Komponente, die das ereignisbasierte asynchrone Muster unterstützt](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Wenn Sie ein Projekt, die in diesem Beispiel verwendet ausführen, wird ein Formular "Primzahl Calculator" mit zwei Schaltflächen und ein Raster angezeigt: **neuen Task starten** und **"Abbrechen"**. Klicken Sie auf die **neuen Task starten** mehrmals nacheinander die Schaltfläche, und klicken, startet ein asynchroner Vorgang eine Berechnung aus, um festzustellen, ob eine zufällig generierter Testzahl eine Primzahl ist. Das Formular wird in regelmäßigen Abständen und inkrementelle Ergebnisse anzuzeigen. Jeder Vorgang ist eine eindeutige Aufgaben-ID zugewiesen. Das Ergebnis der Berechnung wird angezeigt, der **Ergebnis** Spalte; Wenn die Anzahl der Tests keine Primzahl ist, wird Sie als beschriftet **zusammengesetzt –** und seine erste Divisor wird angezeigt.  
  
 Alle ausstehenden Vorgang abgebrochen werden kann, mit der **"Abbrechen"** Schaltfläche. Mehrfachauswahl können vorgenommen werden.  
  
> [!NOTE]
>  Die meisten Zahlen ist es sich um Primzahlen nicht. Wenn Sie nicht nach mehreren abgeschlossenen Vorgänge eine Primzahl gefunden haben, einfach weitere Aufgaben starten und schließlich finden Sie einige Primzahlen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
