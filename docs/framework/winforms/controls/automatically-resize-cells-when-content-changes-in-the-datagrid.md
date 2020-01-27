---
title: Zellen automatisch ändern, wenn sich der Inhalt im DataGridView-Steuerelement ändert
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: 86e3bce993aa06546e301c6d7a7e03a31013c337
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732068"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="31621-102">Gewusst wie: Automatisches Anpassen der Zellengröße bei Änderungen des Inhalts im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31621-102">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="31621-103">Sie können das <xref:System.Windows.Forms.DataGridView> -Steuerelement für das automatische Ändern der Größe der Zeilen, Spalten und Header konfigurieren, wenn sich die Inhalte ändern, damit die Zellen immer groß genug sind, um die Werte anzuzeigen, ohne dass diese abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="31621-103">You can configure the <xref:System.Windows.Forms.DataGridView> control to resize its rows, columns, and headers automatically whenever content changes, so that cells are always large enough to display their values without clipping.</span></span>  
  
 <span data-ttu-id="31621-104">Sie können auf verschiedene Weise einschränken, welche Zellen verwendet werden, um die neue Größe zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="31621-104">You have many options to restrict which cells are used to determine the new sizes.</span></span> <span data-ttu-id="31621-105">Beispielsweise können Sie das Steuerelement so konfigurieren, dass die Breite der Spalten automatisch nur anhand der Werte in den aktuell angezeigten Zeilen angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="31621-105">For example, you can configure the control to automatically resize the width of its columns based only on the values in rows that are currently displayed.</span></span> <span data-ttu-id="31621-106">Mit dieser Option können Sie Ineffizienz bei der Arbeit mit einer großen Anzahl von Zeilen vermeiden. In diesem Fall können Sie jedoch wahlweise auch Größenänderungsmethoden wie z. B. <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> verwenden, um die Größe anzupassen.</span><span class="sxs-lookup"><span data-stu-id="31621-106">With this, you can avoid inefficiency when working with large numbers of rows, although in this case, you might want to use sizing methods such as <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> to adjust sizes at times of your choosing.</span></span>  
  
 <span data-ttu-id="31621-107">Weitere Informationen zur automatischen Größenänderung finden Sie unter [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="31621-107">For more information about automatic resizing, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="31621-108">Im folgenden Codebeispiel werden die Optionen veranschaulicht, die für die automatische Größenänderung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="31621-108">The following code example demonstrates the options available for automatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31621-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31621-109">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31621-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="31621-110">Compiling the Code</span></span>  
 <span data-ttu-id="31621-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="31621-111">This example requires:</span></span>  
  
- <span data-ttu-id="31621-112">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="31621-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31621-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31621-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="31621-114">Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31621-114">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="31621-115">Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31621-115">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="31621-116">Gewusst wie: Programmgesteuertes Anpassen der Zellengröße an den Inhalt im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31621-116">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
