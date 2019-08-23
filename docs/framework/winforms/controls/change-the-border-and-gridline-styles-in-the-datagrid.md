---
title: 'Vorgehensweise: Ändern des Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: ebeca5f933eac4da2bf3d4f300866fd2ff52b32a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917669"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2e348-102">Vorgehensweise: Ändern des Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e348-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2e348-103">Mit dem <xref:System.Windows.Forms.DataGridView> -Steuerelement können Sie die Darstellung der Rahmen-und Gitternetz Linien des Steuer Elements anpassen, um die Benutzer Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="2e348-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="2e348-104">Sie können die Gitternetz Linien Farbe und die Rahmenart des Steuer Elements zusätzlich zu den Rahmen Stilen für die Zellen im Steuerelement ändern.</span><span class="sxs-lookup"><span data-stu-id="2e348-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="2e348-105">Sie können auch unterschiedliche Zell Rahmen Stile für normale Zellen, Zeilen Header Zellen und Spaltenheader Zellen anwenden.</span><span class="sxs-lookup"><span data-stu-id="2e348-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e348-106">Die Gitternetz Linien Farbe wird nur mit den <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>Werten <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, und <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> der <xref:System.Windows.Forms.DataGridViewCellBorderStyle> -Enumeration und dem <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> Wert der <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> -Enumeration verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e348-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="2e348-107">Bei den anderen Werten dieser Enumerationen werden vom Betriebssystem angegebene Farben verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e348-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="2e348-108">Wenn visuelle Stile unter Windows XP und der Windows Server 2003-Familie über die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> -Methode aktiviert sind, wird der <xref:System.Windows.Forms.DataGridView.GridColor%2A> -Eigenschafts Wert außerdem nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e348-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="2e348-109">So ändern Sie die Gitternetz Linien Farbe Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="2e348-109">To change the gridline color programmatically</span></span>  
  
- <span data-ttu-id="2e348-110">Legen Sie die <xref:System.Windows.Forms.DataGridView.GridColor%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="2e348-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="2e348-111">So ändern Sie die Rahmenart des gesamten DataGridView-Steuer Elements Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="2e348-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
- <span data-ttu-id="2e348-112">Legen Sie die <xref:System.Windows.Forms.DataGridView.BorderStyle%2A>-Eigenschaft auf einen der <xref:System.Windows.Forms.BorderStyle>-Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="2e348-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="2e348-113">So ändern Sie die Rahmen Stile für DataGridView-Zellen Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="2e348-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
- <span data-ttu-id="2e348-114">Legen Sie <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>die <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>Eigenschaften, <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> und fest.</span><span class="sxs-lookup"><span data-stu-id="2e348-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="2e348-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e348-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2e348-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2e348-116">Compiling the Code</span></span>  
 <span data-ttu-id="2e348-117">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2e348-117">This example requires:</span></span>  
  
- <span data-ttu-id="2e348-118">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="2e348-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="2e348-119">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e348-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e348-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e348-120">See also</span></span>

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="2e348-121">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e348-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
