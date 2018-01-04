---
title: 'Gewusst wie: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms'
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
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56c8558f34c895567c3eebfbb5a89612c4b56224
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="890b8-102">Gewusst wie: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="890b8-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="890b8-103">Ein Bild oder eine Grafik ist einer der Werte, die in eine Zeile mit Daten angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="890b8-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="890b8-104">In vielen Fällen sind diese Grafiken Foto eines Mitarbeiters oder ein Unternehmenslogo.</span><span class="sxs-lookup"><span data-stu-id="890b8-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="890b8-105">Integrieren von Bildern ist einfach, wenn Sie anzeigen, dass die Daten innerhalb der <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="890b8-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="890b8-106">Die <xref:System.Windows.Forms.DataGridView> Steuerelement behandelt systemintern alle Bildformat von unterstützt die <xref:System.Drawing.Image> Klasse als auch das OLE-Bild, das von einigen Datenbanken verwendet.</span><span class="sxs-lookup"><span data-stu-id="890b8-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="890b8-107">Wenn die <xref:System.Windows.Forms.DataGridView> Datenquelle des Steuerelements besitzt eine Spalte vom Bildern, werden sie automatisch vom angezeigt werden die <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="890b8-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="890b8-108">Im folgenden Codebeispiel wird veranschaulicht, wie ein Symbol aus einer eingebetteten Ressource extrahiert und konvertieren Sie ihn in eine Bitmap für die Anzeige in jeder Zelle der Image-Spalte.</span><span class="sxs-lookup"><span data-stu-id="890b8-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="890b8-109">Ein weiteres Beispiel, die Zellenwerte durch entsprechende Bilder ersetzt werden, finden Sie unter [wie: Anpassen der Datenformatierung im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="890b8-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="890b8-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="890b8-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="890b8-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="890b8-111">Compiling the Code</span></span>  
 <span data-ttu-id="890b8-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="890b8-112">This example requires:</span></span>  
  
-   <span data-ttu-id="890b8-113">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="890b8-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="890b8-114">Eine eingebettete Symbolressource mit dem Namen `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="890b8-114">An embedded icon resource named `tree.ico`.</span></span>  
  
-   <span data-ttu-id="890b8-115">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="890b8-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890b8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="890b8-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="890b8-117">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="890b8-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="890b8-118">Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="890b8-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
