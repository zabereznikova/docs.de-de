---
title: 'Vorgehensweise: Festlegen von abwechselnden Zeilenstilen für das DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
ms.openlocfilehash: 06b93a756b351213a87e1f52bc691aaa27558ac4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078589"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="f8ddc-102">Vorgehensweise: Festlegen von abwechselnden Zeilenstilen für das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8ddc-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f8ddc-103">Tabellendaten werden oft in einem Ledger-ähnlichen Format präsentiert, bei dem die einzelnen Zeilen abwechselnde Hintergrundfarben haben.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-103">Tabular data is often presented to users in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="f8ddc-104">Dieses Format erleichtert es dem Benutzer, zu erkennen, welche Zellen sich in jeder Zeile befinden, insbesondere bei breiten Tabellen mit vielen Spalten.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="f8ddc-105">Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie vollständige Stilinformationen für abwechselnde Zeilen angeben.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="f8ddc-106">Auf diese Weise können Sie Stileigenschaften wie Vordergrundfarbe und Schriftart zusätzlich zur Hintergrundfarbe verwenden, um abwechselnde Zeilen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-106">This enables you use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span>  
  
 <span data-ttu-id="f8ddc-107">Visual Studio bietet Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="f8ddc-108">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-DataGridView-Steuerelement mithilfe des Designers](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="f8ddc-108">Also see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-set-alternating-row-styles-programmatically"></a><span data-ttu-id="f8ddc-109">So legen Sie abwechselnde Zeilenstile programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="f8ddc-109">To set alternating row styles programmatically</span></span>  
  
-   <span data-ttu-id="f8ddc-110">Legen Sie die Eigenschaften der <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte fest, die von der <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>- und der <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>-Eigenschaft der <xref:System.Windows.Forms.DataGridView> zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-110">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> objects returned by the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties of the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  <span data-ttu-id="f8ddc-111">Die Stile, die über die <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>- und die <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>-Eigenschaft angegeben sind, überschreiben die Stile, die auf Spalten- und <xref:System.Windows.Forms.DataGridView>-Ebene festgelegt sind, werden jedoch durch die Stile überschrieben, die auf der einzelnen Zeilen- und Zellenebene festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-111">The styles specified using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties override the styles specified on the column and <xref:System.Windows.Forms.DataGridView> level, but are overridden by the styles set on the individual row and cell level.</span></span> <span data-ttu-id="f8ddc-112">Weitere Informationen finden Sie unter [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f8ddc-112">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8ddc-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f8ddc-113">Compiling the Code</span></span>  
 <span data-ttu-id="f8ddc-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f8ddc-114">This example requires:</span></span>  
  
-   <span data-ttu-id="f8ddc-115">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="f8ddc-116">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f8ddc-117">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="f8ddc-117">Robust Programming</span></span>  
 <span data-ttu-id="f8ddc-118">Um maximale Skalierbarkeit zu erreichen, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte für mehrere Zeilen, Spalten oder Zellen, in denen dieselben Stile verwendet werden, gemeinsam verwenden, anstatt die Stileigenschaften für jedes einzelne Element festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f8ddc-118">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="f8ddc-119">Weitere Informationen finden Sie unter [Best Practices für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f8ddc-119">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ddc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8ddc-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="f8ddc-121">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8ddc-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f8ddc-122">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8ddc-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f8ddc-123">Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8ddc-123">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f8ddc-124">Vorgehensweise: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8ddc-124">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
