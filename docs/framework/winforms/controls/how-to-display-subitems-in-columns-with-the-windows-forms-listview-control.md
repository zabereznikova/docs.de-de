---
title: "Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms"
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
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a9da292b5f65ea9dc44b47a8c3bc13cf43e83b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="423a9-102">Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="423a9-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="423a9-103">Windows Forms <xref:System.Windows.Forms.ListView> Steuerelement kann zusätzliche Text oder Unterelemente für jedes Element in der Detailansicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="423a9-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="423a9-104">Die erste Spalte zeigt den Elementtext, z. B. eine Mitarbeiter-Nummer.</span><span class="sxs-lookup"><span data-stu-id="423a9-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="423a9-105">Das zweite, dritte und die nachfolgende Spalten die erste Zweitens anzuzeigen und die folgenden verbundenen Unterelemente.</span><span class="sxs-lookup"><span data-stu-id="423a9-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="423a9-106">Ein Listenelement Unterelemente hinzu</span><span class="sxs-lookup"><span data-stu-id="423a9-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="423a9-107">Fügen Sie alle Spalten benötigt.</span><span class="sxs-lookup"><span data-stu-id="423a9-107">Add any columns needed.</span></span> <span data-ttu-id="423a9-108">Da die erste Spalte des Elements angezeigt werden <xref:System.Windows.Forms.ListView.Text%2A> -Eigenschaft, benötigen Sie eine Spalte mehr als Unterelemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="423a9-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="423a9-109">Weitere Informationen zum Hinzufügen von Spalten finden Sie unter [wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="423a9-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="423a9-110">Rufen Sie die <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> -Methode der Auflistung zurückgegeben werden, indem Sie die <xref:System.Windows.Forms.ListViewItem.SubItems%2A> Eigenschaft eines Elements.</span><span class="sxs-lookup"><span data-stu-id="423a9-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="423a9-111">Das folgende Codebeispiel legt fest, die Employee Name "und" Department für ein Listenelement.</span><span class="sxs-lookup"><span data-stu-id="423a9-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="423a9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="423a9-112">See Also</span></span>  
 [<span data-ttu-id="423a9-113">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="423a9-113">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="423a9-114">Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="423a9-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="423a9-115">Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="423a9-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="423a9-116">Gewusst wie: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="423a9-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="423a9-117">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="423a9-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
