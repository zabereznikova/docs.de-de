---
title: 'Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet'
description: Erfahren Sie, wie Sie ein Windows Form implementieren, das einen Hintergrund Vorgang verwendet, damit ein Vorgang weiterhin ausgeführt werden kann, während ein anderer Vorgang ausgeführt wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: 23bf4bc02fbf998d92dfce6d84e4e337cbefe7d9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174522"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a>Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet
Mit dem folgenden Beispielprogramm wird ein Formular erstellt, das Fibonacci-Zahlen berechnet. Die Berechnung erfolgt in einem separaten (vom Thread der Benutzeroberfläche unabhängigen) Thread, sodass die Benutzeroberfläche während der Berechnung weiterhin ohne Verzögerungen ausgeführt wird.  
  
 Visual Studio bietet umfassende Unterstützung für diese Aufgabe.  
  
 Siehe auch[Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](walkthrough-implementing-a-form-that-uses-a-background-operation.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
> [!CAUTION]
> Wenn Sie Multithreading verwenden, setzen Sie sich möglicherweise sehr ernsten und komplexen Problemen aus. Beachten Sie die Informationen unter [Empfohlene Vorgehensweise für das verwaltete Threading](../../../standard/threading/managed-threading-best-practices.md), bevor Sie eine Projektmappe implementieren, die Multithreading verwendet.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [Empfohlene Vorgehensweise für das verwaltete Threading](../../../standard/threading/managed-threading-best-practices.md)
