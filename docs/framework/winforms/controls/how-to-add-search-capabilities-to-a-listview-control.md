---
title: 'Gewusst wie: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: 2049638998f7a8d099e14fab9c95384a49c67833
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528276"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="7a03e-102">Gewusst wie: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7a03e-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="7a03e-103">Häufig bei der Arbeit mit einer langen Liste von Elementen in einem <xref:System.Windows.Forms.ListView> Steuerelement aus, das Sie Suchfunktionen für den Benutzer anbieten möchten.</span><span class="sxs-lookup"><span data-stu-id="7a03e-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="7a03e-104">Die <xref:System.Windows.Forms.ListView> Steuerelement bietet diese Funktion auf zwei unterschiedliche Arten: Zuordnen von Text und Speicherort zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7a03e-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="7a03e-105">Die <xref:System.Windows.Forms.ListView.FindItemWithText%2A> Methode können Sie einen Text-Suchvorgänge auf eine <xref:System.Windows.Forms.ListView> in der Listen- oder Detailansicht Ansicht anhand einer Suchzeichenfolge und eine optionale Start- und Index endet.</span><span class="sxs-lookup"><span data-stu-id="7a03e-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="7a03e-106">Im Gegensatz dazu die <xref:System.Windows.Forms.ListView.FindNearestItem%2A> Methode ermöglicht das Suchen eines Elements in einer <xref:System.Windows.Forms.ListView> Symbol oder der Kachel bei einem gegebenen Satz von x- und y-Koordinaten und eine Richtung, gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="7a03e-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="7a03e-107">Ein Element mit Text suchen</span><span class="sxs-lookup"><span data-stu-id="7a03e-107">To find an item using text</span></span>  
  
1.  <span data-ttu-id="7a03e-108">Erstellen einer <xref:System.Windows.Forms.ListView> mit der <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.View.Details> oder <xref:System.Windows.Forms.View.List>, und füllen Sie die <xref:System.Windows.Forms.ListView> mit Elementen.</span><span class="sxs-lookup"><span data-stu-id="7a03e-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="7a03e-109">Rufen Sie die <xref:System.Windows.Forms.ListView.FindItemWithText%2A> -Methode auf und übergibt den Text des Elements, das Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="7a03e-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3.  <span data-ttu-id="7a03e-110">Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer grundlegenden <xref:System.Windows.Forms.ListView>, weisen Sie ihm Elemente und Texteingaben des Benutzers verwenden, um ein Element in der Liste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7a03e-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="7a03e-111">Um ein Element mithilfe der x- und y-Koordinaten zu finden.</span><span class="sxs-lookup"><span data-stu-id="7a03e-111">To find an item using x- and y-coordinates</span></span>  
  
1.  <span data-ttu-id="7a03e-112">Erstellen einer <xref:System.Windows.Forms.ListView> mit der <xref:System.Windows.Forms.View> -Eigenschaftensatz auf <xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>, und füllen Sie die <xref:System.Windows.Forms.ListView> mit Elementen.</span><span class="sxs-lookup"><span data-stu-id="7a03e-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="7a03e-113">Rufen Sie die <xref:System.Windows.Forms.ListView.FindNearestItem%2A> -Methode auf und übergibt die gewünschten x- und y-Koordinaten und die Richtung, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="7a03e-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3.  <span data-ttu-id="7a03e-114">Im folgenden Codebeispiel wird veranschaulicht, wie beim Erstellen einer grundlegenden Symbols <xref:System.Windows.Forms.ListView>, füllen sie mit Elementen, und zeichnen Sie die <xref:System.Windows.Forms.Control.MouseDown> Ereignis, um das nächste Element in der oben Richtung zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7a03e-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7a03e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a03e-115">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>  
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>  
 [<span data-ttu-id="7a03e-116">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7a03e-116">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="7a03e-117">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7a03e-117">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="7a03e-118">Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a03e-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
