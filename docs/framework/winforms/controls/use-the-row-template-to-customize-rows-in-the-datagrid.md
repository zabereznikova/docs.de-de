---
title: 'Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 0dba318e6aa35761f4e9471fdb13b65644747b57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966494"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="280c9-102">Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="280c9-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="280c9-103">Das <xref:System.Windows.Forms.DataGridView> -Steuerelement verwendet die Zeilen Vorlage als Grundlage für alle Zeilen, die dem Steuerelement entweder über die Datenbindung hinzugefügt werden, <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> oder wenn die-Methode aufgerufen wird, ohne eine vorhandene zu verwendende Zeile anzugeben.</span><span class="sxs-lookup"><span data-stu-id="280c9-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="280c9-104">Mit der Zeilen Vorlage können Sie die Darstellung und das Verhalten von Zeilen besser steuern, <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> als die-Eigenschaft bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="280c9-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="280c9-105">Mit der Zeilen Vorlage können Sie alle <xref:System.Windows.Forms.DataGridViewRow> Eigenschaften festlegen, einschließlich. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A></span><span class="sxs-lookup"><span data-stu-id="280c9-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="280c9-106">Es gibt einige Situationen, in denen Sie die Zeilen Vorlage verwenden müssen, um einen bestimmten Effekt zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="280c9-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="280c9-107">Beispielsweise können Informationen zur Zeilenhöhe nicht in einem <xref:System.Windows.Forms.DataGridViewCellStyle>gespeichert werden. Daher müssen Sie eine Zeilen Vorlage verwenden, um die von allen Zeilen verwendete Standardhöhe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="280c9-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="280c9-108">Die Zeilen Vorlage ist auch nützlich, wenn Sie Ihre eigenen Klassen erstellen, <xref:System.Windows.Forms.DataGridViewRow> die von abgeleitet sind, und Sie möchten, dass der benutzerdefinierte Typ verwendet wird, wenn dem Steuerelement neue Zeilen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="280c9-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="280c9-109">Die Zeilen Vorlage wird nur verwendet, wenn Zeilen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="280c9-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="280c9-110">Vorhandene Zeilen können nicht durch Ändern der Zeilen Vorlage geändert werden.</span><span class="sxs-lookup"><span data-stu-id="280c9-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="280c9-111">So verwenden Sie die Zeilen Vorlage</span><span class="sxs-lookup"><span data-stu-id="280c9-111">To use the row template</span></span>  
  
- <span data-ttu-id="280c9-112">Legen Sie Eigenschaften für das von der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> -Eigenschaft abgerufene Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="280c9-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="280c9-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="280c9-113">Compiling the Code</span></span>  
 <span data-ttu-id="280c9-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="280c9-114">This example requires:</span></span>  
  
- <span data-ttu-id="280c9-115">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="280c9-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="280c9-116">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="280c9-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="280c9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="280c9-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="280c9-118">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="280c9-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="280c9-119">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="280c9-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
