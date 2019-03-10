---
title: 'Vorgehensweise: Größe automatisch Zellen aus, wenn Inhalt geändert wird, in das DataGridView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 15a3538dddfb1c36aa276bdf2fbe53cb8597992b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710653"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9d4a8-102">Vorgehensweise: Größe automatisch Zellen aus, wenn Inhalt geändert wird, in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9d4a8-102">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9d4a8-103">Sie können das <xref:System.Windows.Forms.DataGridView> -Steuerelement für das automatische Ändern der Größe der Zeilen, Spalten und Header konfigurieren, wenn sich die Inhalte ändern, damit die Zellen immer groß genug sind, um die Werte anzuzeigen, ohne dass diese abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="9d4a8-103">You can configure the <xref:System.Windows.Forms.DataGridView> control to resize its rows, columns, and headers automatically whenever content changes, so that cells are always large enough to display their values without clipping.</span></span>  
  
 <span data-ttu-id="9d4a8-104">Sie können auf verschiedene Weise einschränken, welche Zellen verwendet werden, um die neue Größe zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="9d4a8-104">You have many options to restrict which cells are used to determine the new sizes.</span></span> <span data-ttu-id="9d4a8-105">Beispielsweise können Sie das Steuerelement so konfigurieren, dass die Breite der Spalten automatisch nur anhand der Werte in den aktuell angezeigten Zeilen angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="9d4a8-105">For example, you can configure the control to automatically resize the width of its columns based only on the values in rows that are currently displayed.</span></span> <span data-ttu-id="9d4a8-106">Mit dieser Option können Sie Ineffizienz bei der Arbeit mit einer großen Anzahl von Zeilen vermeiden. In diesem Fall können Sie jedoch wahlweise auch Größenänderungsmethoden wie z. B. <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> verwenden, um die Größe anzupassen.</span><span class="sxs-lookup"><span data-stu-id="9d4a8-106">With this, you can avoid inefficiency when working with large numbers of rows, although in this case, you might want to use sizing methods such as <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> to adjust sizes at times of your choosing.</span></span>  
  
 <span data-ttu-id="9d4a8-107">Weitere Informationen zur automatischen Größenänderung finden Sie unter [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="9d4a8-107">For more information about automatic resizing, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="9d4a8-108">Im folgenden Codebeispiel werden die Optionen veranschaulicht, die für die automatische Größenänderung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9d4a8-108">The following code example demonstrates the options available for automatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d4a8-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d4a8-109">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d4a8-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9d4a8-110">Compiling the Code</span></span>  
 <span data-ttu-id="9d4a8-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9d4a8-111">This example requires:</span></span>  
  
-   <span data-ttu-id="9d4a8-112">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="9d4a8-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="9d4a8-113">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9d4a8-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9d4a8-114">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="9d4a8-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d4a8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d4a8-115">See also</span></span>
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
- [<span data-ttu-id="9d4a8-116">Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9d4a8-116">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9d4a8-117">Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9d4a8-117">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9d4a8-118">Vorgehensweise: Programmgesteuertes Ändern der Größe Zellen an Inhalt im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9d4a8-118">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
