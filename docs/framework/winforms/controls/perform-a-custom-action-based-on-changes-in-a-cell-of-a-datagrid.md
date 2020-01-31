---
title: Ausführen benutzerdefinierter Aktionen auf der Grundlage von Änderungen in einer Zelle des DataGridView-Steuer Elements
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: a809134b0a79bc9685c5b84acce58b4c61b5c526
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744281"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="82dc9-102">Gewusst wie: Ausführen einer benutzerdefinierten Aktion aufgrund von Änderungen in einer Zelle des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="82dc9-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="82dc9-103">Das <xref:System.Windows.Forms.DataGridView>-Steuerelement verfügt über eine Reihe von Ereignissen, die Sie verwenden können, um Änderungen im Status von <xref:System.Windows.Forms.DataGridView> Zellen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="82dc9-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="82dc9-104">Zwei der am häufigsten verwendeten Ereignisse sind die <xref:System.Windows.Forms.DataGridView.CellValueChanged>-und <xref:System.Windows.Forms.DataGridView.CellStateChanged>-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="82dc9-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="82dc9-105">So erkennen Sie Änderungen an den Werten von DataGridView-Zellen</span><span class="sxs-lookup"><span data-stu-id="82dc9-105">To detect changes in the values of DataGridView cells</span></span>  
  
- <span data-ttu-id="82dc9-106">Schreiben Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValueChanged>-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="82dc9-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="82dc9-107">So erkennen Sie Änderungen in den Zuständen von DataGridView-Zellen</span><span class="sxs-lookup"><span data-stu-id="82dc9-107">To detect changes in the states of DataGridView cells</span></span>  
  
- <span data-ttu-id="82dc9-108">Schreiben Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellStateChanged>-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="82dc9-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="82dc9-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="82dc9-109">Compiling the Code</span></span>  
 <span data-ttu-id="82dc9-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="82dc9-110">This example requires:</span></span>  
  
- <span data-ttu-id="82dc9-111">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="82dc9-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="82dc9-112">Für C#müssen die Ereignishandler mit den entsprechenden Ereignissen verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="82dc9-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
- <span data-ttu-id="82dc9-113">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="82dc9-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82dc9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82dc9-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="82dc9-115">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="82dc9-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="82dc9-116">Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="82dc9-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
