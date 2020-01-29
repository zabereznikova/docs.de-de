---
title: Formatieren von Daten im DataGridView-Steuerelement
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
ms.openlocfilehash: 9ee2869cf4085b5acfdf1f8c440151be506dbe3e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736790"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b2bac-102">Gewusst wie: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2bac-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b2bac-103">Die folgenden Prozeduren veranschaulichen die grundlegende Formatierung von Zellwerten mithilfe der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>-Eigenschaft eines <xref:System.Windows.Forms.DataGridView> Steuer Elements und bestimmter Spalten in einem-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b2bac-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="b2bac-104">Weitere Informationen zur erweiterten Datenformatierung finden Sie unter Gewusst [wie: Anpassen der Datenformatierung im Windows Forms DataGridView-Steuer](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="b2bac-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="b2bac-105">So formatieren Sie Currency-und Date-Werte</span><span class="sxs-lookup"><span data-stu-id="b2bac-105">To format currency and date values</span></span>  
  
- <span data-ttu-id="b2bac-106">Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="b2bac-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="b2bac-107">Im folgenden Codebeispiel wird das Format für bestimmte Spalten mithilfe der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>-Eigenschaft der Spalten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b2bac-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="b2bac-108">Werte in der Spalte `UnitPrice` werden im aktuellen Kultur abhängigen Währungs Format angezeigt, wobei negative Werte in Klammern eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="b2bac-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="b2bac-109">Werte in der Spalte `ShipDate` werden im aktuellen kulturspezifischen kurzen Datumsformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2bac-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="b2bac-110">Weitere Informationen zu <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Werten finden Sie unter [Formatieren von Typen](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="b2bac-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="b2bac-111">So passen Sie die Anzeige von NULL-Daten bankwerten an</span><span class="sxs-lookup"><span data-stu-id="b2bac-111">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="b2bac-112">Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="b2bac-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="b2bac-113">Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>-Eigenschaft verwendet, um in allen Zellen, die Werte gleich <xref:System.DBNull.Value?displayProperty=nameWithType>enthalten, den Eintrag No Entry anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2bac-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="b2bac-114">So aktivieren Sie WordWrap in textbasierten Zellen</span><span class="sxs-lookup"><span data-stu-id="b2bac-114">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="b2bac-115">Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> auf einen der <xref:System.Windows.Forms.DataGridViewTriState>-Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="b2bac-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="b2bac-116">Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>-Eigenschaft verwendet, um den Umbruch Modus für das gesamte-Steuerelement festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b2bac-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="b2bac-117">So geben Sie die Textausrichtung von DataGridView-Zellen an</span><span class="sxs-lookup"><span data-stu-id="b2bac-117">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="b2bac-118">Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> auf einen der <xref:System.Windows.Forms.DataGridViewContentAlignment>-Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="b2bac-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="b2bac-119">Im folgenden Codebeispiel wird die Ausrichtung für eine bestimmte Spalte mithilfe der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>-Eigenschaft der Spalte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b2bac-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="b2bac-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2bac-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2bac-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b2bac-121">Compiling the Code</span></span>  
 <span data-ttu-id="b2bac-122">Diese Beispiele erfordern Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b2bac-122">These examples require:</span></span>  
  
- <span data-ttu-id="b2bac-123">Ein <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem Namen `dataGridView1`, das eine Spalte mit dem Namen `UnitPrice`, eine Spalte mit dem Namen `ShipDate`und eine Spalte mit dem Namen `CustomerName`enthält.</span><span class="sxs-lookup"><span data-stu-id="b2bac-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="b2bac-124">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2bac-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b2bac-125">Robuste Programmierung</span><span class="sxs-lookup"><span data-stu-id="b2bac-125">Robust Programming</span></span>  
 <span data-ttu-id="b2bac-126">Um maximale Skalierbarkeit zu ermöglichen, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte für mehrere Zeilen, Spalten oder Zellen freigeben, die dieselben Stile verwenden, anstatt die Stileigenschaften für jedes Element separat festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b2bac-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="b2bac-127">Weitere Informationen finden Sie unter [bewährte Methoden zum Skalieren des Windows Forms DataGridView-Steuer](best-practices-for-scaling-the-windows-forms-datagridview-control.md)Elements.</span><span class="sxs-lookup"><span data-stu-id="b2bac-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bac-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2bac-128">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="b2bac-129">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2bac-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b2bac-130">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2bac-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b2bac-131">Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2bac-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b2bac-132">Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2bac-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b2bac-133">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="b2bac-133">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
