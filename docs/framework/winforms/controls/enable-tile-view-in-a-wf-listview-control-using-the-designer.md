---
title: 'Gewusst wie: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 86645396033ca1c3cfb025ba6db42b726f7e7969
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734394"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Gewusst wie: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms mithilfe des Designers
Die Funktion der Tile-Ansicht der <xref:System.Windows.Forms.ListView> -Steuerelement können Sie eine visuelle Balance zwischen grafischen und textbasierten Daten bereitstellen. Die textbasierten Daten, die für ein Element in der Ansicht "Nebeneinander" angezeigt werden, sind die gleichen wie die Spalteninformationen, die für die Detailansicht definiert wurden. Markieren Sie Funktionen in Funktionen der Tile-Ansicht in Kombination mit der Gruppierung oder Einfügen der <xref:System.Windows.Forms.ListView> Steuerelement.  
  
 Die Ansicht "Nebeneinander" verwendet ein 32 x 32-Symbol und mehreren Textzeilen, wie in der folgenden Abbildung gezeigt.  
  
 ![Ansicht in einem ListView-Steuerelement "Nebeneinander"](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Kachel anzeigen, dass die Eigenschaften und Methoden können Sie angeben, welche Spaltenfelder für jedes Element angezeigt werden soll, und die Größe und die Darstellung aller Elemente in einem Zeitfenster von Tile-Ansicht zusammen zu steuern. Aus Gründen der Übersichtlichkeit ist die erste Textzeile in einer Kachel immer der Name des Elements. Er kann nicht geändert werden.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.ListView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Die Ansicht "Nebeneinander" steht unter [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur zur Verfügung, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>-Methode aufruft. Unter älteren Betriebssystemen hat Code in Bezug auf die Ansicht "Nebeneinander" keine Auswirkungen, und das <xref:System.Windows.Forms.ListView>-Steuerelement wird in der Ansicht "Große Symbole" angezeigt. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-tile-view-in-the-designer"></a>Ansicht "Nebeneinander" im Designer festgelegt.  
  
1.  Wählen Sie die <xref:System.Windows.Forms.ListView> Steuerelement auf Ihrem Formular.  
  
2.  In der **Eigenschaften** wählen Sie im Fenster der <xref:System.Windows.Forms.ListView.View%2A> Eigenschaft, und wählen Sie **Kachel**.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [Windows XP-Features und Windows Forms-Steuerelemente](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Übersicht über das ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
