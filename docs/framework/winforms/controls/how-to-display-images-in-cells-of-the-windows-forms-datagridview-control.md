---
title: 'Vorgehensweise: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: 90aaff419ecc2c890a8b3802f3aaf12092febb73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082996"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="f10da-102">Vorgehensweise: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f10da-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f10da-103">Ein Bild oder eine Grafik ist einer der Werte, die in eine Zeile mit Daten angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="f10da-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="f10da-104">In vielen Fällen haben diese Grafiken der Form Foto eines Mitarbeiters oder einem Logo des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="f10da-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="f10da-105">Integrieren von Bildern ist einfach, wenn Sie anzeigen, dass die Daten in die <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f10da-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f10da-106">Die <xref:System.Windows.Forms.DataGridView> -Steuerelement behandelt jedes Bildformat, das unterstützt durch die <xref:System.Drawing.Image> -Klasse als auch das OLE-Bild, das von einigen Datenbanken verwendet.</span><span class="sxs-lookup"><span data-stu-id="f10da-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="f10da-107">Wenn die <xref:System.Windows.Forms.DataGridView> Datenquelle des Steuerelements verfügt über eine Spalte mit Bildern, werden sie automatisch vom angezeigt der <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f10da-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="f10da-108">Im folgenden Codebeispiel wird veranschaulicht, wie ein Symbol aus einer eingebetteten Ressource extrahiert, und konvertieren Sie ihn in eine Bitmap für die Anzeige in jeder Zelle der Image-Spalte.</span><span class="sxs-lookup"><span data-stu-id="f10da-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="f10da-109">Ein weiteres Beispiel, das durch entsprechende Bilder Zellenwerte ersetzt werden, finden Sie unter [Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f10da-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f10da-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f10da-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f10da-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f10da-111">Compiling the Code</span></span>  
 <span data-ttu-id="f10da-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f10da-112">This example requires:</span></span>  
  
-   <span data-ttu-id="f10da-113">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="f10da-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="f10da-114">Eine eingebettete Symbolressource mit dem Namen `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="f10da-114">An embedded icon resource named `tree.ico`.</span></span>  
  
-   <span data-ttu-id="f10da-115">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f10da-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10da-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f10da-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="f10da-117">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f10da-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="f10da-118">Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f10da-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
