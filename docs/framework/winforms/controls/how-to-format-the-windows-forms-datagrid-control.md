---
title: "Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Farben, Anwenden auf DataGrid-Steuerelemente"
  - "Spalten [Windows Forms], DataGrid-Steuerelement"
  - "Spalten [Windows Forms], Formatieren im DataGrid-Steuerelement"
  - "DataGrid-Steuerelement [Windows Forms], Standardformate"
  - "DataGrid-Steuerelement [Windows Forms], Formatierung"
  - "Formatieren [Windows Forms]"
  - "Tabellen [Windows Forms], Formatieren im DataGrid-Steuerelement"
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Durch die Anwendung verschiedener Farben auf die unterschiedlichen Teile eines <xref:System.Windows.Forms.DataGrid>\-Steuerelements können Sie die Lesbarkeit und die Verständlichkeit der darin enthaltenen Informationen verbessern.  Farben können sowohl auf Zeilen als auch auf Spalten angewendet werden.  Je nach Bedarf können Zeilen und Spalten auch ausgeblendet oder angezeigt werden.  
  
 Die Formatierung des <xref:System.Windows.Forms.DataGrid>\-Steuerelements umfasst drei grundlegende Aspekte.  Mithilfe von Eigenschaften können Sie ein Standardformat für die Datenanzeige einrichten.  Auf dieser Basis können Sie anschließend anpassen, wie bestimmte Tabellen zur Laufzeit angezeigt werden.  Schließlich können Sie auch festlegen, welche Spalten im Datenblatt angezeigt und welche Farben und Formatierungen dabei verwendet werden.  
  
 Sie können mit der Formatierung des Datenblatts beginnen, indem Sie die Eigenschaften von <xref:System.Windows.Forms.DataGrid> selbst festlegen.  Auf der Grundlage dieser Festlegungen für Farben und Formate können Sie dann je nach den angezeigten Datentabellen und \-spalten weitere Anpassungen vornehmen.  
  
### So richten Sie ein Standardformat für das DataGrid\-Steuerelement ein  
  
1.  Legen Sie die folgenden Eigenschaften fest:  
  
    |Property|Beschreibung|  
    |--------------|------------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die <xref:System.Windows.Forms.DataGrid.BackColor%2A>\-Eigenschaft legt die Farbe der Zeilen mit geraden Zeilennummern fest.  Wenn Sie für die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>\-Eigenschaft eine andere Farbe festlegen, werden alle anderen Zeilen in dieser neuen Farbe angezeigt \(Zeilen 1, 3, 5 usw.\).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der Rasterzeilen mit geraden Zeilennummern \(Zeilen 0, 2, 4, 6 usw.\).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während die <xref:System.Windows.Forms.DataGrid.BackColor%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>\-Eigenschaft die Farbe der Datenblattzeilen festlegen, bestimmt die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>\-Eigenschaft die Farbe des restlichen Bereichs ohne Zeilen, der nur sichtbar ist, wenn Sie an das untere Ende des Datenblatts wechseln oder wenn das Datenblatt nur wenige Zeilen enthält.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Das Rahmenformat des Rasters \(einer der <xref:System.Windows.Forms.BorderStyle>\-Enumerationswerte\).|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Die Hintergrundfarbe der Fensterbeschriftung des Datenblatts, die unmittelbar über dem Datenblatt angezeigt wird.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Die Schriftart, die für die Fensterbeschriftung über dem Raster verwendet wird.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Die Hintergrundfarbe der Fensterbeschriftung des Rasters.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Die zur Anzeige des im Raster enthaltenen Textes verwendete Schriftart.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Die Farbe der Schrift, in der die Daten in den Zeilen des Datenblatts angezeigt werden.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Die Farbe der Rasterzeilen im Datenblatt.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Die Art der Linien zwischen den Zellen des Rasters, d. h. einer der <xref:System.Windows.Forms.DataGridLineStyle>\-Enumerationswerte.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Die Hintergrundfarbe von Zeilen\- und Spaltenüberschriften.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Die für Spaltenüberschriften verwendete Schriftart.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Die Vordergrundfarbe der Spaltenüberschriften des Rasters, einschließlich des Spaltenüberschriftentextes und der Plus\/Minus\-Symbole \(zum Erweitern von Zeilen, wenn mehrere zugeordnete Tabellen angezeigt werden\).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Die Textfarbe aller Links innerhalb des Datenblatts, einschließlich der Links zu untergeordneten Tabellen, dem Relationsnamen usw.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|Die Hintergrundfarbe der übergeordneten Zeilen in einer untergeordneten Tabelle.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|Die Vordergrundfarbe der übergeordneten Zeilen in einer untergeordneten Tabelle.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Legt fest, ob die Tabellen\- und Spaltennamen in der übergeordneten Zeile angezeigt werden. Dazu wird die <xref:System.Windows.Forms.DataGridParentRowsLabelStyle>\-Enumeration verwendet.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Die Standardbreite der Spalten des Rasters in Pixel.  Legen Sie diese Eigenschaft fest, bevor Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft zurücksetzen \(entweder einzeln oder mit der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode\). Andernfalls kann die Eigenschaft nicht angewendet werden.<br /><br /> Für diese Eigenschaft kann kein geringerer Wert als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Die Höhe der Zeilen des Rasters in Pixel.  Legen Sie diese Eigenschaft fest, bevor Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft zurücksetzen \(entweder einzeln oder mit der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode\). Andernfalls kann die Eigenschaft nicht angewendet werden.<br /><br /> Für diese Eigenschaft kann kein geringerer Wert als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Die Breite der Zeilenüberschriften des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Diese Hintergrundfarbe wird beim Auswählen von Zeilen oder Zellen verwendet.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Diese Vordergrundfarbe wird beim Auswählen von Zeilen oder Zellen verwendet.|  
  
    > [!NOTE]
    >  Bedenken Sie beim Anpassen der Farben für die Steuerelemente, dass diese dadurch möglicherweise nicht mehr aufgerufen werden können, weil nur eine geringe Anzahl von Farben zur Auswahl steht \(beispielsweise Rot und Grün\).  Sie können dieses Problem vermeiden, indem Sie die Farben aus der Palette **Systemfarben** verwenden.  
  
     Für die nachstehenden Prozeduren wird vorausgesetzt, dass das Formular über ein an eine Datentabelle gebundenes <xref:System.Windows.Forms.DataGrid>\-Steuerelement verfügt.  Weitere Informationen dazu finden Sie unter [Binden des DataGrid\-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### So legen Sie das Tabellenformat und das Spaltenformat von Datentabellen programmgesteuert fest  
  
1.  Erstellen Sie ein neues Tabellenformat, und legen Sie dessen Eigenschaften fest.  
  
2.  Erstellen Sie ein neues Spaltenformat, und legen Sie dessen Eigenschaften fest.  
  
3.  Fügen Sie das Spaltenformat zur Spaltenformatlauflistung für das Tabellenformat hinzu.  
  
4.  Fügen Sie das Tabellenformat zur Tabellenformatauflistung für das Datenblatt hinzu.  
  
5.  Im nachstehenden Beispiel erstellen Sie eine Instanz eines neuen <xref:System.Windows.Forms.DataGridTableStyle> und legen dessen <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>\-Eigenschaft fest.  
  
6.  Erstellen Sie eine neue Instanz eines **GridColumnStyle**, und legen Sie dessen **MappingName** fest \(sowie weitere Layout\- und Anzeigeeigenschaften\).  
  
7.  Wiederholen Sie die Schritte 2 bis 6 für jedes Spaltenformat, das erstellt werden soll.  
  
     Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Forms.DataGridTextBoxColumn> erstellt wird, weil in der Spalte ein Name angezeigt werden soll.  Zusätzlich fügen Sie das Spaltenformat zur <xref:System.Windows.Forms.GridColumnStylesCollection> des Tabellenformats hinzu, das Sie wiederum zur <xref:System.Windows.Forms.GridTableStylesCollection> des Datenblatts hinzufügen.  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.GridTableStylesCollection>   
 <xref:System.Windows.Forms.GridColumnStylesCollection>   
 <xref:System.Windows.Forms.DataGrid>   
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)