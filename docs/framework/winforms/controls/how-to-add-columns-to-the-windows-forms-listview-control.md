---
title: Hinzufügen von Spalten zum ListView-Steuerelement
description: Erfahren Sie, wie Sie dem Windows Forms ListView-Steuerelement Spalten hinzufügen, um verschiedene Arten von Informationen zu jedem Listenelement anzuzeigen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 7ca4e86ca3a9679876f2525c49596534f175096a
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174561"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="a2cef-103">Vorgehensweise: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2cef-103">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="a2cef-104">In der Detailansicht kann das <xref:System.Windows.Forms.ListView> Steuerelement mehrere Spalten für jedes Listenelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2cef-104">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="a2cef-105">Sie können die Spalten verwenden, um dem Benutzer mehrere Arten von Informationen zu jedem Listenelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2cef-105">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="a2cef-106">Beispielsweise können in einer Liste mit Dateien der Dateiname, Dateityp, die Größe und das Datum der letzten Änderung der Datei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a2cef-106">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="a2cef-107">Informationen zum Auffüllen der Spalten nach ihrer Erstellung finden Sie unter Gewusst [wie: Anzeigen von unter Elementen in Spalten mit dem Windows Forms ListView-Steuer](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="a2cef-107">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="a2cef-108">So fügen Sie Spalten Programm gesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="a2cef-108">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="a2cef-109">Legen Sie die-Eigenschaft des-Steuer Elements <xref:System.Windows.Forms.ListView.View%2A> auf fest <xref:System.Windows.Forms.View.Details> .</span><span class="sxs-lookup"><span data-stu-id="a2cef-109">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="a2cef-110">Verwenden Sie die <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> -Methode der-Eigenschaft der Listenansicht <xref:System.Windows.Forms.ListView.Columns%2A> .</span><span class="sxs-lookup"><span data-stu-id="a2cef-110">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="a2cef-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2cef-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="a2cef-112">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a2cef-112">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="a2cef-113">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a2cef-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
