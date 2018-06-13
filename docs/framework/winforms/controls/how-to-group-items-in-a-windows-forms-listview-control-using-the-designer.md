---
title: 'Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: c532cadc5b42c26f1598c4e7586309cf690456bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539337"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers
Die Grouping-Funktion von der <xref:System.Windows.Forms.ListView> Steuerelement können Sie verwandte Elemente in Gruppen anzuzeigen. Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppenheader getrennt, die die Gruppentitel enthalten. Sie können <xref:System.Windows.Forms.ListView> Gruppen aus, um die Navigation in umfangreichen Listen einfacher durch Gruppieren Elemente alphabetisch nach Datum oder eine beliebige andere logische Gruppierung vornehmen. Die folgende Abbildung zeigt einige gruppierten Elemente.  
  
 ![ListView-Gruppen](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.ListView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
 Um die Gruppierung zu aktivieren, müssen Sie zuerst eine oder mehrere erstellen <xref:System.Windows.Forms.ListViewGroup> Objekte im Designer oder programmgesteuert. Nachdem eine Gruppe definiert wurde, können Sie Elemente zuweisen.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> Gruppen stehen nur in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] bei einem Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode. Unter älteren Betriebssystemen Code in Zusammenhang mit Gruppen hat keine Auswirkungen, und die Gruppen werden nicht angezeigt. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a>Zum Hinzufügen oder Entfernen von Gruppen im designer  
  
1.  In der **Eigenschaften** Fenster, klicken Sie auf die **Auslassungszeichen** (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben die <xref:System.Windows.Forms.ListView.Groups%2A> Eigenschaft.  
  
     Die **ListViewGroup Auflistungs-Editor** angezeigt wird.  
  
2.  Um eine Gruppe hinzuzufügen, klicken Sie auf die **hinzufügen** Schaltfläche. Sie können dann Eigenschaften der neuen Gruppe festlegen, wie z. B. die <xref:System.Windows.Forms.ListViewGroup.Header%2A> und <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> Eigenschaften. Um eine Gruppe zu entfernen, wählen Sie ihn aus, und klicken Sie auf die **entfernen** Schaltfläche.  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a>Zum Zuweisen von Elementen zu Gruppen im designer  
  
1.  In der **Eigenschaften** Fenster, klicken Sie auf die **Auslassungszeichen** (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben die <xref:System.Windows.Forms.ListView.Items%2A> Eigenschaft.  
  
     Die **ListViewItem Auflistungs-Editor** angezeigt wird.  
  
2.  Um ein neues Element hinzuzufügen, klicken Sie auf die **hinzufügen** Schaltfläche. Sie können dann Eigenschaften des neuen Elements festlegen, wie z. B. die <xref:System.Windows.Forms.ListViewItem.Text%2A> und <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> Eigenschaften.  
  
3.  Wählen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A> Eigenschaft, und wählen Sie eine Gruppe aus der Dropdown-Liste.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Übersicht über das ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Windows XP-Features und Windows Forms-Steuerelemente](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
