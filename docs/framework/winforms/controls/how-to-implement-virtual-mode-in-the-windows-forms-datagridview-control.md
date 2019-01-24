---
title: 'Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: d9583c9fd7a5e20e631395ad2423a45b911f8ca3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727650"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="48776-102">Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48776-102">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="48776-103">Im folgenden Codebeispiel wird veranschaulicht, wie große Datenmengen mithilfe eines <xref:System.Windows.Forms.DataGridView>-Steuerelements verwaltet werden, dessen <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="48776-103">The following code example demonstrates how to manage large sets of data using a <xref:System.Windows.Forms.DataGridView> control with its <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property set to `true`.</span></span>  
  
 <span data-ttu-id="48776-104">Eine vollständige Erläuterung dieses Codebeispiels, finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="48776-104">For a complete explanation of this code example, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="48776-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48776-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="48776-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="48776-106">Compiling the Code</span></span>  
 <span data-ttu-id="48776-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="48776-107">This example requires:</span></span>  
  
-   <span data-ttu-id="48776-108">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="48776-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="48776-109">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="48776-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="48776-110">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="48776-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="48776-111">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="48776-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48776-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48776-112">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="48776-113">Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48776-113">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
- [<span data-ttu-id="48776-114">Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48776-114">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="48776-115">Virtueller Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48776-115">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)
