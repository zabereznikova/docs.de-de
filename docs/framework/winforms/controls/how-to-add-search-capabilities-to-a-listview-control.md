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
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>Gewusst wie: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement
Häufig bei der Arbeit mit einer langen Liste von Elementen in einem <xref:System.Windows.Forms.ListView> Steuerelement aus, das Sie Suchfunktionen für den Benutzer anbieten möchten. Die <xref:System.Windows.Forms.ListView> Steuerelement bietet diese Funktion auf zwei unterschiedliche Arten: Zuordnen von Text und Speicherort zu suchen.  
  
 Die <xref:System.Windows.Forms.ListView.FindItemWithText%2A> Methode können Sie einen Text-Suchvorgänge auf eine <xref:System.Windows.Forms.ListView> in der Listen- oder Detailansicht Ansicht anhand einer Suchzeichenfolge und eine optionale Start- und Index endet. Im Gegensatz dazu die <xref:System.Windows.Forms.ListView.FindNearestItem%2A> Methode ermöglicht das Suchen eines Elements in einer <xref:System.Windows.Forms.ListView> Symbol oder der Kachel bei einem gegebenen Satz von x- und y-Koordinaten und eine Richtung, gesucht werden soll.  
  
### <a name="to-find-an-item-using-text"></a>Ein Element mit Text suchen  
  
1.  Erstellen einer <xref:System.Windows.Forms.ListView> mit der <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.View.Details> oder <xref:System.Windows.Forms.View.List>, und füllen Sie die <xref:System.Windows.Forms.ListView> mit Elementen.  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ListView.FindItemWithText%2A> -Methode auf und übergibt den Text des Elements, das Sie suchen möchten.  
  
3.  Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer grundlegenden <xref:System.Windows.Forms.ListView>, weisen Sie ihm Elemente und Texteingaben des Benutzers verwenden, um ein Element in der Liste zu suchen.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>Um ein Element mithilfe der x- und y-Koordinaten zu finden.  
  
1.  Erstellen einer <xref:System.Windows.Forms.ListView> mit der <xref:System.Windows.Forms.View> -Eigenschaftensatz auf <xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>, und füllen Sie die <xref:System.Windows.Forms.ListView> mit Elementen.  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ListView.FindNearestItem%2A> -Methode auf und übergibt die gewünschten x- und y-Koordinaten und die Richtung, die Sie suchen möchten.  
  
3.  Im folgenden Codebeispiel wird veranschaulicht, wie beim Erstellen einer grundlegenden Symbols <xref:System.Windows.Forms.ListView>, füllen sie mit Elementen, und zeichnen Sie die <xref:System.Windows.Forms.Control.MouseDown> Ereignis, um das nächste Element in der oben Richtung zu suchen.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>  
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>  
 [ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Übersicht über das ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
