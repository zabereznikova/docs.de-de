---
title: 'Gewusst wie: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 836d82930c7ff41e7a4ae64a577baa5f1ba780c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528917"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Gewusst wie: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms mithilfe des Designers
Die Funktion "Nebeneinanderanzeige" von der <xref:System.Windows.Forms.ListView> Steuerelement ermöglicht Ihnen, eine visuelle Balance zwischen grafischen und textbasierten Daten zu senden. Die textbasierten Daten, die für ein Element in der Ansicht "Nebeneinander" angezeigt werden, sind die gleichen wie die Spalteninformationen, die für die Detailansicht definiert wurden. Funktionen der Tile-Ansicht in Kombination mit der Gruppierung oder einfügen markieren Funktionen in der <xref:System.Windows.Forms.ListView> Steuerelement.  
  
 Ansicht "Nebeneinander" verwendet ein 32 x 32-Symbol und mehreren Textzeilen an, wie in der folgenden Abbildung gezeigt.  
  
 ![Tile-Ansicht in einem ListView-Steuerelement](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Tile-Ansicht, dass Eigenschaften und Methoden können Sie angeben, welche Spaltenfelder, die für jedes Element angezeigt, und die Größe und die Darstellung aller Elemente innerhalb einer Kachel im Fenster zusammen zu steuern. Aus Gründen der Übersichtlichkeit ist die erste Zeile des Texts in einer Kachel immer den Namen des Elements. Es kann nicht geändert werden.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.ListView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Die Ansicht "Nebeneinander" steht unter [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur zur Verfügung, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>-Methode aufruft. Unter älteren Betriebssystemen hat Code in Bezug auf die Ansicht "Nebeneinander" keine Auswirkungen, und das <xref:System.Windows.Forms.ListView>-Steuerelement wird in der Ansicht "Große Symbole" angezeigt. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-tile-view-in-the-designer"></a>Um die Ansicht "Nebeneinander" im Designer festgelegt.  
  
1.  Wählen Sie die <xref:System.Windows.Forms.ListView> Steuerelement auf dem Formular.  
  
2.  In der **Eigenschaften** wählen die <xref:System.Windows.Forms.ListView.View%2A> Eigenschaft, und wählen Sie **Kachel**.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [Windows XP-Features und Windows Forms-Steuerelemente](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Übersicht über das ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
