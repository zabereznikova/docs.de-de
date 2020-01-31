---
title: Hinzufügen von Spalten zum ListView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: dd438ffbadddfc37ec9eb15e59a908bb58472a45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744584"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="367a4-102">Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="367a4-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="367a4-103">In der Detailansicht kann das <xref:System.Windows.Forms.ListView>-Steuerelement mehrere Spalten für jedes Listenelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="367a4-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="367a4-104">Sie können die Spalten verwenden, um dem Benutzer mehrere Arten von Informationen zu jedem Listenelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="367a4-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="367a4-105">Beispielsweise können in einer Liste mit Dateien der Dateiname, Dateityp, die Größe und das Datum der letzten Änderung der Datei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="367a4-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="367a4-106">Informationen zum Auffüllen der Spalten nach ihrer Erstellung finden Sie unter Gewusst [wie: Anzeigen von unter Elementen in Spalten mit dem Windows Forms ListView-Steuer](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="367a4-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="367a4-107">So fügen Sie Spalten Programm gesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="367a4-107">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="367a4-108">Legen Sie die <xref:System.Windows.Forms.ListView.View%2A>-Eigenschaft des Steuer Elements auf <xref:System.Windows.Forms.View.Details>fest.</span><span class="sxs-lookup"><span data-stu-id="367a4-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="367a4-109">Verwenden Sie die <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A>-Methode der <xref:System.Windows.Forms.ListView.Columns%2A>-Eigenschaft der Listenansicht.</span><span class="sxs-lookup"><span data-stu-id="367a4-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="367a4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="367a4-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="367a4-111">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="367a4-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="367a4-112">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="367a4-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
