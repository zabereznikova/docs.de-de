---
title: 'Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
ms.openlocfilehash: e0d703e16ab89243c7f7cf57dc858a0a3889a590
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389020"
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Verschiedene Farben zu verschiedenen Teilen der Anwendung eine <xref:System.Windows.Forms.DataGrid> steuern können, stellen die Informationen in der er leichter zu lesen und interpretieren. Farbe kann in Zeilen und Spalten angewendet werden. Zeilen und Spalten können auch ausgeblendet oder angezeigt, die in Ihrem eigenen Ermessen.  
  
 Es gibt drei grundlegende Aspekte der Formatierung der <xref:System.Windows.Forms.DataGrid> Steuerelement:  
  
-   Sie können festlegen, dass Eigenschaften zu, um einen Standardstil herzustellen, in dem Daten angezeigt werden.  
  
-   Auf dieser Basis können Sie die Möglichkeit, die bestimmte Tabellen zur Laufzeit angezeigt werden, klicken Sie dann anpassen.  
  
-   Abschließend können Sie ändern, welche Spalten im Raster als auch die Farben angezeigt werden, und andere, die Formatierung wird angezeigt.  
  
 Als ersten Schritt bei der Formatierung ein Datenraster, können Sie festlegen, der Eigenschaften der <xref:System.Windows.Forms.DataGrid> selbst. Diese Farbe und Format-Auswahl bilden eine Basis, die aus der Sie dann abhängig von der Tabellen und Spalten angezeigt, können Änderungen vornehmen.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGrid> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> Steuerelement befindet sich nicht in der **Toolbox** standardmäßig. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Elementen zur Toolbox](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Herstellen einen Standardstil für das DataGrid-Steuerelement  
  
1.  Wählen Sie das <xref:System.Windows.Forms.DataGrid>-Steuerelement.  
  
2.  In der **Eigenschaften** legen die folgenden Eigenschaften, nach Bedarf.  
  
    |Eigenschaft|Beschreibung|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die `BackColor` Eigenschaft definiert die Farbe der geraden Zeilen des Rasters. Beim Festlegen der <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> -Eigenschaft auf eine andere Farbe, jeder anderen Zeile in dieser neuen Farbe festgelegt ist (Zeilen, 1, 3, 5 und So weiter).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der geraden Zeilen des Rasters (Zeilen 0, 2, 4, 6 und So weiter).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während der <xref:System.Windows.Forms.DataGrid.BackColor%2A> und <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> Eigenschaften bestimmt die Farbe der Zeilen im Raster die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> -Eigenschaft bestimmt die Farbe des Bereichs außerhalb der Zeile, der ist nur sichtbar, wenn das Raster unten ein Bildlauf durchgeführt wird oder wenn nur wenige Zeilen sind im Raster enthalten.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Die Rahmenart des Datenblatts, eines der <xref:System.Windows.Forms.BorderStyle> -Enumerationswerte fest.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Die Hintergrundfarbe des Datenblatts fensterbeschriftung unmittelbar oberhalb des Rasters angezeigt wird.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Die Schriftart der Beschriftung am oberen Rand des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Die Hintergrundfarbe der fensterbeschriftung des Datenblatts.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Die Schriftart verwendet, um den Text im Raster anzuzeigen.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Die Farbe der Schriftart, die von den Daten in den Zeilen im Datenraster angezeigt werden soll.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Die Farbe der Datenblattlinien im Datenraster.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Der Stil der Linien zwischen den Zellen des Rasters, eines der <xref:System.Windows.Forms.DataGridLineStyle> -Enumerationswerte fest.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Die Hintergrundfarbe der Zeilen- und Spaltenüberschriften.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Die Schriftart für Spaltenköpfe verwendet.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Die Vordergrundfarbe der Spaltenköpfe des Datenblatts, einschließlich des Texts der Spaltenüberschrift und das Pluszeichen (+) und Minuszeichen (-) Symbole zum Erweitern und Reduzieren von Zeilen, wenn mehrere Tabellen zusammengehörige werden angezeigt.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Die Farbe des Texts, der alle Links im Datenraster, einschließlich Links zu untergeordneten Tabellen, Name der Beziehung und So weiter.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In einer untergeordneten Tabelle ist dies die Hintergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In einer untergeordneten Tabelle ist dies die Vordergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Bestimmt, ob die Tabellen- und Spaltennamen in der übergeordneten Zeile, von angezeigt werden der <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> Enumeration.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Die Standardbreite der Spalten des Rasters in Pixel. Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkungen.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Die Zeilenhöhe (in Pixel) von Zeilen im Raster. Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkungen.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Die Breite der Zeilenheader des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Farbe des Hintergrunds.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe darstellt.|  
  
    > [!NOTE]
    >  Wenn Sie die Farben der Steuerelemente anpassen, ist es möglich, das Steuerelement aufgrund einer schlechten Farbauswahl (z. B. "Red" und "Grün") nicht mehr verfügbar ist. Verwenden Sie die Farben, die auf die **Systemfarben** Palette, um dieses Problem zu vermeiden.  
  
     Das folgende Verfahren erfordert eine <xref:System.Windows.Forms.DataGrid> -Steuerelement an eine Datentabelle gebunden. Weitere Informationen finden Sie unter [Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>Den Tabellen und Spalten einer Datentabelle zur Entwurfszeit fest  
  
1.  Wählen Sie die <xref:System.Windows.Forms.DataGrid> Steuerelement auf Ihrem Formular.  
  
2.  In der **Eigenschaften** wählen Sie im Fenster der <xref:System.Windows.Forms.DataGrid.TableStyles%2A> -Eigenschaft, und klicken Sie auf die **Auslassungspunkte** (![VisualStudioEllipsesButton-bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png " VbEllipsesButton")) Schaltfläche.  
  
3.  In der **DataGridTableStyle Auflistungs-Editor** Dialogfeld klicken Sie auf **hinzufügen** ein Tabellenformat in der Auflistung hinzu.  
  
     Mit der **DataGridTableStyle Auflistungs-Editor**, können Sie hinzufügen und entfernen Tabellenformate, Set-Anzeige und Layout-Eigenschaften und Set benennen Sie die Zuordnung für die Tabellenformate.  
  
4.  Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> -Eigenschaft auf den Zuordnungsnamen für jede Tabellenformat.  
  
     Der Zuordnungsname wird verwendet, um anzugeben, welche das Format der Tabelle verwendet werden soll.  
  
5.  In der **DataGridTableStyle Auflistungs-Editor**, wählen die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Eigenschaft, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton ")).  
  
6.  In der **DataGridColumnStyle Auflistungs-Editor** Dialogfeld Feld, Spaltenformate hinzufügen, um das Tabellenformat, das Sie erstellt haben.  
  
     Mit der **DataGridColumnStyle Auflistungs-Editor**, Sie können hinzufügen und entfernen Sie Spaltenformate, legen Sie Eigenschaften für Anzeige- und Layoutinformationen und legen Sie den Zuordnungsnamen und Formatierung von Zeichenfolgen für die Daten Spalten.  
  
    > [!NOTE]
    >  Weitere Informationen zur Formatierung von Zeichenfolgen finden Sie unter [Formatierung von Typen](../../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
