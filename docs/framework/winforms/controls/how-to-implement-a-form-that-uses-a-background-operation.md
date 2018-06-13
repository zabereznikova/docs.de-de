---
title: 'Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet'
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
ms.openlocfilehash: 5923895e1e6cf86f8de30405dbfdb0a603d708d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533295"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="de38f-102">Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="de38f-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="de38f-103">Mit dem folgenden Beispielprogramm wird ein Formular erstellt, das Fibonacci-Zahlen berechnet.</span><span class="sxs-lookup"><span data-stu-id="de38f-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="de38f-104">Die Berechnung erfolgt in einem separaten (vom Thread der Benutzeroberfläche unabhängigen) Thread, sodass die Benutzeroberfläche während der Berechnung weiterhin ohne Verzögerungen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="de38f-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="de38f-105">Visual Studio bietet umfassende Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="de38f-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="de38f-106">Siehe auch[Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="de38f-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="de38f-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de38f-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de38f-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="de38f-108">Compiling the Code</span></span>  
 <span data-ttu-id="de38f-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="de38f-109">This example requires:</span></span>  
  
-   <span data-ttu-id="de38f-110">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="de38f-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="de38f-111">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="de38f-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="de38f-112">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="de38f-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="de38f-113">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="de38f-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="de38f-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="de38f-114">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="de38f-115">Wenn Sie Multithreading verwenden, setzen Sie sich möglicherweise sehr ernsten und komplexen Problemen aus.</span><span class="sxs-lookup"><span data-stu-id="de38f-115">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="de38f-116">Beachten Sie die Informationen unter [Empfohlene Vorgehensweise für das verwaltete Threading](../../../../docs/standard/threading/managed-threading-best-practices.md), bevor Sie eine Projektmappe implementieren, die Multithreading verwendet.</span><span class="sxs-lookup"><span data-stu-id="de38f-116">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de38f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de38f-117">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="de38f-118">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="de38f-118">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="de38f-119">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="de38f-119">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)
