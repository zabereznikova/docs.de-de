---
title: 'Vorgehensweise: Einfrieren von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: 814eea9bbbee3e1a585eda67ec85d86994d8ce23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539817"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Einfrieren von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Wenn Benutzer Daten anzeigen, die in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement in Windows Forms angezeigt werden, müssen sie mitunter häufig auf eine bestimmte Spalte oder Gruppe von Spalten zugreifen. Wenn Sie eine Tabelle mit Kundendaten, die viele Spalten enthält anzeigen, ist es z. B. hilfreich für Sie den Namen des Kunden jederzeit während andere Spalten außerhalb des sichtbaren Bereichs Scrollen anzeigen.  
  
 Zu diesem Zweck können Sie Spalten im Steuerelement fixieren. Wenn Sie eine Spalte fixieren, werden automatisch auch alle Spalten links daneben (bzw. rechts daneben in von rechts nach links geschriebenen Sprachen) fixiert. Fixierte Spalten behalten ihre Position bei, während alle anderen Spalten bei einem Bildlauf mitwandern. Wenn die Neuanordnung von Spalten aktiviert ist, werden die fixierten Spalten als eine Gruppe im Unterschied zu den nicht fixierten Spalten behandelt. Benutzer können Spalten in beiden Gruppen neu positionieren, jedoch keine Spalte aus einer Gruppe in die andere verschieben.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-freeze-a-column-using-the-designer"></a>So fixieren Sie eine Spalte, die mithilfe des Designers  
  
1.  Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) auf der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Spalten bearbeiten**.  
  
2.  Wählen Sie eine Spalte aus der **Selected Columns** Liste.  
  
3.  In der **Spalteneigenschaften** Raster legen die <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> Eigenschaft `true`.  
  
    > [!NOTE]
    >  Sie können auch eine Spalte fixieren, wenn er dazu hinzufügen der **reagierende** im Feld der **Spalte hinzufügen** Dialogfeld.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [Vorgehensweise: Hinzufügen und Entfernen von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Aktivieren der Neuanordnung von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Anzeigen von Text mit rechts-nach-links in Windows Forms für die Globalisierung](https://msdn.microsoft.com/library/f0663385-2354-4c65-8676-706422283b14)
- [Vorgehensweise: Create a New Windows Forms Application Project (Vorgehensweise: Erstellen Sie ein Windows-Anwendungsprojekt)](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
