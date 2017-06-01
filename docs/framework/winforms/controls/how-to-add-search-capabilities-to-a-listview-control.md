---
title: "Gewusst wie: Hinzuf&#252;gen von Suchfunktionen zu einem ListView-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Listenansichten, Aktivieren von Suchvorgängen"
  - "Listen, Aktivieren von Suchvorgängen"
  - "ListView-Steuerelement [Windows Forms], Hinzufügen von Suchfunktionen"
  - "Suchen, Hinzufügen von Suchfunktionen zu ListView-Steuerelementen"
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Hinzuf&#252;gen von Suchfunktionen zu einem ListView-Steuerelement
Bei der Arbeit mit einer großen Liste von Elementen in einem <xref:System.Windows.Forms.ListView>\-Steuerelement, möchten Sie dem Benutzer häufig Suchfunktionen ermöglichen.  Das <xref:System.Windows.Forms.ListView>\-Steuerelement bietet diese Funktionen auf zwei verschiedene Weisen an: durch Textvergleich und Positionssuche.  
  
 Mithilfe der <xref:System.Windows.Forms.ListView.FindItemWithText%2A>\-Methode können Sie eine Textsuche in einer <xref:System.Windows.Forms.ListView> in der Listen\- oder Detailansicht anhand einer Suchzeichenfolge und eines Start\- und Endeindex durchführen.  Mithilfe der <xref:System.Windows.Forms.ListView.FindNearestItem%2A>\-Methode können Sie hingegen ein Element in einer <xref:System.Windows.Forms.ListView> in der Symbol\- oder Tile\-Ansicht anhand von X\- und Y\-Koordinaten und einer Suchrichtung suchen.  
  
### So suchen Sie ein Element mithilfe von Text  
  
1.  Erstellen Sie eine <xref:System.Windows.Forms.ListView>, während die <xref:System.Windows.Forms.ListView.View%2A>\-Eigenschaft auf <xref:System.Windows.Forms.View> oder <xref:System.Windows.Forms.View> festgelegt ist, und füllen Sie dann die <xref:System.Windows.Forms.ListView> mit Elementen.  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ListView.FindItemWithText%2A>\-Methode auf, und übergeben Sie den Text des gesuchten Elements.  
  
3.  Im folgenden Codebeispiel wird gezeigt, wie Sie eine einfache <xref:System.Windows.Forms.ListView> erstellen, mit Elementen füllen und anhand der Texteingabe eines Benutzers ein Element in der Liste suchen.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### So suchen Sie ein Element mithilfe von X\- und Y\-Koordinaten  
  
1.  Erstellen Sie eine <xref:System.Windows.Forms.ListView>, während die <xref:System.Windows.Forms.View>\-Eigenschaft auf <xref:System.Windows.Forms.View> oder <xref:System.Windows.Forms.View> festgelegt ist, und füllen Sie dann die <xref:System.Windows.Forms.ListView> mit Elementen.  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ListView.FindNearestItem%2A>\-Methode auf, und übergeben Sie die gewünschten X\- und Y\-Koordinaten und die gewünschte Suchrichtung.  
  
3.  Im folgenden Codebeispiel wird gezeigt, wie eine einfache <xref:System.Windows.Forms.ListView> mit Symbolen erstellt, mit Elementen gefüllt und das <xref:System.Windows.Forms.Control.MouseDown>\-Ereignis erfasst wird, um das nächste Element in Aufwärtsrichtung gesucht wird.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>   
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>   
 [ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)