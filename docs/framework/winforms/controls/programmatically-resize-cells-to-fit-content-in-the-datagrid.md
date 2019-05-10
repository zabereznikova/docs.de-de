---
title: 'Vorgehensweise: Programmgesteuertes Anpassen der Zellengröße an den Inhalt im DataGridView-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: 8c95d60ba36275ec4d0e263f97bc28a559c1f38e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64654459"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3100e-102">Vorgehensweise: Programmgesteuertes Anpassen der Zellengröße an den Inhalt im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3100e-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3100e-103">Sie können die <xref:System.Windows.Forms.DataGridView>-Steuerelementmethoden verwenden, um die Größen von Zeilen, Spalten und Headern zu ändern, sodass die darin enthaltenen Werte ungekürzt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3100e-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="3100e-104">Mit diesen Methoden können Sie die Größen der <xref:System.Windows.Forms.DataGridView>-Elemente zu von Ihnen gewählten Zeitpunkten ändern.</span><span class="sxs-lookup"><span data-stu-id="3100e-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="3100e-105">Alternativ können Sie das Steuerelement so konfigurieren, dass diese Elemente automatisch angepasst werden, sobald sich der Inhalt ändert.</span><span class="sxs-lookup"><span data-stu-id="3100e-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="3100e-106">Dies kann jedoch ineffizient sein, wenn Sie mit großen Datenmengen arbeiten oder wenn sich Ihre Daten häufig ändern.</span><span class="sxs-lookup"><span data-stu-id="3100e-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="3100e-107">Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="3100e-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="3100e-108">In der Regel passen Sie <xref:System.Windows.Forms.DataGridView>-Elemente nur dann programmgesteuert an ihren Inhalt an, wenn Sie neue Daten aus einer Datenquelle laden oder der Benutzer einen Wert bearbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="3100e-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="3100e-109">Dies ist nützlich, um die Leistung zu optimieren, ist aber auch nützlich, wenn Sie Ihren Benutzern ermöglichen möchten, die Größen von Zeilen und Spalten manuell mit der Maus ändern zu können.</span><span class="sxs-lookup"><span data-stu-id="3100e-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="3100e-110">Im folgenden Codebeispiel werden die Optionen veranschaulicht, die zur programmgesteuerten Größenanpassung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3100e-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3100e-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3100e-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3100e-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3100e-112">Compiling the Code</span></span>  
 <span data-ttu-id="3100e-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3100e-113">This example requires:</span></span>  
  
- <span data-ttu-id="3100e-114">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="3100e-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="3100e-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3100e-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="3100e-116">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="3100e-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3100e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3100e-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="3100e-118">Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3100e-118">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3100e-119">Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3100e-119">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3100e-120">Vorgehensweise: Größe automatisch Zellen aus, wenn Inhalt geändert wird, in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3100e-120">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
