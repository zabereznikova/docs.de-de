---
title: 'Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 7c25c012798adcf90c652beb91a7550406e5f8ff
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321431"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers
Die Grouping-Funktion von der <xref:System.Windows.Forms.ListView> -Steuerelement ermöglicht Ihnen, verwandte Elemente in Gruppen anzuzeigen. Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppenheader getrennt, die die Gruppentitel enthalten. Sie können <xref:System.Windows.Forms.ListView> Gruppen zum Navigieren in umfangreichen Listen einfacher durch Gruppieren von Elementen alphabetisch nach Datum oder eine beliebige andere logische Gruppierung. Die folgende Abbildung zeigt einige gruppierte Elemente.  
  
 ![ListView-Gruppen](./media/listviewgroups.gif "ListViewGroups")  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.ListView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
 Aktivieren der Gruppierung, müssen Sie zunächst eine oder mehrere erstellen <xref:System.Windows.Forms.ListViewGroup> Objekte, die entweder im Designer oder programmgesteuert. Sobald eine Gruppe definiert wurde, können Sie Elemente darin zuweisen.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> Gruppen stehen nur auf [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] bei einem Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode. Unter früheren Betriebssystemen Code im Zusammenhang mit Gruppen hat keine Auswirkungen, und die Gruppen werden nicht angezeigt. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a>Zum Hinzufügen oder Entfernen von Gruppen im designer  
  
1. In der **Eigenschaften** Fenster, klicken Sie auf die **Auslassungspunkte** (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) neben die <xref:System.Windows.Forms.ListView.Groups%2A> Eigenschaft.  
  
     Die **ListViewGroup Auflistungs-Editor** angezeigt wird.  
  
2. Um eine Gruppe hinzuzufügen, klicken Sie auf die **hinzufügen** Schaltfläche. Sie können dann Eigenschaften der neuen Gruppe festlegen, wie z. B. die <xref:System.Windows.Forms.ListViewGroup.Header%2A> und <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> Eigenschaften. Um eine Gruppe zu entfernen, wählen Sie ihn, und klicken Sie auf die **entfernen** Schaltfläche.  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a>Zuweisen von Elementen zu Gruppen im designer  
  
1. In der **Eigenschaften** Fenster, klicken Sie auf die **Auslassungspunkte** (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) neben die <xref:System.Windows.Forms.ListView.Items%2A> Eigenschaft.  
  
     Die **ListViewItem Auflistungs-Editor** angezeigt wird.  
  
2. Um ein neues Element hinzuzufügen, klicken Sie auf die **hinzufügen** Schaltfläche. Sie können dann Eigenschaften des neuen Elements, z. B. Festlegen der <xref:System.Windows.Forms.ListViewItem.Text%2A> und <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> Eigenschaften.  
  
3. Wählen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A> Eigenschaft, und wählen Sie eine Gruppe aus der Dropdown-Liste.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
