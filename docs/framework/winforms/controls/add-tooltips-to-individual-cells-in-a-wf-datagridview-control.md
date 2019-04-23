---
title: 'Vorgehensweise: Hinzufügen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: 3307c92a13e5730de6dce0fe45b924e44b7af554
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119638"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="8c57a-102">Vorgehensweise: Hinzufügen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c57a-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8c57a-103">Standardmäßig QuickInfos werden zum Anzeigen der Werte von <xref:System.Windows.Forms.DataGridView> Zellen, die zu klein, um den gesamten Inhalt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c57a-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="8c57a-104">Sie können dieses Verhalten jedoch überschreiben, um die QuickInfo-Text-Werte für einzelne Zellen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="8c57a-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="8c57a-105">Dies ist hilfreich, die Benutzer zusätzliche Informationen zu einer Zelle angezeigt oder eine alternative Beschreibung des Zelleninhalts Benutzern anbieten.</span><span class="sxs-lookup"><span data-stu-id="8c57a-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="8c57a-106">Wenn Sie eine Zeile, die Statussymbole anzeigt verfügen, sollten Sie z. B. erklärungstexte, die mithilfe von QuickInfos bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8c57a-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="8c57a-107">Sie können auch die Anzeige von QuickInfos auf Zellenebene deaktivieren, durch Festlegen der <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="8c57a-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="8c57a-108">Eine QuickInfo auf eine Zelle hinzufügen</span><span class="sxs-lookup"><span data-stu-id="8c57a-108">To add a ToolTip to a cell</span></span>  
  
-   <span data-ttu-id="8c57a-109">Legen Sie die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="8c57a-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8c57a-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8c57a-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="8c57a-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8c57a-111">This example requires:</span></span>  
  
-   <span data-ttu-id="8c57a-112">Ein <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem Namen `dataGridView1` , enthält eine Spalte namens `Rating` für die Anzeige von Zeichenfolgenwerten, die von einem bis vier Sternchen ("\*") Symbole.</span><span class="sxs-lookup"><span data-stu-id="8c57a-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="8c57a-113">Die <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis des Steuerelements muss die Ereignishandlermethode, die im Beispiel gezeigte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="8c57a-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
-   <span data-ttu-id="8c57a-114">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c57a-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8c57a-115">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="8c57a-115">Robust Programming</span></span>  
 <span data-ttu-id="8c57a-116">Beim Binden der <xref:System.Windows.Forms.DataGridView> die Steuerung an eine externe Datenquelle oder eine eigene Datenquelle durch Implementieren des virtuellen Modus bereitstellen, treten möglicherweise Leistungsprobleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="8c57a-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="8c57a-117">Um eine Leistungseinbuße zu vermeiden, bei der Arbeit mit großen Mengen von Daten, verarbeiten die <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> Ereignis anstelle der Einstellung der <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> -Eigenschaft mehrerer Zellen.</span><span class="sxs-lookup"><span data-stu-id="8c57a-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="8c57a-118">Wenn Sie dieses Ereignis behandeln, beim Abrufen des Werts einer Zelle <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> Eigenschaft löst das-Ereignis aus und gibt den Wert des der <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> -Eigenschaft im Ereignishandler angegeben.</span><span class="sxs-lookup"><span data-stu-id="8c57a-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c57a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c57a-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8c57a-120">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c57a-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
