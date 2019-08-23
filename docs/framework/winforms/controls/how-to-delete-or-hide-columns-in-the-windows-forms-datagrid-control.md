---
title: 'Vorgehensweise: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: 70229abddb831788f521f85747db1093c941ba8a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967372"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Vorgehensweise: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Sie können <xref:System.Windows.Forms.DataGrid> Spalten im Windows Forms Steuerelement Programm gesteuert löschen oder ausblenden, indem Sie die Eigenschaften und Methoden <xref:System.Windows.Forms.GridColumnStylesCollection> des-Objekts und des-Objekts (die <xref:System.Windows.Forms.DataGridTableStyle> Member der- <xref:System.Windows.Forms.DataGridColumnStyle> Klasse sind) verwenden.  
  
 Die gelöschten oder ausgeblendeten Spalten sind immer noch in der Datenquelle vorhanden, an die das Raster gebunden ist, und es kann weiterhin Programm gesteuert darauf zugegriffen werden Sie sind nicht mehr im DataGrid sichtbar.  
  
> [!NOTE]
> Wenn Ihre Anwendung nicht auf bestimmte Datenspalten zugreift, und Sie nicht möchten, dass Sie im DataGrid angezeigt werden, ist es wahrscheinlich nicht notwendig, Sie zuerst in die Datenquelle einzufügen.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>So löschen Sie eine Spalte Programm gesteuert aus dem DataGrid-Steuerelement  
  
1. Deklarieren Sie im Deklarations Bereich Ihres Formulars eine neue Instanz der <xref:System.Windows.Forms.DataGridTableStyle> -Klasse.  
  
2. Legen Sie <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> die-Eigenschaft auf die Tabelle in der Datenquelle fest, auf die der Stil angewendet werden soll. Im folgenden Beispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft verwendet, von der angenommen wird, dass bereits festgelegt ist.  
  
3. Fügen Sie das <xref:System.Windows.Forms.DataGridTableStyle> neue-Objekt zur Auflistung der Tabellen Stile des DataGrid hinzu.  
  
4. Ruft die <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> <xref:System.Windows.Forms.DataGrid>-Methode der- <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Auflistung auf und gibt den Spalten Index der zu löschenden Spalte an.  
  
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
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>So blenden Sie eine Spalte im DataGrid Programm gesteuert aus  
  
1. Deklarieren Sie im Deklarations Bereich Ihres Formulars eine neue Instanz der <xref:System.Windows.Forms.DataGridTableStyle> -Klasse.  
  
2. Legen Sie <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> die-Eigenschaft <xref:System.Windows.Forms.DataGridTableStyle> des-Objekts auf die Tabelle in der Datenquelle fest, auf die Sie den Stil anwenden möchten. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft verwendet, von der angenommen wird, dass bereits festgelegt ist.  
  
3. Fügen Sie das <xref:System.Windows.Forms.DataGridTableStyle> neue-Objekt zur Auflistung der Tabellen Stile des DataGrid hinzu.  
  
4. Blenden Sie die Spalte durch Festlegen `Width` der-Eigenschaft auf 0 aus, und geben Sie dabei den Spalten Index der auszublendenden Spalte an.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Ändern der angezeigten Daten zur Laufzeit im DataGrid-Steuerelement Windows Forms](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [Vorgehensweise: Hinzufügen von Tabellen und Spalten zum Windows Forms DataGrid-Steuerelement](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
