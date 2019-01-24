---
title: 'Vorgehensweise: Ändern Sie die Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 052538f22c1da9836a61f66e3230e5e3e3cc72cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590889"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fd919-102">Vorgehensweise: Ändern Sie die Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd919-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fd919-103">Mit der <xref:System.Windows.Forms.DataGridView> -Steuerelement, können Sie die Darstellung von Rahmen und Gitternetzlinien auf die Verbesserung der benutzerfreundlichkeit des Steuerelements anpassen.</span><span class="sxs-lookup"><span data-stu-id="fd919-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="fd919-104">Sie können die Farbe der Gitternetzlinien und die Steuerelement-Rahmenart zusätzlich die Rahmenarten für die Zellen innerhalb des Steuerelements zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fd919-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="fd919-105">Sie können auch andere Zelle Rahmenarten für die normalen Zellen Zeilenheaderzellen und Spaltenheaderzellen anwenden.</span><span class="sxs-lookup"><span data-stu-id="fd919-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd919-106">Die Farbe der Gitternetzlinien wird verwendet, nur mit der <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, und <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> Werte von der <xref:System.Windows.Forms.DataGridViewCellBorderStyle> Enumeration und die <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> Wert der <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="fd919-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="fd919-107">Die anderen Werte dieser Enumerationen verwenden Sie Farben, die vom Betriebssystem angegeben.</span><span class="sxs-lookup"><span data-stu-id="fd919-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="fd919-108">Darüber hinaus, wenn visuelle Stile auf Windows XP und Windows Server 2003-Familie über aktiviert sind die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> -Methode, die <xref:System.Windows.Forms.DataGridView.GridColor%2A> Eigenschaftswert wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd919-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="fd919-109">So ändern Sie die Farbe der Gitternetzlinien programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="fd919-109">To change the gridline color programmatically</span></span>  
  
-   <span data-ttu-id="fd919-110">Legen Sie die <xref:System.Windows.Forms.DataGridView.GridColor%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="fd919-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="fd919-111">So ändern Sie die Rahmenart des gesamten DataGridView-Steuerelement programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="fd919-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
-   <span data-ttu-id="fd919-112">Legen Sie die <xref:System.Windows.Forms.DataGridView.BorderStyle%2A>-Eigenschaft auf einen der <xref:System.Windows.Forms.BorderStyle>-Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="fd919-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="fd919-113">So ändern Sie programmgesteuert die Rahmenarten für DataGridView-Zellen</span><span class="sxs-lookup"><span data-stu-id="fd919-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
-   <span data-ttu-id="fd919-114">Legen Sie die <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, und <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="fd919-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="fd919-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd919-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd919-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="fd919-116">Compiling the Code</span></span>  
 <span data-ttu-id="fd919-117">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fd919-117">This example requires:</span></span>  
  
-   <span data-ttu-id="fd919-118">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="fd919-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="fd919-119">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd919-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd919-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd919-120">See also</span></span>
- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="fd919-121">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd919-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
