---
title: 'Gewusst wie: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: 7e3e281a766e22ed76bbf6ae7726cba092a9741d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538860"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="79f09-102">Gewusst wie: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79f09-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="79f09-103">Die folgenden Prozeduren veranschaulichen einfache Formatierung von Zellenwerten durch die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> Eigenschaft ein <xref:System.Windows.Forms.DataGridView> Steuerelement und für bestimmte Spalten in einem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="79f09-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="79f09-104">Informationen zum erweiterten Daten zu formatieren, finden Sie unter [wie: Anpassen der Datenformatierung im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="79f09-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="79f09-105">Formatieren von Währung und Datumswerte</span><span class="sxs-lookup"><span data-stu-id="79f09-105">To format currency and date values</span></span>  
  
-   <span data-ttu-id="79f09-106">Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="79f09-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="79f09-107">Das folgende Codebeispiel legt das Format für bestimmte Spalten mithilfe der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> -Eigenschaft der Spalten.</span><span class="sxs-lookup"><span data-stu-id="79f09-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="79f09-108">Werte in der `UnitPrice` Spalte in der aktuellen kulturspezifischen Währungsformat angezeigt werden, mit negativen Werten, die in Klammern eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="79f09-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="79f09-109">Werte in der `ShipDate` Spalte in der aktuellen kulturspezifischen kurzen Datumsformat angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="79f09-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="79f09-110">Weitere Informationen zu <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> -Werte finden Sie in [Formatierung von Typen](../../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="79f09-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="79f09-111">Die Anzeige der Datenbank-Nullwerte anpassen</span><span class="sxs-lookup"><span data-stu-id="79f09-111">To customize the display of null database values</span></span>  
  
-   <span data-ttu-id="79f09-112">Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="79f09-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="79f09-113">Im folgenden Codebeispiel wird mit der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> "keinen Eintrag" in allen Zellen mit Werten gleich anzuzeigende Eigenschaft <xref:System.DBNull.Value?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79f09-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="79f09-114">Aktivieren des Zeilenumbruchs in textbasierten Zellen</span><span class="sxs-lookup"><span data-stu-id="79f09-114">To enable wordwrap in text-based cells</span></span>  
  
-   <span data-ttu-id="79f09-115">Festlegen der <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> Eigenschaft eine <xref:System.Windows.Forms.DataGridViewCellStyle> in eines der <xref:System.Windows.Forms.DataGridViewTriState> Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="79f09-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="79f09-116">Im folgenden Codebeispiel wird mit der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> Eigenschaft, um den Umbruchmodus für das gesamte Steuerelement festzulegen.</span><span class="sxs-lookup"><span data-stu-id="79f09-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="79f09-117">Die Ausrichtung des Texts von DataGridView-Zellen an</span><span class="sxs-lookup"><span data-stu-id="79f09-117">To specify the text alignment of DataGridView cells</span></span>  
  
-   <span data-ttu-id="79f09-118">Festlegen der <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> Eigenschaft eine <xref:System.Windows.Forms.DataGridViewCellStyle> in eines der <xref:System.Windows.Forms.DataGridViewContentAlignment> Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="79f09-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="79f09-119">Das folgende Codebeispiel legt die Ausrichtung für eine bestimmte Spalte mit der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> -Eigenschaft der Spalte.</span><span class="sxs-lookup"><span data-stu-id="79f09-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="79f09-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79f09-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="79f09-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="79f09-121">Compiling the Code</span></span>  
 <span data-ttu-id="79f09-122">Diese Beispiele erfordern Folgendes:</span><span class="sxs-lookup"><span data-stu-id="79f09-122">These examples require:</span></span>  
  
-   <span data-ttu-id="79f09-123">Ein <xref:System.Windows.Forms.DataGridView> Steuerelement namens `dataGridView1` , enthält eine Spalte mit dem Namen `UnitPrice`, eine Spalte mit dem Namen `ShipDate`, und eine Spalte mit dem Namen `CustomerName`.</span><span class="sxs-lookup"><span data-stu-id="79f09-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
-   <span data-ttu-id="79f09-124">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79f09-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="79f09-125">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="79f09-125">Robust Programming</span></span>  
 <span data-ttu-id="79f09-126">Für maximale Skalierbarkeit freigeben <xref:System.Windows.Forms.DataGridViewCellStyle> Objekten über mehrere Zeilen, Spalten oder Zellen, die dieselben Stile, anstatt die Stileigenschaften für jedes Element einzeln zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="79f09-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="79f09-127">Weitere Informationen finden Sie unter [Best Practices zum Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="79f09-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f09-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79f09-128">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [<span data-ttu-id="79f09-129">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79f09-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="79f09-130">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79f09-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="79f09-131">Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79f09-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="79f09-132">Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79f09-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="79f09-133">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="79f09-133">Formatting Types</span></span>](../../../../docs/standard/base-types/formatting-types.md)
