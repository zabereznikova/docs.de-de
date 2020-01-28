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
ms.openlocfilehash: 30342a89f3176255fa7217ccbbbd91c166ff7f35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732958"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Das Anwenden verschiedener Farben auf verschiedene Teile eines <xref:System.Windows.Forms.DataGrid> Steuer Elements kann dazu beitragen, die Informationen leichter zu lesen und zu interpretieren. Farbe kann auf Zeilen und Spalten angewendet werden. Zeilen und Spalten können auch ausgeblendet oder nach eigenem Ermessen angezeigt werden.  
  
 Es gibt drei grundlegende Aspekte beim Formatieren des <xref:System.Windows.Forms.DataGrid> Steuer Elements. Sie können Eigenschaften festlegen, um einen Standardstil festzulegen, in dem Daten angezeigt werden. Aus dieser Basis können Sie dann die Art und Weise anpassen, in der bestimmte Tabellen zur Laufzeit angezeigt werden. Schließlich können Sie ändern, welche Spalten im Datenraster angezeigt werden und welche Farben und andere Formatierung angezeigt werden.  
  
 Als ersten Schritt beim Formatieren eines Datenrasters können Sie die Eigenschaften des <xref:System.Windows.Forms.DataGrid> selbst festlegen. Diese Farben und Formatierungsoptionen bilden eine Basis, von der Sie abhängig von den angezeigten Datentabellen und Spalten Änderungen vornehmen können.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>So legen Sie einen Standardstil für das DataGrid-Steuerelement fest  
  
1. Legen Sie nach Bedarf die folgenden Eigenschaften fest:  
  
    |Die Eigenschaften-|Beschreibung|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die <xref:System.Windows.Forms.DataGrid.BackColor%2A>-Eigenschaft definiert die Farbe der gerade nummerierten Zeilen im Raster. Wenn Sie die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>-Eigenschaft auf eine andere Farbe festlegen, wird jede andere Zeile auf diese neue Farbe festgelegt (Zeilen 1, 3, 5 usw.).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der gerade nummerierten Zeilen des Rasters (Zeilen 0, 2, 4, 6 usw.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während die Eigenschaften <xref:System.Windows.Forms.DataGrid.BackColor%2A> und <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> die Farbe der Zeilen im Raster bestimmen, bestimmt die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>-Eigenschaft die Farbe des nicht Zeilen Bereichs, der nur sichtbar ist, wenn ein Raster nach unten bewegt wird oder nur einige Zeilen im Raster enthalten sind.|  
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
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Die Vordergrundfarbe der Spaltenheader des Rasters, einschließlich des Spaltenheader Texts und der Plus/Minus-Symbole (zum Erweitern von Zeilen, wenn mehrere verknüpfte Tabellen angezeigt werden).|  
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
    > Beachten Sie beim Anpassen der Farben von Steuerelementen, dass es möglich ist, das Steuerelement nicht zugänglich zu machen, aufgrund von schlechter Farbauswahl (z. b. rot und grün). Verwenden Sie die Farben, die auf der Palette **System Farben** verfügbar sind, um dieses Problem zu vermeiden.  
  
     Bei den folgenden Prozeduren wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.DataGrid>-Steuerelement an eine Datentabelle Weitere Informationen finden Sie unter [Binden des Windows Forms DataGrid-Steuer Elements an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>So legen Sie den Tabellen-und Spalten Stil einer Datentabelle Programm gesteuert fest  
  
1. Erstellen Sie einen neuen Tabellen Stil, und legen Sie seine Eigenschaften fest.  
  
2. Erstellen Sie einen Spalten Stil, und legen Sie seine Eigenschaften fest.  
  
3. Fügen Sie den Spalten Stil der Auflistung der Spalten Stile des Tabellen Stils hinzu.  
  
4. Fügen Sie den Tabellen Stil der Auflistung der Tabellen Stile des Datenrasters hinzu.  
  
5. Erstellen Sie im folgenden Beispiel eine Instanz eines neuen <xref:System.Windows.Forms.DataGridTableStyle>, und legen Sie dessen <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>-Eigenschaft fest.  
  
6. Erstellen Sie eine neue Instanz eines **GridColumnStyle** -Elements, und legen Sie seinen **MappingName** (und andere Layout-und Anzeigeeigenschaften) fest.  
  
7. Wiederholen Sie die Schritte 2 bis 6 für jeden Spalten Stil, den Sie erstellen möchten.  
  
     Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.DataGridTextBoxColumn> erstellt wird, da ein Name in der-Spalte angezeigt werden soll. Außerdem fügen Sie dem <xref:System.Windows.Forms.GridColumnStylesCollection> des Tabellen Stils den Spalten Stil hinzu, und Sie fügen den Tabellen Stil der <xref:System.Windows.Forms.GridTableStylesCollection> des Datenrasters hinzu.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
