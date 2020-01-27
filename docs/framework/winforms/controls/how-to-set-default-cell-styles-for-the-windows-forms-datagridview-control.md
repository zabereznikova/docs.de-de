---
title: Festlegen von Standardzellen Formaten für das DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: 6b2d7de671e48ae8f55987c262e15717138b3fb4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744869"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="a35dd-102">Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a35dd-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a35dd-103">Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie Standardzellenstile für das gesamte Steuerelement und für bestimmte Spalten und Zeilen angeben.</span><span class="sxs-lookup"><span data-stu-id="a35dd-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="a35dd-104">Diese Standardeinstellungen werden von der Steuerelementebene bis herunter auf die Spaltenebene, dann auf die Zeilenebene und anschließend auf die Zellenebene gefiltert.</span><span class="sxs-lookup"><span data-stu-id="a35dd-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="a35dd-105">Wenn eine bestimmte Eigenschaft <xref:System.Windows.Forms.DataGridViewCellStyle> nicht auf Zellenebene festgelegt ist, wird die standardmäßige Eigenschafteneinstellung auf Zeilenebene verwendet.</span><span class="sxs-lookup"><span data-stu-id="a35dd-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="a35dd-106">Wenn die Eigenschaft auf Zeilenebene ebenfalls nicht festgelegt ist, wird die Standardspalteneinstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a35dd-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="a35dd-107">Wenn die Eigenschaft schließlich auf Spaltenebene ebenfalls nicht festgelegt ist, wird die <xref:System.Windows.Forms.DataGridView>-Standardeinstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a35dd-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="a35dd-108">Mit dieser Einstellung können Sie vermeiden, die Eigenschafteneinstellungen auf mehreren Ebenen duplizieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="a35dd-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="a35dd-109">Geben Sie einfach auf jeder Ebene die Stile an, die sich von den darüber liegenden Ebenen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="a35dd-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="a35dd-110">Weitere Informationen finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="a35dd-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="a35dd-111">Visual Studio bietet umfassende Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="a35dd-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="a35dd-112">Siehe auch Gewusst [wie: Festlegen von Standardzellen Stilen und Datenformaten für das Windows Forms DataGridView-Steuerelement mithilfe des Designers](default-cell-styles-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="a35dd-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="a35dd-113">Die legen Sie Standardzellenstile programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="a35dd-113">To set the default cell styles programmatically</span></span>  
  
1. <span data-ttu-id="a35dd-114">Legen Sie die Eigenschaften des <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekts fest, das über die Eigenschaft <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a35dd-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2. <span data-ttu-id="a35dd-115">Erstellen und initialisieren Sie neue <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte für die Verwendung durch mehreren Zeilen und Spalten.</span><span class="sxs-lookup"><span data-stu-id="a35dd-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3. <span data-ttu-id="a35dd-116">Legen Sie die Eigenschaft `DefaultCellStyle` bestimmter Zeilen und Spalten fest.</span><span class="sxs-lookup"><span data-stu-id="a35dd-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="a35dd-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a35dd-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a35dd-118">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a35dd-118">Compiling the Code</span></span>  
 <span data-ttu-id="a35dd-119">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a35dd-119">This example requires:</span></span>  
  
- <span data-ttu-id="a35dd-120">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="a35dd-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="a35dd-121">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a35dd-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a35dd-122">Robuste Programmierung</span><span class="sxs-lookup"><span data-stu-id="a35dd-122">Robust Programming</span></span>  
 <span data-ttu-id="a35dd-123">Um maximale Skalierbarkeit zu erreichen, wenn Sie mit sehr großen Datenmengen arbeiten, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte für mehrere Zeilen, Spalten oder Zellen freigeben, die dieselben Stile verwenden, anstatt die Stileigenschaften für einzelne Elemente separat festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a35dd-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="a35dd-124">Darüber hinaus sollten Sie freigegebene Zeilen erstellen und auf diese zugreifen, indem Sie die Eigenschaft <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="a35dd-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a35dd-125">Weitere Informationen finden Sie unter [bewährte Methoden zum Skalieren des Windows Forms DataGridView-Steuer](best-practices-for-scaling-the-windows-forms-datagridview-control.md)Elements.</span><span class="sxs-lookup"><span data-stu-id="a35dd-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a35dd-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a35dd-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a35dd-127">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a35dd-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a35dd-128">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a35dd-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a35dd-129">Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a35dd-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a35dd-130">Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a35dd-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
