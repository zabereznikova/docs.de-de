---
title: 'Vorgehensweise: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement'
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
ms.openlocfilehash: c25349d4ab981d422ade93944f709c3068a7aba9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722363"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>Vorgehensweise: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement
Wenn bei der Arbeit mit einer umfangreichen Liste von Elementen in einer <xref:System.Windows.Forms.ListView> -Steuerelement, das Sie Suchfunktionen für den Benutzer zu anbieten möchten. Die <xref:System.Windows.Forms.ListView> Steuerelement bietet diese Funktion auf zwei Arten: Zuordnen von Text und Speicherort zu suchen.  
  
 Die <xref:System.Windows.Forms.ListView.FindItemWithText%2A> Methode können Sie auf eine Textsuche durchführen einer <xref:System.Windows.Forms.ListView> in Listen- oder Detailmodus anzeigen, die anhand einer Suchzeichenfolge und eine Start- und endIndex. Im Gegensatz dazu die <xref:System.Windows.Forms.ListView.FindNearestItem%2A> Methode können Sie finden Sie ein Element in eine <xref:System.Windows.Forms.ListView> im Symbol oder Tile-Ansicht, wenn Sie eine Gruppe von x- und y-Koordinaten und eine Richtung zu suchen.  
  
### <a name="to-find-an-item-using-text"></a>Ein Element mit Text suchen  
  
1.  Erstellen einer <xref:System.Windows.Forms.ListView> mit der <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.View.Details> oder <xref:System.Windows.Forms.View.List>, und füllen Sie dann die <xref:System.Windows.Forms.ListView> mit Elementen.  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ListView.FindItemWithText%2A> -Methode, übergeben Sie den Text des Elements, das Sie suchen möchten.  
  
3.  Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen eines grundlegenden <xref:System.Windows.Forms.ListView>mit Elementen zu füllen und Texteingabe des Benutzers verwenden, um ein Element in der Liste zu suchen.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>Um ein Element, das mit x- und y-Koordinaten zu finden.  
  
1.  Erstellen einer <xref:System.Windows.Forms.ListView> mit der <xref:System.Windows.Forms.View> -Eigenschaftensatz auf <xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>, und füllen Sie dann die <xref:System.Windows.Forms.ListView> mit Elementen.  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ListView.FindNearestItem%2A> Methode und übergeben die gewünschten x- und y-Koordinaten und die Richtung, die Sie suchen möchten.  
  
3.  Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen eines grundlegenden Symbols <xref:System.Windows.Forms.ListView>, füllen Sie es mit Elementen, und zeichnen Sie die <xref:System.Windows.Forms.Control.MouseDown> Ereignis an das nächstgelegene Element gesucht, in der sich Richtung.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
