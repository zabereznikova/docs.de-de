---
title: 'Vorgehensweise: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: e216a91a612c5d4370d5786492426f757f39a262
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658090"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2c903-102">Vorgehensweise: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c903-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2c903-103">Wenn Sie die Neuanordnung von Spalten im <xref:System.Windows.Forms.DataGridView>-Steuerelement aktivieren, können die Benutzer eine Spalte an eine neuen Position ziehen, indem sie den Spaltenkopf mit der Maus ziehen.</span><span class="sxs-lookup"><span data-stu-id="2c903-103">When you enable column reordering in the <xref:System.Windows.Forms.DataGridView> control, users can move a column to a new position by dragging the column header with the mouse.</span></span> <span data-ttu-id="2c903-104">Im <xref:System.Windows.Forms.DataGridView>-Steuerelement bestimmt der Wert der Eigenschaftswert <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>, ob Benutzer Spalten an andere Positionen ziehen können.</span><span class="sxs-lookup"><span data-stu-id="2c903-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property value determines whether users can move columns to different positions.</span></span>  
  
 <span data-ttu-id="2c903-105">Visual Studio bietet Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="2c903-105">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="2c903-106">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Aktivieren der Neuanordnung von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](https://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="2c903-106">Also see [How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))</span></span>  
  
### <a name="to-enable-column-reordering-programmatically"></a><span data-ttu-id="2c903-107">So aktivieren Sie die Neuanordnung von Spalten programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="2c903-107">To enable column reordering programmatically</span></span>  
  
-   <span data-ttu-id="2c903-108">Legen Sie die <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="2c903-108">Set the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2c903-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2c903-109">Compiling the Code</span></span>  
 <span data-ttu-id="2c903-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2c903-110">This example requires:</span></span>  
  
-   <span data-ttu-id="2c903-111">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="2c903-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="2c903-112">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c903-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c903-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c903-113">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2c903-114">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c903-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="2c903-115">Vorgehensweise: Einfrieren von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c903-115">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
