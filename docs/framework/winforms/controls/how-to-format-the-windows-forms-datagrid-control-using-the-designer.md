---
title: 'Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms mithilfe des Designers'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b47b0c2353764f5452c2bb3f6ca37af11d6d904c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Verschiedene Farben für verschiedene Teile des Anwenden einer <xref:System.Windows.Forms.DataGrid> bestimmen können, stellen die Informationen in diesem einfacher zu lesen und zu interpretieren. Farbe kann in Zeilen und Spalten angewendet werden. Zeilen und Spalten können auch ausgeblendet oder angezeigt, die in Ihrem eigenen Ermessen.  
  
 Es gibt drei grundlegende Aspekte der Formatierung der <xref:System.Windows.Forms.DataGrid> Steuerelement:  
  
-   Sie können festlegen, dass Eigenschaften herstellen ein Standardformat, in dem Daten angezeigt werden.  
  
-   Auf dieser Basis können Sie dann die Möglichkeit anpassen, die bestimmte Tabellen zur Laufzeit angezeigt werden.  
  
-   Schließlich können Sie ändern, welche Spalten im Datenraster sowie die Farben angezeigt werden, und andere Formatierung aus, die angezeigt wird.  
  
 Als ersten Schritt bei der Formatierung eines Datenrasters können Sie die Eigenschaften der Festlegen der <xref:System.Windows.Forms.DataGrid> selbst. Diese Optionen Farbe und Format bilden eine Basis, von der Sie dann ändert sich je nach den Datentabellen und Spalten angezeigt, können.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.DataGrid> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> Steuerelement befindet sich nicht in der **Toolbox** standardmäßig. Weitere Informationen finden Sie unter [wie: Hinzufügen von Elementen zur Toolbox](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Herstellen einer Standardformat für das DataGrid-Steuerelement  
  
1.  Wählen Sie das <xref:System.Windows.Forms.DataGrid>-Steuerelement.  
  
2.  In der **Eigenschaften** die folgenden Eigenschaften fest, nach Bedarf.  
  
    |Eigenschaft|Beschreibung|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die `BackColor` Eigenschaft definiert die Farbe der geraden Zeilen des Rasters. Beim Festlegen der <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> -Eigenschaft auf eine andere Farbe, jeder anderen Zeile in dieser neuen Farbe festgelegt ist (Zeilen 1, 3, 5 und So weiter).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der geraden Zeilen des Rasters (Zeilen 0, 2, 4, 6 usw.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während der <xref:System.Windows.Forms.DataGrid.BackColor%2A> und <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> Eigenschaften bestimmt die Farbe der Zeilen im Raster die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> Eigenschaft bestimmt die Farbe des Bereichs außerhalb der Zeile, der ist nur sichtbar, wenn das Raster unten Bildlauf durchgeführt wird oder wenn nur wenige Zeilen sind im Raster enthalten.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Die Rahmenart des Datenblatts, eines der <xref:System.Windows.Forms.BorderStyle> Enumerationswerte.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Farbe des Hintergrunds des Datenblatts fensterbeschriftung unmittelbar oberhalb des Rasters angezeigt wird.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Die Schriftart der Beschriftung oben im Raster.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Die Hintergrundfarbe der Beschriftung des Datenblatts.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Die Schriftart verwendet, um den Text im Raster anzuzeigen.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Die Farbe der Schriftart an, durch die Daten in den Zeilen des Datenblatts angezeigt.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Die Farbe der Datenblattlinien des Datenblatts.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Der Stil der Linien zwischen den Zellen des Rasters, eines der <xref:System.Windows.Forms.DataGridLineStyle> Enumerationswerte.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Die Hintergrundfarbe von Zeilen- und Spaltenüberschriften.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Die für die Spaltenüberschriften verwendete Schriftart.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Die Vordergrundfarbe der Spaltenköpfe des Datenblatts, einschließlich der Spaltenkopftexte und das Pluszeichen (+) und Minuszeichen (-) Symbole zum Erweitern und Reduzieren von Zeilen, wenn mehrere Tabellen zusammengehörige werden angezeigt.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Die Farbe des Texts für alle Verknüpfungen im Datenraster, einschließlich Links zu untergeordneten Tabellen, die Namen der Geschäftsbeziehung usw.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In einer untergeordneten Tabelle ist dies die Hintergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In einer untergeordneten Tabelle ist dies die Vordergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Bestimmt, ob die Tabellen- und Spaltennamen in der übergeordneten Zeile, von der angezeigt werden die <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> Enumeration.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Die Standardbreite der Spalten des Rasters in Pixel. Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder einzeln oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkung.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Die Zeilenhöhe (in Pixel) von Zeilen im Raster. Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder einzeln oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkung.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Die Breite der Zeilenheader des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Farbe des Hintergrunds.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe.|  
  
    > [!NOTE]
    >  Wenn Sie die Farben der Steuerelemente anpassen, ist es möglich, das Steuerelement kann nicht zugegriffen werden aufgrund einer schlechten Farbauswahl (z. B. "Rot" und "Grün") ist. Verwenden Sie die Farben auf die **Systemfarben** Palette, um dieses Problem zu vermeiden.  
  
     Das folgende Verfahren erfordert eine <xref:System.Windows.Forms.DataGrid> -Steuerelements an eine Datentabelle gebunden. Weitere Informationen finden Sie unter [Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>Den Tabellen und Spalten einer Datentabelle zur Entwurfszeit fest  
  
1.  Wählen Sie die <xref:System.Windows.Forms.DataGrid> Steuerelement auf dem Formular.  
  
2.  In der **Eigenschaften** wählen die <xref:System.Windows.Forms.DataGrid.TableStyles%2A> -Eigenschaft, und klicken Sie auf die **Auslassungszeichen** (![von VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " VbEllipsesButton")) Schaltfläche.  
  
3.  In der **DataGridTableStyle Auflistungs-Editor** (Dialogfeld), klicken Sie auf **hinzufügen** ein Tabellenformat in der Auflistung hinzu.  
  
     Mit der **DataGridTableStyle Auflistungs-Editor**, können Sie hinzufügen und Tabellenformate entfernen, Set-Anzeige und Layout-Eigenschaften und Set benennen Sie die Zuordnung für die Tabelle Stile.  
  
4.  Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> -Eigenschaft auf den Zuordnungsnamen für jede Tabellenformat.  
  
     Der Zuordnungsname wird verwendet, um anzugeben, welche Tabellenformat für die Tabelle verwendet werden soll.  
  
5.  In der **DataGridTableStyle Auflistungs-Editor**, wählen die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Eigenschaft, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton ")).  
  
6.  In der **DataGridColumnStyle Auflistungs-Editor** Dialogfeld fügen Spaltenformate den Tabelle-Stil, die Sie erstellt haben.  
  
     Mit der **DataGridColumnStyle Auflistungs-Editor**, Sie können hinzufügen und entfernen Sie Spaltenformate, legen Sie Eigenschaften anzeigen und Layout und legen Sie den Zuordnungsnamen und Formatieren von Zeichenfolgen für die Daten Spalten.  
  
    > [!NOTE]
    >  Weitere Informationen zum Formatieren von Zeichenfolgen finden Sie unter [Formatierung von Typen](../../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
