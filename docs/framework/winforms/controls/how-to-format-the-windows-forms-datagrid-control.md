---
title: 'Vorgehensweise: Formatieren des DataGrid-Steuerelements in Windows Forms'
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
ms.openlocfilehash: 99acef0a7b29228ddf0406352ff5a88b77294b00
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966668"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Vorgehensweise: Formatieren des DataGrid-Steuerelements in Windows Forms
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Das Anwenden verschiedener Farben auf verschiedene Teile eines <xref:System.Windows.Forms.DataGrid> Steuer Elements kann helfen, die Informationen leichter zu lesen und zu interpretieren. Farbe kann auf Zeilen und Spalten angewendet werden. Zeilen und Spalten können auch ausgeblendet oder nach eigenem Ermessen angezeigt werden.  
  
 Es gibt drei grundlegende Aspekte beim Formatieren des <xref:System.Windows.Forms.DataGrid> -Steuer Elements. Sie können Eigenschaften festlegen, um einen Standardstil festzulegen, in dem Daten angezeigt werden. Aus dieser Basis können Sie dann die Art und Weise anpassen, in der bestimmte Tabellen zur Laufzeit angezeigt werden. Schließlich können Sie ändern, welche Spalten im Datenraster angezeigt werden und welche Farben und andere Formatierung angezeigt werden.  
  
 Als ersten Schritt beim Formatieren eines Datenrasters können Sie die Eigenschaften von <xref:System.Windows.Forms.DataGrid> selbst festlegen. Diese Farben und Formatierungsoptionen bilden eine Basis, von der Sie abhängig von den angezeigten Datentabellen und Spalten Änderungen vornehmen können.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>So legen Sie einen Standardstil für das DataGrid-Steuerelement fest  
  
1. Legen Sie nach Bedarf die folgenden Eigenschaften fest:  
  
    |Eigenschaft|Beschreibung|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die <xref:System.Windows.Forms.DataGrid.BackColor%2A> -Eigenschaft definiert die Farbe der gerade nummerierten Zeilen des Rasters. Wenn Sie die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> -Eigenschaft auf eine andere Farbe festlegen, wird jede andere Zeile auf diese neue Farbe festgelegt (Zeilen 1, 3, 5 usw.).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der gerade nummerierten Zeilen des Rasters (Zeilen 0, 2, 4, 6 usw.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während die <xref:System.Windows.Forms.DataGrid.BackColor%2A> - <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> Eigenschaft und die-Eigenschaft die Farbe der Zeilen im Raster <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> bestimmen, bestimmt die-Eigenschaft die Farbe des Bereichs, der nicht zeilenbasiert, der nur sichtbar ist, wenn ein Raster nach unten bewegt wird, oder wenn nur wenige Zeilen in enthalten sind. Das Raster.|  
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
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Bestimmt mithilfe <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> der-Enumeration, ob die Tabellen-und Spaltennamen in der übergeordneten Zeile angezeigt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Die Standardbreite der Spalten des Rasters in Pixel. Legen Sie diese Eigenschaft fest, bevor <xref:System.Windows.Forms.DataGrid.DataSource%2A> Sie <xref:System.Windows.Forms.DataGrid.DataMember%2A> die-Eigenschaft und die-Eigenschaft zurück <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> setzen (entweder separat oder über die-Methode), oder die-Eigenschaft hat keine Auswirkung.<br /><br /> Die-Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Die Zeilenhöhe (in Pixel) der Zeilen im Raster. Legen Sie diese Eigenschaft fest, bevor <xref:System.Windows.Forms.DataGrid.DataSource%2A> Sie <xref:System.Windows.Forms.DataGrid.DataMember%2A> die-Eigenschaft und die-Eigenschaft zurück <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> setzen (entweder separat oder über die-Methode), oder die-Eigenschaft hat keine Auswirkung.<br /><br /> Die-Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Die Breite der Zeilen Header des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Hintergrundfarbe.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe.|  
  
    > [!NOTE]
    > Beachten Sie beim Anpassen der Farben von Steuerelementen, dass es möglich ist, das Steuerelement nicht zugänglich zu machen, aufgrund von schlechter Farbauswahl (z. b. rot und grün). Verwenden Sie die Farben, die auf der Palette **System Farben** verfügbar sind, um dieses Problem zu vermeiden.  
  
     Bei den folgenden Prozeduren wird davon <xref:System.Windows.Forms.DataGrid> ausgegangen, dass das Formular über ein Steuerelement an eine Datentabelle verfügt Weitere Informationen finden Sie unter [Binden des Windows Forms DataGrid-Steuer Elements an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>So legen Sie den Tabellen-und Spalten Stil einer Datentabelle Programm gesteuert fest  
  
1. Erstellen Sie einen neuen Tabellen Stil, und legen Sie seine Eigenschaften fest.  
  
2. Erstellen Sie einen Spalten Stil, und legen Sie seine Eigenschaften fest.  
  
3. Fügen Sie den Spalten Stil der Auflistung der Spalten Stile des Tabellen Stils hinzu.  
  
4. Fügen Sie den Tabellen Stil der Auflistung der Tabellen Stile des Datenrasters hinzu.  
  
5. Erstellen Sie im folgenden Beispiel eine Instanz einer neuen <xref:System.Windows.Forms.DataGridTableStyle> , und legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> zugehörige-Eigenschaft fest.  
  
6. Erstellen Sie eine neue Instanz eines **GridColumnStyle** -Elements, und legen Sie seinen **MappingName** (und andere Layout-und Anzeigeeigenschaften) fest.  
  
7. Wiederholen Sie die Schritte 2 bis 6 für jeden Spalten Stil, den Sie erstellen möchten.  
  
     Im folgenden Beispiel wird veranschaulicht, <xref:System.Windows.Forms.DataGridTextBoxColumn> wie ein erstellt wird, da ein Name in der-Spalte angezeigt werden soll. Außerdem fügen Sie den Spalten Stil <xref:System.Windows.Forms.GridColumnStylesCollection> der des Tabellen Stils hinzu, und Sie fügen den Tabellen Stil <xref:System.Windows.Forms.GridTableStylesCollection> der des Datenrasters hinzu.  
  
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
- [Vorgehensweise: Löschen oder Ausblenden von Spalten im Windows Forms DataGrid-Steuerelement](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
