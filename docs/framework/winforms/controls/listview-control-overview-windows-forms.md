---
title: Übersicht über das ListView-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: 7b7eac942a7e857ad731c0f77389e84aee287c08
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952166"
---
# <a name="listview-control-overview-windows-forms"></a>Übersicht über das ListView-Steuerelement (Windows Forms)
Mit dem <xref:System.Windows.Forms.ListView>-Steuerelement in Windows Forms wird eine Liste von Elementen mit Symbolen angezeigt. Mit einer Listenansicht können Sie eine Benutzeroberfläche erstellen, deren Darstellung dem rechten Fensterbereich von Windows Explorer ähnelt. Das-Steuerelement verfügt über vier Ansichtsmodi: LargeIcon, SmallIcon, List und Details.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Was Sie mit dem ListView-Steuerelement tun können  
  
> [!NOTE]
> Ein zusätzlicher Ansichtsmodus (Kachel) ist nur unter Windows XP und dem Betriebssystem Windows Server 2003 verfügbar. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren Sie die Kachel Ansicht in einem Windows Forms ListView-Steuer](how-to-enable-tile-view-in-a-windows-forms-listview-control.md)Element.  
  
 Im LargeIcon-Modus werden große Symbole neben dem Element Text angezeigt. Wenn das Steuerelement groß genug ist, werden die Elemente in mehreren Spalten angezeigt. Der SmallIcon-Modus ist identisch, mit dem Unterschied, dass kleine Symbole angezeigt werden. Der Listenmodus zeigt kleine Symbole an, befindet sich jedoch immer in einer einzelnen Spalte. Im Detail Modus werden Elemente in mehreren Spalten angezeigt. Weitere Informationen finden Sie unter [Vorgehensweise: Fügen Sie dem Windows Forms ListView-Steuer](how-to-add-columns-to-the-windows-forms-listview-control.md)Element Spalten hinzu. Der Ansichtsmodus wird von der <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaft bestimmt. Alle Ansichtsmodi können Bilder aus Bildlisten anzeigen. Weitere Informationen finden Sie unter [Vorgehensweise: Zeigen Sie Symbole für das Windows Forms ListView](how-to-display-icons-for-the-windows-forms-listview-control.md)-Steuerelement an.  
  
 In der folgenden Tabelle sind einige <xref:System.Windows.Forms.ListView> der Member und Sichten aufgeführt, in denen Sie gültig sind.  
  
|ListView-Member|Ansicht|  
|---------------------|----------|  
|<xref:System.Windows.Forms.ListView.Alignment%2A> -Eigenschaft|<xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoArrange%2A> -Eigenschaft|<xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>-Methode|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.Columns%2A> -Eigenschaft|<xref:System.Windows.Forms.View.Details> oder <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem> -Ereignis|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.FindItemWithText%2A>-Methode|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>oder <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.FindNearestItem%2A>-Methode|<xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.GetItemAt%2A>-Methode|<xref:System.Windows.Forms.View.Details> oder <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.Groups%2A> -Eigenschaft|Alle Sichten außer<xref:System.Windows.Forms.View.List>|  
|<xref:System.Windows.Forms.ListView.HeaderStyle%2A> -Eigenschaft|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.InsertionMark%2A> -Eigenschaft|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>oder <xref:System.Windows.Forms.View.Tile>|  
  
 Die Schlüsseleigenschaft des <xref:System.Windows.Forms.ListView> -Steuer Elements ist <xref:System.Windows.Forms.ListView.Items%2A>, das die vom-Steuerelement angezeigten Elemente enthält. Die <xref:System.Windows.Forms.ListView.SelectedItems%2A> -Eigenschaft enthält eine Auflistung der Elemente, die derzeit im-Steuerelement ausgewählt sind. Der Benutzer kann mehrere Elemente auswählen, z. b. zum Ziehen und Ablegen mehrerer Elemente gleichzeitig auf ein anderes Steuerelement <xref:System.Windows.Forms.ListView.MultiSelect%2A> , wenn die- `true`Eigenschaft auf festgelegt ist. Das <xref:System.Windows.Forms.ListView> -Steuerelement kann Kontrollkästchen neben den Elementen anzeigen, wenn <xref:System.Windows.Forms.ListView.CheckBoxes%2A> die-Eigenschaft auf `true`festgelegt ist.  
  
 Die <xref:System.Windows.Forms.ListView.Activation%2A> -Eigenschaft bestimmt, welche Art von Aktion der Benutzer ausführen muss, um ein Element in der Liste zu aktivieren <xref:System.Windows.Forms.ItemActivation.Standard>: die Optionen <xref:System.Windows.Forms.ItemActivation.TwoClick>sind, <xref:System.Windows.Forms.ItemActivation.OneClick>und. <xref:System.Windows.Forms.ItemActivation.OneClick>die Aktivierung erfordert nur einen Mausklick, um das Element zu aktivieren. <xref:System.Windows.Forms.ItemActivation.TwoClick>die Aktivierung erfordert, dass der Benutzer doppelklicken muss, um das Element zu aktivieren. mit einem einzigen Mausklick wird die Farbe des Element Texts geändert. <xref:System.Windows.Forms.ItemActivation.Standard>die Aktivierung erfordert, dass der Benutzer einen Doppelklick durchführt, um ein Element zu aktivieren, aber das Element ändert sich nicht.  
  
 Das <xref:System.Windows.Forms.ListView> Steuerelement unterstützt auch die visuellen Stile und andere Features, die auf der Windows XP-Plattform verfügbar sind, einschließlich Gruppierung, Kachel Ansicht und Einfügemarkierungen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem Windows Forms ListView-Steuerelement](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von Spalten zum Windows Forms ListView-Steuerelement](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeige Symbole für das Windows Forms ListView-Steuerelement](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von unter Elementen in Spalten mit dem Windows Forms ListView-Steuerelement](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Wählen Sie ein Element im Windows Forms ListView-Steuerelement aus.](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [Vorgehensweise: Gruppieren von Elementen in einem Windows Forms ListView-Steuerelement](how-to-group-items-in-a-windows-forms-listview-control.md)
- [Vorgehensweise: Einfügemarke in einem Windows Forms ListView-Steuerelement anzeigen](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement](how-to-add-search-capabilities-to-a-listview-control.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Informationen zu einem TreeView-oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
