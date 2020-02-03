---
title: Anpassen der Datenformatierung im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
ms.openlocfilehash: 6bc1a65b876df842df322db165dc08fcc0c931dc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746777"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2ca91-102">Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ca91-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2ca91-103">Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>-Ereignis implementieren, durch den geändert wird, wie Zellen in Abhängigkeit von ihren Spalten und Werten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ca91-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="2ca91-104">Zellen in der Spalte `Balance`, die negative Zahlen enthalten, erhalten einen roten Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="2ca91-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="2ca91-105">Sie können diese Zellen auch als Währungszellen formatieren, sodass negative Werte in Klammern angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ca91-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="2ca91-106">Weitere Informationen finden Sie unter [Vorgehensweise: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="2ca91-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="2ca91-107">Zellen in der Spalte `Priority` zeigen Bilder anstelle entsprechender Textzellenwerte an.</span><span class="sxs-lookup"><span data-stu-id="2ca91-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="2ca91-108">Die <xref:System.Windows.Forms.ConvertEventArgs.Value%2A>-Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>-Instanz wird verwendet, um sowohl den Textzellenwert abzurufen als auch den entsprechenden Bildanzeigewert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2ca91-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ca91-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ca91-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ca91-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2ca91-110">Compiling the Code</span></span>  
 <span data-ttu-id="2ca91-111">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2ca91-111">This example requires:</span></span>  
  
- <span data-ttu-id="2ca91-112">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="2ca91-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="2ca91-113"><xref:System.Drawing.Bitmap>-Bilder mit den Namen `highPri.bmp`, `mediumPri.bmp` und `lowPri.bmp`, die sich im selben Verzeichnis befinden wie die ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="2ca91-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca91-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ca91-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="2ca91-115">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ca91-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2ca91-116">Vorgehensweise: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ca91-116">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2ca91-117">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ca91-117">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2ca91-118">Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ca91-118">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
