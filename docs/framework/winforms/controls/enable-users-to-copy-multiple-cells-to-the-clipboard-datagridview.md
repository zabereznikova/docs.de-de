---
title: 'Vorgehensweise: Festlegen, dass mehrere Zellen aus dem DataGridView-Steuerelement in Windows Forms in die Zwischenablage kopiert werden können'
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
ms.openlocfilehash: f7b6c37db0935dae703e9641b2c2605b2ec88126
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142232"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="92977-102">Vorgehensweise: Festlegen, dass mehrere Zellen aus dem DataGridView-Steuerelement in Windows Forms in die Zwischenablage kopiert werden können</span><span class="sxs-lookup"><span data-stu-id="92977-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="92977-103">Wenn Sie das Kopieren von Zellen aktivieren, stellen Sie die Daten in Ihrem <xref:System.Windows.Forms.DataGridView>-Steuerelement problemlos für andere Anwendungen über <xref:System.Windows.Forms.Clipboard> zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="92977-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="92977-104">Die Werte der ausgewählten Zellen werden in Zeichenfolgen konvertiert und als durch Tabstopp getrennte Textwerte zur Zwischenablage hinzugefügt, damit sie in Anwendungen wie Notepad und Excel eingefügt sowie als HTML-formatierte Tabelle zum Einfügen in Anwendungen wie Word verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="92977-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="92977-105">Sie können das Kopieren von Zellen konfigurieren, sodass nur Zellwerte kopiert werden, damit der Text von Zeilen- und Spaltenüberschriften in die Zwischenablagedaten einbezogen wird. Sie können den Headertext auch nur für den Fall einbeziehen, dass Benutzer ganze Zeilen oder Spalten auswählen.</span><span class="sxs-lookup"><span data-stu-id="92977-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="92977-106">Je nach Auswahlmodus können Benutzer mehrere getrennte Gruppen von Zellen auswählen.</span><span class="sxs-lookup"><span data-stu-id="92977-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="92977-107">Wenn ein Benutzer Zellen in die Zwischenablage kopiert, werden Zeilen und Spalten ohne ausgewählte Zellen nicht kopiert.</span><span class="sxs-lookup"><span data-stu-id="92977-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="92977-108">Alle anderen Zeilen oder Spalten werden zu Zeilen und Spalten in der Tabelle der Daten, die in die Zwischenablage kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="92977-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="92977-109">Nicht ausgewählte Zellen in diesen Zeilen oder Spalten werden als leere Platzhalter in die Zwischenablage kopiert.</span><span class="sxs-lookup"><span data-stu-id="92977-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="92977-110">So aktivieren Sie das Kopieren von Zellen</span><span class="sxs-lookup"><span data-stu-id="92977-110">To enable cell copying</span></span>  
  
-   <span data-ttu-id="92977-111">Legen Sie die <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="92977-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="92977-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92977-112">Example</span></span>  
 <span data-ttu-id="92977-113">Im folgenden vollständigen Codebeispiel wird veranschaulicht, wie die Zellen in die Zwischenablage kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="92977-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="92977-114">Dieses Beispiel enthält eine Schaltfläche, die ausgewählte Zellen mithilfe der <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType>-Methode in die Zwischenablage kopiert und den Inhalt der Zwischenablage in einem Textfeld anzeigt.</span><span class="sxs-lookup"><span data-stu-id="92977-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="92977-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="92977-115">Compiling the Code</span></span>  
 <span data-ttu-id="92977-116">Dieser Code erfordert:</span><span class="sxs-lookup"><span data-stu-id="92977-116">This code requires:</span></span>  
  
-   <span data-ttu-id="92977-117">Verweise auf die Assemblys "N:System" und "N:System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="92977-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="92977-118">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="92977-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="92977-119">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="92977-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92977-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92977-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [<span data-ttu-id="92977-121">Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92977-121">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
