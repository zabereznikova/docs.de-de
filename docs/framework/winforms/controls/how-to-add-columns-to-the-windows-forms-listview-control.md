---
title: "Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms"
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
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8df87e62e8c19ee6e30ffdbc2a4e473b444f538
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="0a8e9-102">Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a8e9-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="0a8e9-103">In der Detailansicht der <xref:System.Windows.Forms.ListView> -Steuerelement kann mehrere Spalten für jedes Listenelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0a8e9-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="0a8e9-104">Die Spalten können Sie für den Benutzer verschiedene Arten von Informationen zu jedem Listenelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0a8e9-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="0a8e9-105">Beispielsweise konnte eine Liste der Dateien angezeigt, die Dateinamen, Dateityp, Größe und das Datum, an der letzten der Datei Änderung.</span><span class="sxs-lookup"><span data-stu-id="0a8e9-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="0a8e9-106">Informationen zum Auffüllen der Spalten aus, nachdem sie erstellt wurden, finden Sie unter [Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0a8e9-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="0a8e9-107">So fügen Sie Spalten programmgesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="0a8e9-107">To add columns programmatically</span></span>  
  
1.  <span data-ttu-id="0a8e9-108">Legen Sie das Steuerelement <xref:System.Windows.Forms.ListView.View%2A> Eigenschaft <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="0a8e9-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2.  <span data-ttu-id="0a8e9-109">Verwenden der <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> Methode der Listenansicht <xref:System.Windows.Forms.ListView.Columns%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0a8e9-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="0a8e9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a8e9-110">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 [<span data-ttu-id="0a8e9-111">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0a8e9-111">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="0a8e9-112">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0a8e9-112">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
