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
ms.openlocfilehash: cb3a826262a49a8653e3a344bd126d434f2522dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073038"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="cc91b-102">Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc91b-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cc91b-103">Die <xref:System.Windows.Forms.DataGridView> Steuerelement verwendet die Zeilenvorlage als Grundlage für alle Zeilen, die es dem Steuerelement hinzugefügt, über die Datenbindung oder beim Aufrufen der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> Methode ohne Angabe einer vorhandenen Zeile verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc91b-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="cc91b-104">Die Zeilenvorlage ermöglicht Ihnen größere Kontrolle über das Erscheinungsbild und Verhalten von Zeilen als die <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="cc91b-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="cc91b-105">Mit der Zeilenvorlage können Sie alle festlegen <xref:System.Windows.Forms.DataGridViewRow> Eigenschaften, einschließlich <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc91b-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="cc91b-106">Es gibt einige Situationen, in dem Sie die Zeilenvorlage verwenden müssen, um einen bestimmten Effekt zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="cc91b-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="cc91b-107">Z. B. Informationen über die Zeilenhöhe in gespeichert werden kann keiner <xref:System.Windows.Forms.DataGridViewCellStyle>, Sie eine Zeilenvorlage verwenden müssen, um die Standardhöhe aller Zeilen ein, zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cc91b-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="cc91b-108">Die Zeilenvorlage ist auch nützlich, bei der Erstellung eigener Klassen abgeleitet <xref:System.Windows.Forms.DataGridViewRow> und den benutzerdefinierten Typ verwendet, wenn dem Steuerelement neue Zeilen hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc91b-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc91b-109">Die Zeilenvorlage wird verwendet, nur, wenn Zeilen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cc91b-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="cc91b-110">Sie können keine vorhandene Zeilen ändern, durch Ändern der Zeilenvorlage.</span><span class="sxs-lookup"><span data-stu-id="cc91b-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="cc91b-111">Verwenden die Zeilenvorlage</span><span class="sxs-lookup"><span data-stu-id="cc91b-111">To use the row template</span></span>  
  
-   <span data-ttu-id="cc91b-112">Legen Sie Eigenschaften für das Objekt abgerufen, die von der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cc91b-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cc91b-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="cc91b-113">Compiling the Code</span></span>  
 <span data-ttu-id="cc91b-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc91b-114">This example requires:</span></span>  
  
-   <span data-ttu-id="cc91b-115">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="cc91b-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="cc91b-116">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cc91b-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc91b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc91b-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="cc91b-118">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc91b-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="cc91b-119">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc91b-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
