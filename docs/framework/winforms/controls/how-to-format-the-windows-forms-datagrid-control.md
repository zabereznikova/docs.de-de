---
title: DataGrid-Steuerelement formatieren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182139"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Das Anwenden unterschiedlicher Farben <xref:System.Windows.Forms.DataGrid> auf verschiedene Teile eines Steuerelements kann dazu beitragen, die darin enthaltenen Informationen leichter lesbar und zu interpretieren. Farbe kann auf Zeilen und Spalten angewendet werden. Zeilen und Spalten können auch nach Eigenem Ermessen ausgeblendet oder angezeigt werden.  
  
 Es gibt drei grundlegende <xref:System.Windows.Forms.DataGrid> Aspekte der Formatierung des Steuerelements. Sie können Eigenschaften festlegen, um einen Standardstil festzulegen, in dem Daten angezeigt werden. Von dieser Basis aus können Sie dann die Art und Weise anpassen, wie bestimmte Tabellen zur Laufzeit angezeigt werden. Schließlich können Sie ändern, welche Spalten im Datenraster angezeigt werden, sowie die angezeigten Farben und andere Formatierungen.  
  
 Als ersten Schritt beim Formatieren eines Datenrasters <xref:System.Windows.Forms.DataGrid> können Sie die Eigenschaften der selbst festlegen. Diese Farb- und Formatauswahlen bilden eine Basis, von der aus Sie dann Änderungen vornehmen können, abhängig von den angezeigten Datentabellen und Spalten.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>So legen Sie einen Standardstil für das DataGrid-Steuerelement fest  
  
1. Legen Sie die folgenden Eigenschaften entsprechend fest:  
  
    |Eigenschaft|Beschreibung|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die <xref:System.Windows.Forms.DataGrid.BackColor%2A> Eigenschaft definiert die Farbe der geraden Zeilen des Rasters. Wenn Sie <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> die Eigenschaft auf eine andere Farbe festlegen, wird jede zweite Zeile auf diese neue Farbe festgelegt (Zeilen 1, 3, 5 usw.).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der geraden Zeilen des Rasters (Zeilen 0, 2, 4, 6 usw.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während <xref:System.Windows.Forms.DataGrid.BackColor%2A> die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> und Eigenschaften die Farbe von <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> Zeilen im Raster bestimmen, bestimmt die Eigenschaft die Farbe des Nicht-Zeilenbereichs, der nur sichtbar ist, wenn das Raster nach unten gescrollt wird oder wenn nur wenige Zeilen im Raster enthalten sind.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Der Rahmenstil des Rasters, <xref:System.Windows.Forms.BorderStyle> einer der Enumerationswerte.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Die Hintergrundfarbe der Fensterbeschriftung des Rasters, die direkt über dem Raster angezeigt wird.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Die Schriftart der Beschriftung am oberen Rand des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Die Hintergrundfarbe der Fensterbeschriftung des Rasters.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Die Schriftart, die zum Anzeigen des Texts im Raster verwendet wird.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Die Farbe der Schriftart, die von den Daten in den Zeilen des Datenrasters angezeigt wird.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Die Farbe der Rasterlinien des Datenrasters.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Der Stil der Linien, die die Zellen des <xref:System.Windows.Forms.DataGridLineStyle> Rasters trennen, einer der Enumerationswerte.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Die Hintergrundfarbe von Zeilen- und Spaltenüberschriften.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Die Schriftart, die für die Spaltenüberschriften verwendet wird.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Die Vordergrundfarbe der Spaltenüberschriften des Rasters, einschließlich des Spaltenkopfzeilentexts und der Plus/Minus-Glyphen (zum Erweitern von Zeilen, wenn mehrere verknüpfte Tabellen angezeigt werden).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Die Farbe des Textes aller Verknüpfungen im Datenraster, einschließlich Verknüpfungen zu untergeordneten Tabellen, dem Beziehungsnamen usw.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In einer untergeordneten Tabelle ist dies die Hintergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In einer untergeordneten Tabelle ist dies die Vordergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Bestimmt, ob die Tabellen- und Spaltennamen in der <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> übergeordneten Zeile anhand der Enumeration angezeigt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Die Standardbreite der Spalten des Rasters in Pixel. Legen Sie diese Eigenschaft <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> und -eigenschaften (entweder separat oder über die Methode) fest, da die Eigenschaft keine Auswirkungen hat.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Die Zeilenhöhe (in Pixel) von Zeilen im Raster. Legen Sie diese Eigenschaft <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> und -eigenschaften (entweder separat oder über die Methode) fest, da die Eigenschaft keine Auswirkungen hat.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Die Breite der Zeilenüberschriften des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Hintergrundfarbe.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe.|  
  
    > [!NOTE]
    > Beachten Sie beim Anpassen der Farben von Steuerelementen, dass es möglich ist, das Steuerelement aufgrund einer schlechten Farbauswahl (z. B. Rot und Grün) unzugänglich zu machen. Verwenden Sie die Farben, die in der Palette **"Systemfarben"** verfügbar sind, um dieses Problem zu vermeiden.  
  
     Die folgenden Verfahren gehen <xref:System.Windows.Forms.DataGrid> davon aus, dass das Formular über ein Steuerelement verfügt, das an eine Datentabelle gebunden ist. Weitere Informationen finden Sie unter [Binden des Windows Forms DataGrid-Steuerelements an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>So legen Sie den Tabellen- und Spaltenstil einer Datentabelle programmgesteuert fest  
  
1. Erstellen Sie einen neuen Tabellenstil, und legen Sie dessen Eigenschaften fest.  
  
2. Erstellen Sie einen Spaltenstil, und legen Sie dessen Eigenschaften fest.  
  
3. Fügen Sie den Spaltenstil der Spaltenstilsammlung des Tabellenstils hinzu.  
  
4. Fügen Sie den Tabellenstil der Tabellenstilsammlung des Datenrasters hinzu.  
  
5. Erstellen Sie im folgenden Beispiel eine <xref:System.Windows.Forms.DataGridTableStyle> Instanz <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> einer neuen Instanz, und legen Sie ihre Eigenschaft fest.  
  
6. Erstellen Sie eine neue Instanz eines **GridColumnStyle,** und legen Sie den **MappingName** (und einige andere Layout- und Anzeigeeigenschaften) fest.  
  
7. Wiederholen Sie die Schritte 2 bis 6 für jeden Spaltenstil, den Sie erstellen möchten.  
  
     Das folgende Beispiel veranschaulicht, wie ein <xref:System.Windows.Forms.DataGridTextBoxColumn> erstellt wird, da ein Name in der Spalte angezeigt werden soll. Darüber hinaus fügen Sie den <xref:System.Windows.Forms.GridColumnStylesCollection> Spaltenstil zum Tabellenformat und den <xref:System.Windows.Forms.GridTableStylesCollection> Tabellenstil zum Datenraster hinzu.  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName
       ' to the name of a DataColumn in the DataTable.
       ' Set the HeaderText and Width properties.
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to
       ' the GridTableStylesCollection.
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName
       // to the name of a DataColumn in the DataTable.
       // Set the HeaderText and Width properties.
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to
       // the GridTableStylesCollection.
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName
          // to the name of a DataColumn in the DataTable.
          // Set the HeaderText and Width properties.
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to
          // the GridTableStylesCollection.
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
