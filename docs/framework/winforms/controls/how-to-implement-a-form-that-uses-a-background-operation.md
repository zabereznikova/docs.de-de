---
title: 'Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet'
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
ms.openlocfilehash: df7c6caf7b23824a596e94e1bd62205907b0b56a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592406"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="a7036-102">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="a7036-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="a7036-103">Mit dem folgenden Beispielprogramm wird ein Formular erstellt, das Fibonacci-Zahlen berechnet.</span><span class="sxs-lookup"><span data-stu-id="a7036-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="a7036-104">Die Berechnung erfolgt in einem separaten (vom Thread der Benutzeroberfläche unabhängigen) Thread, sodass die Benutzeroberfläche während der Berechnung weiterhin ohne Verzögerungen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a7036-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="a7036-105">Visual Studio bietet umfassende Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="a7036-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="a7036-106">Siehe auch [Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="a7036-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7036-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7036-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a7036-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a7036-108">Compiling the Code</span></span>  
 <span data-ttu-id="a7036-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a7036-109">This example requires:</span></span>  
  
- <span data-ttu-id="a7036-110">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="a7036-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a7036-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="a7036-111">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a7036-112">Wenn Sie Multithreading verwenden, setzen Sie sich möglicherweise sehr ernsten und komplexen Problemen aus.</span><span class="sxs-lookup"><span data-stu-id="a7036-112">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="a7036-113">Beachten Sie die Informationen unter [Empfohlene Vorgehensweise für das verwaltete Threading](../../../standard/threading/managed-threading-best-practices.md), bevor Sie eine Projektmappe implementieren, die Multithreading verwendet.</span><span class="sxs-lookup"><span data-stu-id="a7036-113">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7036-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7036-114">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="a7036-115">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="a7036-115">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="a7036-116">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="a7036-116">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
