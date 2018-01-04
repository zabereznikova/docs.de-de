---
title: 'Gewusst wie: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4898ed7ddff6ca1800ba9380707ad989cbec1125
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8bd75-102">Gewusst wie: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bd75-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8bd75-103">Die <xref:System.Windows.Forms.DataGridView> Steuerelement verwendet die Zeilenvorlage als Grundlage für alle Zeilen, die an das Steuerelement hinzufügt, über die Datenbindung oder beim Aufrufen der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> -Methode ohne Angabe einer vorhandenen Zeile verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bd75-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="8bd75-104">Die Zeilenvorlage bietet Ihnen eine bessere Kontrolle über das Aussehen und Verhalten von Zeilen als die <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> Eigenschaft ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8bd75-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="8bd75-105">Mit der Zeilenvorlage können Sie festlegen, eine <xref:System.Windows.Forms.DataGridViewRow> Eigenschaften, einschließlich <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="8bd75-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="8bd75-106">Es gibt einige Situationen, in denen Sie die Zeilenvorlage verwenden müssen, um einen bestimmten Effekt zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="8bd75-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="8bd75-107">Z. B. kann keine Informationen über die Zeilenhöhe gespeichert werden, einem <xref:System.Windows.Forms.DataGridViewCellStyle>, sodass Sie eine Zeilenvorlage verwenden müssen, um die Standardhöhe verwendet, die für alle Zeilen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8bd75-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="8bd75-108">Die Zeilenvorlage ist auch nützlich, wenn Sie Ihren eigenen Klassen abgeleitet erstellen <xref:System.Windows.Forms.DataGridViewRow> und Ihren benutzerdefinierten Typ verwendet werden, wenn das Steuerelement neue Zeilen hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8bd75-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bd75-109">Die Zeilenvorlage wird verwendet, nur, wenn Zeilen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8bd75-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="8bd75-110">Sie können nicht vorhandene Zeilen ändern, indem Sie die Zeilenvorlage ändern.</span><span class="sxs-lookup"><span data-stu-id="8bd75-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="8bd75-111">Verwenden der Zeilenvorlage</span><span class="sxs-lookup"><span data-stu-id="8bd75-111">To use the row template</span></span>  
  
-   <span data-ttu-id="8bd75-112">Legen Sie Eigenschaften für das Objekt abgerufen, die von der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8bd75-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8bd75-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8bd75-113">Compiling the Code</span></span>  
 <span data-ttu-id="8bd75-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8bd75-114">This example requires:</span></span>  
  
-   <span data-ttu-id="8bd75-115">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="8bd75-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="8bd75-116">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8bd75-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd75-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bd75-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="8bd75-118">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bd75-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="8bd75-119">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bd75-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
