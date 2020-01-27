---
title: Benutzern das Kopieren mehrerer Zellen in die Zwischenablage aus dem DataGridView-Steuerelement ermöglichen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: 2bb74a1f0c59b28ab496ce9c89c1c1b5f9d8147b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745786"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="c30dc-102">Gewusst wie: Festlegen, dass mehrere Zellen aus dem DataGridView-Steuerelement in Windows Forms in die Zwischenablage kopiert werden können</span><span class="sxs-lookup"><span data-stu-id="c30dc-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c30dc-103">Wenn Sie das Kopieren von Zellen aktivieren, stellen Sie die Daten in Ihrem <xref:System.Windows.Forms.DataGridView>-Steuerelement problemlos für andere Anwendungen über <xref:System.Windows.Forms.Clipboard> zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c30dc-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="c30dc-104">Die Werte der ausgewählten Zellen werden in Zeichenfolgen konvertiert und als durch Tabstopp getrennte Textwerte zur Zwischenablage hinzugefügt, damit sie in Anwendungen wie Notepad und Excel eingefügt sowie als HTML-formatierte Tabelle zum Einfügen in Anwendungen wie Word verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c30dc-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="c30dc-105">Sie können das Kopieren von Zellen konfigurieren, sodass nur Zellwerte kopiert werden, damit der Text von Zeilen- und Spaltenüberschriften in die Zwischenablagedaten einbezogen wird. Sie können den Headertext auch nur für den Fall einbeziehen, dass Benutzer ganze Zeilen oder Spalten auswählen.</span><span class="sxs-lookup"><span data-stu-id="c30dc-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="c30dc-106">Je nach Auswahlmodus können Benutzer mehrere getrennte Gruppen von Zellen auswählen.</span><span class="sxs-lookup"><span data-stu-id="c30dc-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="c30dc-107">Wenn ein Benutzer Zellen in die Zwischenablage kopiert, werden Zeilen und Spalten ohne ausgewählte Zellen nicht kopiert.</span><span class="sxs-lookup"><span data-stu-id="c30dc-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="c30dc-108">Alle anderen Zeilen oder Spalten werden zu Zeilen und Spalten in der Tabelle der Daten, die in die Zwischenablage kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c30dc-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="c30dc-109">Nicht ausgewählte Zellen in diesen Zeilen oder Spalten werden als leere Platzhalter in die Zwischenablage kopiert.</span><span class="sxs-lookup"><span data-stu-id="c30dc-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="c30dc-110">So aktivieren Sie das Kopieren von Zellen</span><span class="sxs-lookup"><span data-stu-id="c30dc-110">To enable cell copying</span></span>  
  
- <span data-ttu-id="c30dc-111">Legen Sie die <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c30dc-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="c30dc-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c30dc-112">Example</span></span>  
 <span data-ttu-id="c30dc-113">Im folgenden vollständigen Codebeispiel wird veranschaulicht, wie die Zellen in die Zwischenablage kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="c30dc-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="c30dc-114">Dieses Beispiel enthält eine Schaltfläche, die ausgewählte Zellen mithilfe der <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType>-Methode in die Zwischenablage kopiert und den Inhalt der Zwischenablage in einem Textfeld anzeigt.</span><span class="sxs-lookup"><span data-stu-id="c30dc-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c30dc-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c30dc-115">Compiling the Code</span></span>  
 <span data-ttu-id="c30dc-116">Dieser Code erfordert:</span><span class="sxs-lookup"><span data-stu-id="c30dc-116">This code requires:</span></span>  
  
- <span data-ttu-id="c30dc-117">Verweise auf die Assemblys "N:System" und "N:System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="c30dc-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30dc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c30dc-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [<span data-ttu-id="c30dc-119">Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c30dc-119">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
