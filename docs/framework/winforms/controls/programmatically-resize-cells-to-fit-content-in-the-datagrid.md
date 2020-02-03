---
title: Programm gesteuertes Anpassen der Zellen Größe an den Inhalt im DataGridView-Steuerelement
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
ms.openlocfilehash: df3b378a8ba358fa0bfe549a7901b3d59d53f556
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742447"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8798d-102">Gewusst wie: Programmgesteuertes Anpassen der Zellengröße an den Inhalt im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8798d-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8798d-103">Sie können die <xref:System.Windows.Forms.DataGridView>-Steuerelementmethoden verwenden, um die Größen von Zeilen, Spalten und Headern zu ändern, sodass die darin enthaltenen Werte ungekürzt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8798d-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="8798d-104">Mit diesen Methoden können Sie die Größen der <xref:System.Windows.Forms.DataGridView>-Elemente zu von Ihnen gewählten Zeitpunkten ändern.</span><span class="sxs-lookup"><span data-stu-id="8798d-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="8798d-105">Alternativ können Sie das Steuerelement so konfigurieren, dass diese Elemente automatisch angepasst werden, sobald sich der Inhalt ändert.</span><span class="sxs-lookup"><span data-stu-id="8798d-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="8798d-106">Dies kann jedoch ineffizient sein, wenn Sie mit großen Datenmengen arbeiten oder wenn sich Ihre Daten häufig ändern.</span><span class="sxs-lookup"><span data-stu-id="8798d-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="8798d-107">Weitere Informationen finden Sie unter [Größen Anpassungsoptionen im Windows Forms DataGridView-Steuer](sizing-options-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="8798d-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="8798d-108">In der Regel passen Sie <xref:System.Windows.Forms.DataGridView>-Elemente nur dann programmgesteuert an ihren Inhalt an, wenn Sie neue Daten aus einer Datenquelle laden oder der Benutzer einen Wert bearbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="8798d-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="8798d-109">Dies ist nützlich, um die Leistung zu optimieren, ist aber auch nützlich, wenn Sie Ihren Benutzern ermöglichen möchten, die Größen von Zeilen und Spalten manuell mit der Maus ändern zu können.</span><span class="sxs-lookup"><span data-stu-id="8798d-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="8798d-110">Im folgenden Codebeispiel werden die Optionen veranschaulicht, die zur programmgesteuerten Größenanpassung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8798d-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8798d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8798d-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8798d-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8798d-112">Compiling the Code</span></span>  
 <span data-ttu-id="8798d-113">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8798d-113">This example requires:</span></span>  
  
- <span data-ttu-id="8798d-114">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="8798d-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8798d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8798d-115">See also</span></span>

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
- [<span data-ttu-id="8798d-116">Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8798d-116">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8798d-117">Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8798d-117">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8798d-118">Gewusst wie: Automatisches Anpassen der Zellengröße bei Änderungen des Inhalts im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8798d-118">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
