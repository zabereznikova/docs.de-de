---
title: 'Gewusst wie: Ausführen einer benutzerdefinierten Aktion aufgrund von Änderungen in einer Zelle des DataGridView-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: 3de58c1dd87d890f089366e6e85041f2983acc64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535144"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="1b576-102">Gewusst wie: Ausführen einer benutzerdefinierten Aktion aufgrund von Änderungen in einer Zelle des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b576-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1b576-103">Die <xref:System.Windows.Forms.DataGridView> Steuerelement verfügt über eine Anzahl von Ereignissen Sie zum Erkennen von Änderungen in den Status der können <xref:System.Windows.Forms.DataGridView> Zellen.</span><span class="sxs-lookup"><span data-stu-id="1b576-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="1b576-104">Die beiden am häufigsten verwendeten sind die <xref:System.Windows.Forms.DataGridView.CellValueChanged> und <xref:System.Windows.Forms.DataGridView.CellStateChanged> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="1b576-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="1b576-105">Zum Erkennen von Änderungen in die Werte von DataGridView-Zellen</span><span class="sxs-lookup"><span data-stu-id="1b576-105">To detect changes in the values of DataGridView cells</span></span>  
  
-   <span data-ttu-id="1b576-106">Schreiben Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValueChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1b576-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="1b576-107">Zum Erkennen von Änderungen in den Status von DataGridView-Zellen</span><span class="sxs-lookup"><span data-stu-id="1b576-107">To detect changes in the states of DataGridView cells</span></span>  
  
-   <span data-ttu-id="1b576-108">Schreiben Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellStateChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1b576-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1b576-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1b576-109">Compiling the Code</span></span>  
 <span data-ttu-id="1b576-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1b576-110">This example requires:</span></span>  
  
-   <span data-ttu-id="1b576-111">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="1b576-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="1b576-112">Bei c# müssen die Ereignishandler mit den entsprechenden Ereignissen verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="1b576-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
-   <span data-ttu-id="1b576-113">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b576-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b576-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b576-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>  
 [<span data-ttu-id="1b576-115">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b576-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 [<span data-ttu-id="1b576-116">Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b576-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
