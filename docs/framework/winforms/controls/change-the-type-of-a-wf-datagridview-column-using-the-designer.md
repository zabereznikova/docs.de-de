---
title: 'Gewusst wie: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: b5d395575ac486307625fbdf2f236b6a588cc3ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Gewusst wie: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers
In einigen Fällen wird der Datentyp einer Spalte ändern möchten, die bereits zu einem Windows Forms hinzugefügt wurde <xref:System.Windows.Forms.DataGridView> Steuerelement. Beispielsweise empfiehlt es sich um die Typen von einige der Spalten zu ändern, die automatisch generiert werden, wenn Sie das Steuerelement an eine Datenquelle binden. Dies ist hilfreich, wenn die Tabelle, die Sie anzeigen, Spalten mit Fremdschlüsseln in Zeilen in einer verknüpften Tabelle verfügt. In diesem Fall empfiehlt es sich um Textspalten Feld zu ersetzen, die diese Fremdschlüssel Spalten mit Kombinationsfeldern angezeigt, in denen sinnvolle Werten aus der verknüpften Tabelle angezeigt.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a>So ändern Sie den Datentyp einer Spalte mithilfe des Designers  
  
1.  Klicken Sie auf das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Spalten bearbeiten**.  
  
2.  Wählen Sie eine Spalte aus der **ausgewählte Spalten** Liste.  
  
3.  In der **Spalteneigenschaften** Raster Festlegen der `ColumnType` Eigenschaft in den neuen Spaltentyp.  
  
    > [!NOTE]
    >  Die `ColumnType` -Eigenschaft ist nur zur Entwurf, der die Klasse, die den Spaltentyp darstellt angibt. Es ist keine tatsächliche Eigenschaft in einer Spaltenklasse definiert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
