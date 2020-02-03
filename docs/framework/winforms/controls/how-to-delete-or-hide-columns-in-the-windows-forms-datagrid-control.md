---
title: Löschen oder Ausblenden von Spalten im DataGrid-Steuerelement
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
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743295"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Sie können Spalten im Windows Forms <xref:System.Windows.Forms.DataGrid>-Steuerelement Programm gesteuert löschen oder ausblenden, indem Sie die Eigenschaften und Methoden der <xref:System.Windows.Forms.GridColumnStylesCollection>-und <xref:System.Windows.Forms.DataGridColumnStyle> Objekte (die Member der <xref:System.Windows.Forms.DataGridTableStyle>-Klasse sind) verwenden.  
  
 Die gelöschten oder ausgeblendeten Spalten sind immer noch in der Datenquelle vorhanden, an die das Raster gebunden ist, und es kann weiterhin Programm gesteuert darauf zugegriffen werden Sie sind nicht mehr im DataGrid sichtbar.  
  
> [!NOTE]
> Wenn Ihre Anwendung nicht auf bestimmte Datenspalten zugreift, und Sie nicht möchten, dass Sie im DataGrid angezeigt werden, ist es wahrscheinlich nicht notwendig, Sie zuerst in die Datenquelle einzufügen.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>So löschen Sie eine Spalte Programm gesteuert aus dem DataGrid-Steuerelement  
  
1. Deklarieren Sie im Deklarations Bereich Ihres Formulars eine neue Instanz der <xref:System.Windows.Forms.DataGridTableStyle>-Klasse.  
  
2. Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType>-Eigenschaft auf die Tabelle in der Datenquelle fest, auf die der Stil angewendet werden soll. Im folgenden Beispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>-Eigenschaft verwendet, von der ausgegangen wird, dass bereits festgelegt ist.  
  
3. Fügen Sie das neue <xref:System.Windows.Forms.DataGridTableStyle> Objekt der Auflistung der Tabellen Stile des DataGrid hinzu.  
  
4. Ruft die <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A>-Methode der <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Collection des <xref:System.Windows.Forms.DataGrid>auf und gibt den Spalten Index der zu löschenden Spalte an.  
  
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
  
1. Deklarieren Sie im Deklarations Bereich Ihres Formulars eine neue Instanz der <xref:System.Windows.Forms.DataGridTableStyle>-Klasse.  
  
2. Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>-Eigenschaft des <xref:System.Windows.Forms.DataGridTableStyle> auf die-Tabelle in der Datenquelle fest, auf die Sie den Stil anwenden möchten. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>-Eigenschaft verwendet, von der ausgegangen wird, dass bereits festgelegt ist.  
  
3. Fügen Sie das neue <xref:System.Windows.Forms.DataGridTableStyle> Objekt der Auflistung der Tabellen Stile des DataGrid hinzu.  
  
4. Blenden Sie die Spalte durch Festlegen der `Width`-Eigenschaft auf 0 aus, und geben Sie dabei den Spalten Index der auszublendenden Spalte an.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
