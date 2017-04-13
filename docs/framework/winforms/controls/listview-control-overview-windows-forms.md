---
title: "&#220;bersicht &#252;ber das ListView-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListView"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Listenansichten"
  - "Listen"
  - "ListView-Steuerelement [Windows Forms], Informationen über das ListView-Steuerelement"
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;bersicht &#252;ber das ListView-Steuerelement (Windows&#160;Forms)
Mit dem <xref:System.Windows.Forms.ListView>\-Steuerelement in Windows Forms wird eine Liste von Elementen mit Symbolen angezeigt.  Mit einer Listenansicht kann eine Benutzeroberfläche erstellt werden, die dem rechten Bereich von Windows Explorer ähnelt.  Das Steuerelement verfügt über vier Ansichtsmodi: **LargeIcon**, **SmallIcon**, **List** und **Details**.  
  
## Mögliche Aktionen mit dem ListView\-Steuerelement  
  
> [!NOTE]
>  Die zusätzliche Ansicht Nebeneinander ist nur unter den Betriebssystemen Windows XP und Windows Server 2003 verfügbar.  Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren der Tile\-Ansicht in einem ListView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 Im **LargeIcon**\-Modus werden große Symbole neben dem Elementtext angezeigt. Die Anzeige der Elemente erfolgt in mehreren Spalten, sofern die Größe des Steuerelements ausreichend ist.  Der **SmallIcon**\-Modus entspricht dem **LargeIcon**\-Modus, es werden jedoch kleine Symbole angezeigt.  Im **List**\-Modus werden kleine Symbole angezeigt, jedoch immer in einer einzigen Spalte.  Im **Details**\-Modus erfolgt die Anzeige der Elemente in mehreren Spalten.  Ausführlichere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Spalten zum ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).  Der Ansichtsmodus wird durch die <xref:System.Windows.Forms.ListView.View%2A>\-Eigenschaft bestimmt.  Bilder aus Bildlisten können in allen Ansichtsmodi angezeigt werden.  Ausführlichere Informationen finden Sie unter [Gewusst wie: Anzeigen von Symbolen für das ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 In der nachstehenden Tabelle sind einige <xref:System.Windows.Forms.ListView>\-Member und die Ansichten, in denen sie gültig sind, aufgelistet.  
  
|ListView\-Member|Ansicht|  
|----------------------|-------------|  
|<xref:System.Windows.Forms.ListView.Alignment%2A>\-Eigenschaft|<xref:System.Windows.Forms.View> oder <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.AutoArrange%2A>\-Eigenschaft|<xref:System.Windows.Forms.View> oder <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>\-Methode|<xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.Columns%2A>\-Eigenschaft|<xref:System.Windows.Forms.View> oder <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem>\-Ereignis|<xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.FindItemWithText%2A>\-Methode|<xref:System.Windows.Forms.View>, <xref:System.Windows.Forms.View> oder <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.FindNearestItem%2A>\-Methode|<xref:System.Windows.Forms.View> oder <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.GetItemAt%2A>\-Methode|<xref:System.Windows.Forms.View> oder <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.Groups%2A>\-Eigenschaft|Alle Ansichtsmodi mit Ausnahme von <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.HeaderStyle%2A>\-Eigenschaft|<xref:System.Windows.Forms.View>.|  
|<xref:System.Windows.Forms.ListView.InsertionMark%2A>\-Eigenschaft|<xref:System.Windows.Forms.View>, <xref:System.Windows.Forms.View> oder <xref:System.Windows.Forms.View>|  
  
 Die Haupteigenschaft des <xref:System.Windows.Forms.ListView>\-Steuerelements ist die <xref:System.Windows.Forms.ListView.Items%2A>\-Eigenschaft, die die vom Steuerelement angezeigten Elemente enthält.  Die <xref:System.Windows.Forms.ListView.SelectedItems%2A>\-Eigenschaft enthält eine Auflistung der Elemente, die aktuell im Steuerelement ausgewählt sind.  Der Benutzer kann mehrere Elemente auswählen, z. B. um mehrere Elemente gleichzeitig auf ein anderes Steuerelement zu ziehen und dort abzulegen, sofern für die <xref:System.Windows.Forms.ListView.MultiSelect%2A>\-Eigenschaft `true` festgelegt ist.  Das <xref:System.Windows.Forms.ListView>\-Steuerelement kann Kontrollkästchen neben den Elementen anzeigen, wenn für die <xref:System.Windows.Forms.ListView.CheckBoxes%2A>\-Eigenschaft `true` festgelegt ist.  
  
 Mit der <xref:System.Windows.Forms.ListView.Activation%2A>\-Eigenschaft wird festgelegt, welche Aktion der Benutzer ausführen muss, um ein Element in der Liste zu aktivieren: die Optionen sind <xref:System.Windows.Forms.ItemActivation>, <xref:System.Windows.Forms.ItemActivation> und <xref:System.Windows.Forms.ItemActivation>.  Für die <xref:System.Windows.Forms.ItemActivation>\-Aktivierung ist ein Einfachklick zur Aktivierung des Elements erforderlich.  Zur <xref:System.Windows.Forms.ItemActivation>\-Aktivierung muss der Benutzer doppelklicken, um das Element zu aktivieren. Mit einem Einfachklick wird die Farbe des Elementtextes geändert.  Zur <xref:System.Windows.Forms.ItemActivation>\-Aktivierung muss der Benutzer doppelklicken, um ein Element zu aktivieren, die Darstellung des Elements ändert sich jedoch nicht.  
  
 Das <xref:System.Windows.Forms.ListView>\-Steuerelement unterstützt auch die unter Windows XP verfügbaren visuellen Stile und zusätzlichen Features, z. B. Gruppierung, Ansicht Nebeneinander und Einfügemarken.  Weitere Informationen finden Sie unter [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/de-de/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0).  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListView>   
 [ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Gewusst wie: Hinzufügen von Spalten zum ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Gewusst wie: Anzeigen von Symbolen für das ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)   
 [Gewusst wie: Auswählen eines Elements im ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)   
 [Gewusst wie: Gruppieren von Elementen in einem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)   
 [Gewusst wie: Anzeigen einer Einfügemarke in einem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)   
 [Gewusst wie: Hinzufügen von Suchfunktionen zu einem ListView\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)   
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView\- oder ListView\-Steuerelement \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [Gewusst wie: Erstellen einer Multipane\-Benutzeroberfläche mit Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)