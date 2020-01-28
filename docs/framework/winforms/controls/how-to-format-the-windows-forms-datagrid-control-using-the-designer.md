---
title: Formatieren des DataGrid-Steuer Elements mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
ms.openlocfilehash: 548acac0fc7724490bfe89927ec0662b3488c230
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736796"
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms mithilfe des Designers

> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Das Anwenden verschiedener Farben auf verschiedene Teile eines <xref:System.Windows.Forms.DataGrid> Steuer Elements kann dazu beitragen, die Informationen leichter zu lesen und zu interpretieren. Farbe kann auf Zeilen und Spalten angewendet werden. Zeilen und Spalten können auch ausgeblendet oder nach eigenem Ermessen angezeigt werden.

Es gibt drei grundlegende Aspekte beim Formatieren des <xref:System.Windows.Forms.DataGrid>-Steuer Elements:

- Sie können Eigenschaften festlegen, um einen Standardstil festzulegen, in dem Daten angezeigt werden.

- Aus dieser Basis können Sie dann die Art und Weise anpassen, in der bestimmte Tabellen zur Laufzeit angezeigt werden.

- Schließlich können Sie ändern, welche Spalten im Datenraster angezeigt werden und welche Farben und andere Formatierung angezeigt werden.

Als ersten Schritt beim Formatieren eines Datenrasters können Sie die Eigenschaften des <xref:System.Windows.Forms.DataGrid> selbst festlegen. Diese Farben und Formatierungsoptionen bilden eine Basis, von der Sie abhängig von den angezeigten Datentabellen und Spalten Änderungen vornehmen können.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGrid>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md). In Visual Studio 2005 ist das <xref:System.Windows.Forms.DataGrid>-Steuerelement nicht standardmäßig in der **Toolbox** . Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen von Elementen zur Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>So legen Sie einen Standardstil für das DataGrid-Steuerelement fest

1. Wählen Sie das <xref:System.Windows.Forms.DataGrid>-Steuerelement.

2. Legen Sie im **Eigenschaften** Fenster die folgenden Eigenschaften entsprechend fest.

    |Die Eigenschaften-|Beschreibung|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die `BackColor`-Eigenschaft definiert die Farbe der gerade nummerierten Zeilen im Raster. Wenn Sie die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>-Eigenschaft auf eine andere Farbe festlegen, wird jede andere Zeile auf diese neue Farbe festgelegt (Zeilen 1, 3, 5 usw.).|
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der gerade nummerierten Zeilen des Rasters (Zeilen 0, 2, 4, 6 usw.).|
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während die Eigenschaften <xref:System.Windows.Forms.DataGrid.BackColor%2A> und <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> die Farbe der Zeilen im Raster bestimmen, bestimmt die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>-Eigenschaft die Farbe des Bereichs außerhalb des Zeilen Bereichs, der nur sichtbar ist, wenn ein Raster nach unten bewegt wird oder nur einige Zeilen im Raster enthalten sind.|
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Die Rahmenart des Rasters, einer der <xref:System.Windows.Forms.BorderStyle> Enumerationswerte.|
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Die Hintergrundfarbe der Fenster Beschriftung des Rasters, die unmittelbar oberhalb des Rasters angezeigt wird.|
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Die Schriftart der Beschriftung am oberen Rand des Rasters.|
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Die Hintergrundfarbe der Fenster Beschriftung des Datenblatts.|
    |<xref:System.Windows.Forms.Control.Font%2A>|Die Schriftart, die verwendet wird, um den Text im Raster anzuzeigen.|
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Die Farbe der Schriftart, die von den Daten in den Zeilen des Datenrasters angezeigt wird.|
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Die Farbe der Rasterlinien des Datenrasters.|
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Der Stil der Zeilen, die die Zellen des Rasters trennen, einer der <xref:System.Windows.Forms.DataGridLineStyle> Enumerationswerte.|
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Die Hintergrundfarbe der Zeilen-und Spaltenheader.|
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Die Schriftart, die für die Spaltenheader verwendet wird.|
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Die Vordergrundfarbe der Spaltenheader des Rasters, einschließlich des Spaltenheader Texts und des Plus Zeichens (+) und Minuszeichen (-), die Zeilen erweitern und reduzieren, wenn mehrere verknüpfte Tabellen angezeigt werden.|
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Die Textfarbe aller Links im Datenraster, einschließlich Links zu untergeordneten Tabellen, Beziehungs Name usw.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In einer untergeordneten Tabelle ist dies die Hintergrundfarbe der übergeordneten Zeilen.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In einer untergeordneten Tabelle ist dies die Vordergrundfarbe der übergeordneten Zeilen.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Bestimmt mithilfe der <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> Enumeration, ob die Tabellen-und Spaltennamen in der übergeordneten Zeile angezeigt werden.|
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Die Standardbreite der Spalten des Rasters in Pixel. Legen Sie diese Eigenschaft fest, bevor Sie die Eigenschaften <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> zurücksetzen (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode), oder die Eigenschaft hat keine Auswirkungen.<br /><br /> Die-Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Die Zeilenhöhe (in Pixel) der Zeilen im Raster. Legen Sie diese Eigenschaft fest, bevor Sie die Eigenschaften <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> zurücksetzen (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode), oder die Eigenschaft hat keine Auswirkungen.<br /><br /> Die-Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Die Breite der Zeilen Header des Rasters.|
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Hintergrundfarbe.|
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe.|

    > [!NOTE]
    > Wenn Sie die Farben der Steuerelemente anpassen, ist es möglich, das Steuerelement aufgrund von schlechter Farbauswahl (z. b. rot und grün) nicht zugänglich zu machen. Verwenden Sie die Farben, die auf der Palette **System Farben** verfügbar sind, um dieses Problem zu vermeiden.

    Das folgende Verfahren erfordert ein <xref:System.Windows.Forms.DataGrid>-Steuerelement, das an eine Datentabelle gebunden ist. Weitere Informationen finden Sie unter Gewusst [wie: Binden des Windows Forms DataGrid-Steuer Elements an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>So legen Sie den Tabellen-und Spalten Stil einer Datentabelle zur Entwurfszeit fest

1. Wählen Sie das <xref:System.Windows.Forms.DataGrid>-Steuerelement auf dem Formular aus.

2. Wählen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.Windows.Forms.DataGrid.TableStyles%2A> aus, und klicken Sie auf die Schaltfläche mit den Auslassungs **Punkten (![** der Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)).

3. Klicken Sie im Dialogfeld **DataGridTableStyle** -Auflistungs-Editor auf **Hinzufügen** , um der Sammlung einen Tabellen Stil hinzuzufügen.

     Mit dem **DataGridTableStyle**-Auflistungs-Editor können Sie Tabellen Stile hinzufügen und entfernen, Anzeige-und Layouteigenschaften festlegen und den Namen der Zuordnung für die Tabellen Stile festlegen.

4. Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>-Eigenschaft auf den Namen der Zuordnung für die einzelnen Tabellen Stile fest.

     Der Zuordnungsname wird verwendet, um anzugeben, welcher Tabellen Stil mit welcher Tabelle verwendet werden soll.

5. Wählen Sie im **DataGridTableStyle**-Auflistungs-Editor die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>-Eigenschaft aus, und klicken Sie auf die Schaltfläche mit den Auslassungs Zeichen![(...) im Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)).

6. Fügen Sie im Dialogfeld **DataGridColumnStyle** -Auflistungs-Editor dem Tabellenformat, das Sie erstellt haben, Spalten Formate hinzu.

     Mit dem **DataGridColumnStyle**-Auflistungs-Editor können Sie Spalten Stile hinzufügen und entfernen, Anzeige-und Layouteigenschaften festlegen und den Zuordnungsnamen und die Formatierungs Zeichenfolgen für die Datenspalten festlegen.

    > [!NOTE]
    > Weitere Informationen zum Formatieren von Zeichen folgen finden Sie unter [Formatieren von Typen](../../../standard/base-types/formatting-types.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
