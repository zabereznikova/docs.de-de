---
title: 'Vorgehensweise: Ausführen einer benutzerdefinierten Aktion basierend auf Änderungen in einer Zelle des DataGridView-Steuerelement für eine Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: 125da277c2db44f01e6cad8cea08fbd927234f09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686854"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="287c6-102">Vorgehensweise: Ausführen einer benutzerdefinierten Aktion basierend auf Änderungen in einer Zelle des DataGridView-Steuerelement für eine Windows Forms</span><span class="sxs-lookup"><span data-stu-id="287c6-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="287c6-103">Die <xref:System.Windows.Forms.DataGridView> Steuerelement hat eine Anzahl von Ereignissen Sie zum Erkennen von Änderungen in den Zustand des können <xref:System.Windows.Forms.DataGridView> Zellen.</span><span class="sxs-lookup"><span data-stu-id="287c6-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="287c6-104">Die beiden am häufigsten verwendeten sind die <xref:System.Windows.Forms.DataGridView.CellValueChanged> und <xref:System.Windows.Forms.DataGridView.CellStateChanged> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="287c6-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="287c6-105">Zum Erkennen von Änderungen in die Werte von DataGridView-Zellen</span><span class="sxs-lookup"><span data-stu-id="287c6-105">To detect changes in the values of DataGridView cells</span></span>  
  
-   <span data-ttu-id="287c6-106">Schreiben Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CellValueChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="287c6-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="287c6-107">Änderungen am Zustand der DataGridView-Zellen erkannt</span><span class="sxs-lookup"><span data-stu-id="287c6-107">To detect changes in the states of DataGridView cells</span></span>  
  
-   <span data-ttu-id="287c6-108">Schreiben Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CellStateChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="287c6-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="287c6-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="287c6-109">Compiling the Code</span></span>  
 <span data-ttu-id="287c6-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="287c6-110">This example requires:</span></span>  
  
-   <span data-ttu-id="287c6-111">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="287c6-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="287c6-112">Für C#, die Ereignishandler müssen eine Verbindung mit den entsprechenden Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="287c6-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
-   <span data-ttu-id="287c6-113">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="287c6-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287c6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="287c6-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="287c6-115">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="287c6-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="287c6-116">Exemplarische Vorgehensweise: Überprüfen von Daten in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="287c6-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
