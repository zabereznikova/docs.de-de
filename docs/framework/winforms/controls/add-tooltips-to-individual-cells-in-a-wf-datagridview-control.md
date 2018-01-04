---
title: "Gewusst wie: Hinzufügen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a533f4cbf5000489e774ba8661c3ab03cea4948a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="1ca6a-102">Gewusst wie: Hinzufügen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ca6a-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1ca6a-103">Standardmäßig QuickInfos werden zum Anzeigen der Werte von <xref:System.Windows.Forms.DataGridView> Zellen, die zu klein, um den gesamten Inhalt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="1ca6a-104">Sie können dieses Verhalten jedoch überschreiben, um QuickInfo-Text-Werte für einzelne Zellen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="1ca6a-105">Dies ist hilfreich, die Benutzer zusätzliche Informationen zu einer Zelle angezeigt oder eine alternative Beschreibung des Zelleninhalts Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="1ca6a-106">Haben eine Zeile, die Statussymbolen anzeigt, sollten Sie erläuterungen zu den Text mithilfe von QuickInfos bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="1ca6a-107">Sie können die Anzeige von QuickInfos auf Zellenebene auch deaktivieren, indem die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="1ca6a-108">So fügen Sie eine QuickInfo auf eine Zelle hinzu</span><span class="sxs-lookup"><span data-stu-id="1ca6a-108">To add a ToolTip to a cell</span></span>  
  
-   <span data-ttu-id="1ca6a-109">Legen Sie die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1ca6a-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1ca6a-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="1ca6a-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1ca6a-111">This example requires:</span></span>  
  
-   <span data-ttu-id="1ca6a-112">Ein <xref:System.Windows.Forms.DataGridView> Steuerelement namens `dataGridView1` , enthält eine Spalte namens `Rating` für die Anzeige von Zeichenfolgenwerten, die von einem bis vier Sternchen ("*") Symbole.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("*") symbols.</span></span> <span data-ttu-id="1ca6a-113">Die <xref:System.Windows.Forms.DataGridView.CellFormatting> -Ereignisses des Steuerelements muss die Ereignishandlermethode, die im Beispiel gezeigte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
-   <span data-ttu-id="1ca6a-114">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1ca6a-115">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="1ca6a-115">Robust Programming</span></span>  
 <span data-ttu-id="1ca6a-116">Beim Binden der <xref:System.Windows.Forms.DataGridView> die Steuerung an eine externe Datenquelle oder eine eigene Datenquelle durch das Implementieren des virtuellen Modus bereitstellen, treten möglicherweise Leistungsprobleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="1ca6a-117">Um Leistungseinbußen zu vermeiden, bei der Arbeit mit großen Datenmengen, behandeln die <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> Ereignis statt der Einstellung der <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> Eigenschaft aus mehreren Zellen.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="1ca6a-118">Wenn Sie dieses Ereignis behandeln, Abrufen des Werts einer Zelle <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> Eigenschaft löst das-Ereignis aus und gibt den Wert der <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> -Eigenschaft im Ereignishandler angegeben.</span><span class="sxs-lookup"><span data-stu-id="1ca6a-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ca6a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ca6a-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="1ca6a-120">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ca6a-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
