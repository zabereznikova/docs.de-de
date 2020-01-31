---
title: Anzeigen von Bildern in Zellen des DataGridView-Steuer Elements
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
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740284"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="af2ff-102">Gewusst wie: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af2ff-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="af2ff-103">Ein Bild oder eine Grafik ist einer der Werte, die in einer Daten Zeile angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="af2ff-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="af2ff-104">Häufig haben diese Grafiken das Foto eines Mitarbeiters oder ein Firmenlogo.</span><span class="sxs-lookup"><span data-stu-id="af2ff-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="af2ff-105">Das Einschließen von Bildern ist einfach, wenn Sie Daten innerhalb des <xref:System.Windows.Forms.DataGridView> Steuer Elements anzeigen.</span><span class="sxs-lookup"><span data-stu-id="af2ff-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="af2ff-106">Das <xref:System.Windows.Forms.DataGridView>-Steuerelement behandelt alle Bildformate, die von der <xref:System.Drawing.Image>-Klasse unterstützt werden, und das von einigen Datenbanken verwendete OLE-Bildformat.</span><span class="sxs-lookup"><span data-stu-id="af2ff-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="af2ff-107">Wenn die Datenquelle des <xref:System.Windows.Forms.DataGridView> Steuer Elements über eine Spalte mit Bildern verfügt, werden diese automatisch vom <xref:System.Windows.Forms.DataGridView>-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af2ff-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="af2ff-108">Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein Symbol aus einer eingebetteten Ressource extrahieren und in eine Bitmap konvertieren, um Sie in jeder Zelle einer Bild Spalte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="af2ff-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="af2ff-109">Ein weiteres Beispiel, das Text Zellwerte durch entsprechende Bilder ersetzt, finden Sie unter Gewusst [wie: Anpassen der Datenformatierung im Windows Forms DataGridView-Steuer](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="af2ff-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af2ff-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af2ff-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="af2ff-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="af2ff-111">Compiling the Code</span></span>  
 <span data-ttu-id="af2ff-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="af2ff-112">This example requires:</span></span>  
  
- <span data-ttu-id="af2ff-113">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="af2ff-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="af2ff-114">Eine eingebettete Symbol Ressource mit dem Namen `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="af2ff-114">An embedded icon resource named `tree.ico`.</span></span>  
  
- <span data-ttu-id="af2ff-115">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af2ff-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af2ff-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af2ff-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="af2ff-117">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af2ff-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="af2ff-118">Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af2ff-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
