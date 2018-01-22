---
title: "Übersicht über das ListView-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b79fecb0a537f4c568b4a57e9ce2bfab8d8e1005
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="listview-control-overview-windows-forms"></a>Übersicht über das ListView-Steuerelement (Windows Forms)
Mit dem <xref:System.Windows.Forms.ListView>-Steuerelement in Windows Forms wird eine Liste von Elementen mit Symbolen angezeigt. Mit einer Listenansicht können Sie eine Benutzeroberfläche erstellen, deren Darstellung dem rechten Fensterbereich von Windows Explorer ähnelt. Das Steuerelement verfügt über vier Ansichtsmodi: LargeIcon, SmallIcon, Liste und Details.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Was können Sie mit dem ListView-Steuerelement tun.  
  
> [!NOTE]
>  Eine zusätzliche Ansicht nebeneinander ist nur unter Windows XP und Windows Server 2003-Betriebssystem verfügbar. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 Der LargeIcon-Modus zeigt große Symbole neben den Elementtext. die Elemente werden in mehreren Spalten angezeigt, wenn das Steuerelement groß genug ist. Der SmallIcon-Modus ist identisch, außer dass es sich um kleine Symbole angezeigt. Die Listenmodus kleine Symbole angezeigt, jedoch befindet sich immer in einer einzelnen Spalte. Details-Modus werden die Elemente in mehreren Spalten angezeigt. Weitere Informationen finden Sie unter [wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md). Der Anzeigemodus richtet sich nach der <xref:System.Windows.Forms.ListView.View%2A> Eigenschaft. Alle Ansichtsmodi kann Bilder aus einer Bildliste angezeigt. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 Die folgende Tabelle enthält einige der <xref:System.Windows.Forms.ListView> Member und die Ansichten, die sie in gültig sind.  
  
|ListView-Element|Ansicht|  
|---------------------|----------|  
|<xref:System.Windows.Forms.ListView.Alignment%2A>-Eigenschaft|<xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoArrange%2A>-Eigenschaft|<xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>-Methode|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.Columns%2A>-Eigenschaft|<xref:System.Windows.Forms.View.Details> oder <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem>-Ereignis|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.FindItemWithText%2A>-Methode|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>oder <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.FindNearestItem%2A>-Methode|<xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.GetItemAt%2A>-Methode|<xref:System.Windows.Forms.View.Details> oder <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.Groups%2A>-Eigenschaft|Alle Ansichten außer<xref:System.Windows.Forms.View.List>|  
|<xref:System.Windows.Forms.ListView.HeaderStyle%2A>-Eigenschaft|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.InsertionMark%2A>-Eigenschaft|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>oder <xref:System.Windows.Forms.View.Tile>|  
  
 Die wichtigste Eigenschaft die <xref:System.Windows.Forms.ListView> Steuerelement <xref:System.Windows.Forms.ListView.Items%2A>, enthält die Elemente im Steuerelement angezeigt wird. Die <xref:System.Windows.Forms.ListView.SelectedItems%2A> Eigenschaft enthält eine Auflistung der derzeit im Steuerelement ausgewählten Elemente. Der Benutzer kann mehrere Elemente auswählen, z. B. Drag & drop mehrere Elemente gleichzeitig auf ein anderes Steuerelement, wenn die <xref:System.Windows.Forms.ListView.MultiSelect%2A> -Eigenschaftensatz auf `true`. Die <xref:System.Windows.Forms.ListView> -Steuerelement kann die Kontrollkästchen neben den Elementen anzeigen, wenn die <xref:System.Windows.Forms.ListView.CheckBoxes%2A> -Eigenschaftensatz auf `true`.  
  
 Die <xref:System.Windows.Forms.ListView.Activation%2A> Eigenschaft bestimmt, welche Aktion der Benutzer ausführen muss, zum Aktivieren eines Elements in der Liste: die Optionen sind <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>, und <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ItemActivation.OneClick>zur Aktivierung muss einem Klick auf das Element zu aktivieren. <xref:System.Windows.Forms.ItemActivation.TwoClick>Aktivierung muss der Benutzer doppelklicken, um das Element zu aktivieren. einem einzigen Mausklick ändert sich die Farbe des Elementtexts. <xref:System.Windows.Forms.ItemActivation.Standard>Aktivierung muss der Benutzer doppelklicken, um ein Element zu aktivieren, aber das Element ändert sich nicht auf die Darstellung.  
  
 Die <xref:System.Windows.Forms.ListView> Steuerelement unterstützt auch die visuellen Stile und andere Funktionen, die verfügbar sind auf der Windows XP-Plattform, einschließlich u. a. Einfügemarken, Gruppierung und Ansicht "Nebeneinander". Weitere Informationen finden Sie unter [Windows XP-Features und Windows Forms-Steuerelemente](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListView>  
 [ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [Gewusst wie: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [Gewusst wie: Auswählen eines Elements im ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 [Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)  
 [Gewusst wie: Anzeigen einer Einfügemarke in einem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 [Gewusst wie: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)
