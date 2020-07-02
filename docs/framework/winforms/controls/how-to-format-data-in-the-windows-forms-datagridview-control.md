---
title: Formatieren von Daten im DataGridView-Steuerelement
description: Erfahren Sie, wie Sie Zellwerte mithilfe der DefaultCellStyle-Eigenschaft eines Windows Forms DataGridView-Steuer Elements und bestimmter Spalten in einem-Steuerelement formatieren.
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
ms.openlocfilehash: d6105c1d1120876f854332e7a10106cc1caf6276
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622808"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="19cbb-103">Vorgehensweise: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19cbb-103">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="19cbb-104">Die folgenden Prozeduren veranschaulichen die grundlegende Formatierung von Zellwerten mithilfe der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> -Eigenschaft eines <xref:System.Windows.Forms.DataGridView> -Steuer Elements und bestimmter Spalten in einem-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="19cbb-104">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="19cbb-105">Weitere Informationen zur erweiterten Datenformatierung finden Sie unter Gewusst [wie: Anpassen der Datenformatierung im Windows Forms DataGridView-Steuer](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="19cbb-105">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="19cbb-106">So formatieren Sie Currency-und Date-Werte</span><span class="sxs-lookup"><span data-stu-id="19cbb-106">To format currency and date values</span></span>  
  
- <span data-ttu-id="19cbb-107">Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="19cbb-107">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="19cbb-108">Im folgenden Codebeispiel wird das Format für bestimmte Spalten mithilfe der- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Eigenschaft der-Spalten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="19cbb-108">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="19cbb-109">Werte in der `UnitPrice` Spalte werden im aktuellen Kultur abhängigen Währungs Format angezeigt, wobei negative Werte in Klammern eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="19cbb-109">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="19cbb-110">Werte in der `ShipDate` Spalte werden im aktuellen kulturspezifischen kurzen Datumsformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="19cbb-110">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="19cbb-111">Weitere Informationen zu- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Werten finden Sie unter [Formatieren von Typen](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="19cbb-111">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="19cbb-112">So passen Sie die Anzeige von NULL-Daten bankwerten an</span><span class="sxs-lookup"><span data-stu-id="19cbb-112">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="19cbb-113">Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="19cbb-113">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="19cbb-114">Im folgenden Codebeispiel wird die- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> Eigenschaft verwendet, um in allen Zellen mit Werten, die gleich sind, "kein Eintrag" anzuzeigen <xref:System.DBNull.Value?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="19cbb-114">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="19cbb-115">So aktivieren Sie WordWrap in textbasierten Zellen</span><span class="sxs-lookup"><span data-stu-id="19cbb-115">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="19cbb-116">Legen Sie die- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> auf einen der- <xref:System.Windows.Forms.DataGridViewTriState> Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="19cbb-116">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="19cbb-117">Im folgenden Codebeispiel wird die- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> Eigenschaft verwendet, um den Umbruch Modus für das gesamte-Steuerelement festzulegen.</span><span class="sxs-lookup"><span data-stu-id="19cbb-117">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="19cbb-118">So geben Sie die Textausrichtung von DataGridView-Zellen an</span><span class="sxs-lookup"><span data-stu-id="19cbb-118">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="19cbb-119">Legen Sie die- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> auf einen der- <xref:System.Windows.Forms.DataGridViewContentAlignment> Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="19cbb-119">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="19cbb-120">Im folgenden Codebeispiel wird die Ausrichtung für eine bestimmte Spalte mithilfe der- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Eigenschaft der-Spalte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="19cbb-120">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="19cbb-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19cbb-121">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="19cbb-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="19cbb-122">Compiling the Code</span></span>  
 <span data-ttu-id="19cbb-123">Voraussetzungen für diese Beispiele sind:</span><span class="sxs-lookup"><span data-stu-id="19cbb-123">These examples require:</span></span>  
  
- <span data-ttu-id="19cbb-124">Ein Steuerelement mit dem <xref:System.Windows.Forms.DataGridView> Namen, `dataGridView1` das eine Spalte mit dem Namen, eine Spalte mit dem Namen `UnitPrice` `ShipDate` und eine Spalte namens enthält `CustomerName` .</span><span class="sxs-lookup"><span data-stu-id="19cbb-124">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="19cbb-125">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="19cbb-125">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="19cbb-126">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="19cbb-126">Robust Programming</span></span>  
 <span data-ttu-id="19cbb-127">Um maximale Skalierbarkeit zu ermöglichen, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte für mehrere Zeilen, Spalten oder Zellen freigeben, die dieselben Stile verwenden, anstatt die Stileigenschaften für jedes Element separat festzulegen.</span><span class="sxs-lookup"><span data-stu-id="19cbb-127">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="19cbb-128">Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="19cbb-128">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19cbb-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19cbb-129">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="19cbb-130">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19cbb-130">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="19cbb-131">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19cbb-131">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="19cbb-132">Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19cbb-132">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="19cbb-133">Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19cbb-133">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="19cbb-134">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="19cbb-134">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
