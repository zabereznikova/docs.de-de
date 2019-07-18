---
title: 'Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: cc364f3609f8041378b0b03b8e1bc8f312fade18
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319910"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Sie können Daten anzeigen, in Windows Forms <xref:System.Windows.Forms.DataGrid> -Steuerelement in Tabellen und Spalten durch das Erstellen **DataGridTableStyle** Objekte und Hinzufügen der Benutzer zur der **GridTableStylesCollection** -Objekt, das ist erfolgt über die <xref:System.Windows.Forms.DataGrid> des Steuerelements **TableStyles** Eigenschaft. Jedes Format zeigt den Inhalt der Datentabelle, in angegeben ist der **DataGridTableStyle** des Objekts **%MappingName** Eigenschaft. Standardmäßig zeigt ein Tabellenformat ohne Spaltenformate angegeben, dass alle Spalten in der Datentabelle. Sie können einschränken, welche Spalten aus der Tabelle angezeigt werden, indem das Hinzufügen von **DataGridColumnStyle** Objekte die **GridColumnStylesCollection** -Objekt, das über zugegriffen wird die  **Angezeigten** Eigenschaft der einzelnen **DataGridTableStyle** Objekt.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>So eine Tabelle und Spalte ein DataGrid-Steuerelement programmgesteuert hinzu  
  
1. Sie müssen zuerst binden, um Daten in der Tabelle anzuzeigen, die <xref:System.Windows.Forms.DataGrid> Steuerelement zu einem Dataset. Weitere Informationen finden Sie unter [Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Wenn Sie Spaltenformate programmgesteuert festlegen zu können, erstellen Sie immer **DataGridColumnStyle** -Objekte und fügen sie der **GridColumnStylesCollection** Objekt vor dem Hinzufügen von  **DataGridTableStyle** Objekte die **GridTableStylesCollection** Objekt. Wenn Sie eine leere hinzufügen **DataGridTableStyle** Objekt, das der Auflistung **DataGridColumnStyle** Objekte automatisch für Sie generiert werden. Daher eine Ausnahme wird ausgelöst, wenn Sie versuchen, das Hinzufügen neuer **DataGridColumnStyle** Objekte mit doppelten **%MappingName** -Werte in der **GridColumnStylesCollection**Objekt.  
  
2. Deklarieren Sie ein neues Tabellenformat, und legen Sie dessen Zuordnungsnamen.  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3. Deklarieren Sie einen neuen Stil für die Spalte, und legen Sie den Zuordnungsnamen und andere Eigenschaften.  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4. Rufen Sie die **hinzufügen** -Methode der der **GridColumnStylesCollection** Objekt, das die Spalte das Tabellenformat hinzufügen  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5. Rufen Sie die **hinzufügen** Methode der **GridTableStylesCollection** Objekt, das Tabellenformat das Datenraster hinzugefügt.  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Vorgehensweise: Löschen oder Ausblenden von Spalten im DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
