---
title: 'Vorgehensweise: Ausführen eines Vorgangs im Hintergrund'
description: Erfahren Sie, wie Sie mit der BackgroundWorker-Klasse einen zeitaufwändigen Windows Forms Vorgang im Hintergrund ausführen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 6b2a97f5acf1e906dfe141aee62e99a4e50dca9f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621573"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="e1bc9-103">Vorgehensweise: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="e1bc9-103">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="e1bc9-104">Gibt es einen Vorgang, der bis zu seinem Abschluss eine lange Zeit in Anspruch nimmt, und Sie möchten keine Verzögerungen in der Benutzeroberfläche verursachen, können Sie die <xref:System.ComponentModel.BackgroundWorker>-Klasse dazu verwenden, den Vorgang über einen anderen Thread auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e1bc9-104">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="e1bc9-105">Im folgenden Codebeispiel wird gezeigt, wie ein zeitaufwändiger Vorgang im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e1bc9-105">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="e1bc9-106">Das Formular verfügt über die Schaltflächen **Start** und **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="e1bc9-106">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="e1bc9-107">Klicken Sie auf die Schaltfläche **Start**, um einen asynchronen Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e1bc9-107">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="e1bc9-108">Klicken Sie auf die Schaltfläche **Abbrechen**, um einen aktiven asynchronen Vorgang anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="e1bc9-108">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="e1bc9-109">Das Ergebnis jedes Vorgangs wird in einem <xref:System.Windows.Forms.MessageBox>-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1bc9-109">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="e1bc9-110">Visual Studio bietet umfassende Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="e1bc9-110">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="e1bc9-111">Siehe auch [Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](walkthrough-running-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="e1bc9-111">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1bc9-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1bc9-112">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1bc9-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e1bc9-113">Compiling the Code</span></span>  
 <span data-ttu-id="e1bc9-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e1bc9-114">This example requires:</span></span>  
  
- <span data-ttu-id="e1bc9-115">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="e1bc9-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bc9-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1bc9-116">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="e1bc9-117">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="e1bc9-117">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="e1bc9-118">BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="e1bc9-118">BackgroundWorker Component</span></span>](backgroundworker-component.md)
