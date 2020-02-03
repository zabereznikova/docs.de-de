---
title: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement
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
ms.openlocfilehash: 2db2e38c326cbcd78c58ee4fe00cd9ed20ae0e8a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747205"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms

> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Sie können Daten in der Windows Forms <xref:System.Windows.Forms.DataGrid>-Steuerelement in Tabellen und Spalten anzeigen, indem Sie **DataGridTableStyle** -Objekte erstellen und Sie dem **GridTableStylesCollection** -Objekt hinzufügen, auf das über die **TableStyles** -Eigenschaft des <xref:System.Windows.Forms.DataGrid>-Steuer Elements zugegriffen wird. Jedes Tabellenformat zeigt den Inhalt einer beliebigen Datentabelle an, die in der **MappingName** -Eigenschaft des **DataGridTableStyle** -Objekts angegeben ist. Standardmäßig werden in einem Tabellenformat ohne Angabe von Spalten Formaten alle Spalten in der Datentabelle angezeigt. Sie können einschränken, welche Spalten aus der Tabelle angezeigt werden, indem Sie dem **GridColumnStylesCollection** -Objekt **DataGridColumnStyle** -Objekte hinzufügen, auf das über die **GridColumnStyles** -Eigenschaft der einzelnen **DataGridTableStyle** -Objekte zugegriffen wird.

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>So fügen Sie einem DataGrid eine Tabelle und eine Spalte Programm gesteuert hinzu

1. Um Daten in der Tabelle anzuzeigen, müssen Sie zuerst das <xref:System.Windows.Forms.DataGrid>-Steuerelement an ein DataSet binden. Weitere Informationen finden Sie unter Gewusst [wie: Binden des Windows Forms DataGrid-Steuer Elements an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

    > [!CAUTION]
    > Erstellen Sie beim programmgesteuerten Angeben von Spalten **Formaten immer DataGridColumnStyle** -Objekte, und fügen Sie Sie dem **GridColumnStylesCollection** -Objekt hinzu, bevor Sie dem **GridTableStylesCollection** -Objekt **DataGridTableStyle** -Objekte hinzufügen. Wenn Sie der Auflistung ein leeres **DataGridTableStyle** -Objekt hinzufügen, werden automatisch **DataGridColumnStyle** -Objekte für Sie generiert. Folglich wird eine Ausnahme ausgelöst, wenn Sie versuchen, dem **GridColumnStylesCollection** -Objekt neue **DataGridColumnStyle** -Objekte mit doppelten **MappingName** -Werten hinzuzufügen.

2. Deklarieren Sie einen neuen Tabellen Stil, und legen Sie seinen Zuordnungsnamen

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

3. Deklarieren Sie einen neuen Spalten Stil, und legen Sie seinen Zuordnungsnamen und andere Eigenschaften fest

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

4. Ruft die **Add** -Methode des **GridColumnStylesCollection** -Objekts auf, um die Spalte dem Tabellenformat hinzuzufügen.

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. Greifen Sie auf die **Add** -Methode des **GridTableStylesCollection** -Objekts zu, um dem Datenraster den Tabellen Stil hinzuzufügen.

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a>Weitere Informationen

- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
