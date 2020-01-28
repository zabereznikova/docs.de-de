---
title: Hinzufügen von Quick Infos zu einzelnen Zellen im DataGridView-Steuerelement
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
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732180"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="bcf4e-102">Gewusst wie: Hinzufügen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bcf4e-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="bcf4e-103">Standardmäßig werden Quick Infos verwendet, um die Werte <xref:System.Windows.Forms.DataGridView> Zellen anzuzeigen, die zu klein sind, um den gesamten Inhalt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="bcf4e-104">Sie können dieses Verhalten jedoch überschreiben, um QuickInfo-Textwerte für einzelne Zellen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="bcf4e-105">Dies ist hilfreich, um Benutzern zusätzliche Informationen zu einer Zelle anzuzeigen oder Benutzern eine alternative Beschreibung der Zellen Inhalte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="bcf4e-106">Wenn Sie z. b. eine Zeile haben, in der Statussymbole angezeigt werden, können Sie mithilfe von Quick Infos Texterklärungen angeben.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="bcf4e-107">Sie können die Anzeige von Quick Infos auf Zellen Ebene auch deaktivieren, indem Sie die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>-Eigenschaft auf `false`festlegen.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="bcf4e-108">So fügen Sie einer Zelle eine QuickInfo hinzu</span><span class="sxs-lookup"><span data-stu-id="bcf4e-108">To add a ToolTip to a cell</span></span>  
  
- <span data-ttu-id="bcf4e-109">Legen Sie die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bcf4e-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="bcf4e-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="bcf4e-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bcf4e-111">This example requires:</span></span>  
  
- <span data-ttu-id="bcf4e-112">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte mit dem Namen `Rating` zum Anzeigen von Zeichen folgen Werten von einem bis vier Sternchen ("\*") enthält.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="bcf4e-113">Das <xref:System.Windows.Forms.DataGridView.CellFormatting>-Ereignis des-Steuer Elements muss der im Beispiel gezeigten Ereignishandlermethode zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
- <span data-ttu-id="bcf4e-114">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bcf4e-115">Robuste Programmierung</span><span class="sxs-lookup"><span data-stu-id="bcf4e-115">Robust Programming</span></span>  
 <span data-ttu-id="bcf4e-116">Wenn Sie das <xref:System.Windows.Forms.DataGridView> Steuerelement an eine externe Datenquelle binden oder durch Implementieren des virtuellen Modus eine eigene Datenquelle bereitstellen, treten möglicherweise Leistungsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="bcf4e-117">Um bei der Arbeit mit großen Datenmengen eine Leistungs Einbuße zu vermeiden, müssen Sie das <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>-Ereignis behandeln, anstatt die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>-Eigenschaft mehrerer Zellen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="bcf4e-118">Wenn Sie dieses Ereignis behandeln, wird durch das erhalten des Werts einer Zelle <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>-Eigenschaft das-Ereignis ausgelöst, und der Wert der <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType>-Eigenschaft wird entsprechend der Angabe im-Ereignishandler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bcf4e-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf4e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcf4e-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bcf4e-120">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bcf4e-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
