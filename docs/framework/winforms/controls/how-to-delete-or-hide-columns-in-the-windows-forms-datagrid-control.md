---
title: "Gewusst wie: L&#246;schen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Spalten [Windows Forms], Löschen in Datenblättern"
  - "Spalten [Windows Forms], Ausblenden"
  - "Datenblätter, Löschen von Spalten"
  - "Datenblätter, Ausblenden von Spalten"
  - "DataGrid-Steuerelement [Windows Forms], Löschen von Spalten"
  - "DataGrid-Steuerelement [Windows Forms], Ausblenden von Spalten"
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: L&#246;schen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows&#160;Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Sie können im <xref:System.Windows.Forms.DataGrid>\-Steuerelement in Windows Forms Spalten programmgesteuert löschen oder ausblenden, indem Sie die Eigenschaften und Methoden des <xref:System.Windows.Forms.GridColumnStylesCollection>\-Objekts und des <xref:System.Windows.Forms.DataGridColumnStyle>\-Objekts \(Member der <xref:System.Windows.Forms.DataGridTableStyle>\-Klasse\) verwenden.  
  
 Die gelöschten oder ausgeblendeten Spalten sind in der Datenquelle, mit der das Raster verbunden ist, weiterhin vorhanden und können programmgesteuert aufgerufen werden.  Die Spalten sind im Datenblatt lediglich nicht mehr sichtbar.  
  
> [!NOTE]
>  Wenn die Anwendung nicht auf bestimmte Datenspalten zugreift und diese nicht im Datenblatt angezeigt werden sollen, ist es in der Regel nicht unbedingt erforderlich, sie in der Datenquelle an erster Stelle hinzuzufügen.  
  
### So löschen Sie programmgesteuert eine Spalte aus dem datengebundenen Steuerelement \(DataGrid\)  
  
1.  Deklarieren Sie im Deklarationsbereich des Formulars eine neue Instanz der <xref:System.Windows.Forms.DataGridTableStyle>\-Klasse.  
  
2.  Legen Sie für die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=fullName>\-Eigenschaft die Tabelle in der Datenquelle fest, auf die Sie das Format anwenden möchten.  Das folgende Beispiel verwendet die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=fullName>\-Eigenschaft, wobei davon ausgegangen wird, dass diese bereits festgelegt wurde.  
  
3.  Fügen Sie der Tabellenformatauflistung des Datenblatts das neue <xref:System.Windows.Forms.DataGridTableStyle>\-Objekt hinzu.  
  
4.  Rufen Sie zum Festlegen des Spaltenindexes der zu löschenden Spalte die <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A>\-Methode der <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>\-Auflistung von <xref:System.Windows.Forms.DataGrid> auf.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### So blenden Sie programmgesteuert Spalten aus dem DataGrid aus  
  
1.  Deklarieren Sie im Deklarationsbereich des Formulars eine neue Instanz der <xref:System.Windows.Forms.DataGridTableStyle>\-Klasse.  
  
2.  Legen Sie für die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>\-Eigenschaft von <xref:System.Windows.Forms.DataGridTableStyle> die Tabelle in der Datenquelle fest, auf die Sie das Format anwenden möchten.  Das folgende Codebeispiel verwendet die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=fullName>\-Eigenschaft, wobei davon ausgegangen wird, dass diese bereits festgelegt wurde.  
  
3.  Fügen Sie der Tabellenformatauflistung des Datenblatts das neue <xref:System.Windows.Forms.DataGridTableStyle>\-Objekt hinzu.  
  
4.  Blenden Sie die Spalte aus, indem Sie für deren `Width` \-Eigenschaft 0 festlegen. Geben Sie dabei den Spaltenindex der auszublendenden Spalte an.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## Siehe auch  
 [Gewusst wie: Ändern der angezeigten Daten im DataGrid\-Steuerelement in Windows Forms zur Laufzeit](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)   
 [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)