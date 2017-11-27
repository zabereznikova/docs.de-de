---
title: "Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 970c2787bda50bcf0478b64df44176525f839482
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Sie können Daten anzeigen, in Windows Forms <xref:System.Windows.Forms.DataGrid> -Steuerelement in Tabellen und Spalten durch das Erstellen **DataGridTableStyle** Objekte und Hinzufügen der **GridTableStylesCollection** Objekt, das erfolgt über die <xref:System.Windows.Forms.DataGrid> des Steuerelements **TableStyles** Eigenschaft. Jedes Tabellenformat zeigt den Inhalt der Datentabelle, in angegeben ist der **DataGridTableStyle** des Objekts **%MappingName** Eigenschaft. Ein Tabellenformat ohne Spaltenformate angegeben werden in der Standardeinstellung alle Spalten in der Datentabelle angezeigt. Sie können einschränken, welche Spalten aus der Tabelle angezeigt werden, indem das Hinzufügen von **DataGridColumnStyle** -Objekte der **GridColumnStylesCollection** -Objekt, das über zugegriffen wird die  **Angezeigten** -Eigenschaft jedes **DataGridTableStyle** Objekt.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>So fügen eine Tabelle und Spalte ein DataGrid-Steuerelement programmgesteuert hinzu  
  
1.  Sie müssen zuerst binden, um die Daten in der Tabelle anzuzeigen, die <xref:System.Windows.Forms.DataGrid> Steuerelement zu einem Dataset. Weitere Informationen finden Sie unter [Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Wenn Sie Spaltenformate programmgesteuert angeben, erstellen Sie immer **DataGridColumnStyle** -Objekte und fügen sie der **GridColumnStylesCollection** Objekt vor dem Hinzufügen von  **DataGridTableStyle** -Objekte und die **GridTableStylesCollection** Objekt. Wenn Sie eine leere hinzufügen **DataGridTableStyle** Objekt der Auflistung **DataGridColumnStyle** Objekte automatisch für Sie generiert werden. Daher eine Ausnahme wird ausgelöst, wenn Sie versuchen, das Hinzufügen neuer **DataGridColumnStyle** Objekte mit doppelten **%MappingName** -Werte in der **GridColumnStylesCollection**Objekt.  
  
2.  Deklarieren Sie eine neue Tabellenformatvorlage, und legen Sie dessen Zuordnungsnamen.  
  
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
  
3.  Deklarieren Sie eine neue Spalte Formatvorlage und festlegen Sie den Zuordnungsnamen und andere Eigenschaften.  
  
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
  
4.  Rufen Sie die **hinzufügen** Methode der **GridColumnStylesCollection** -Objekt, das Tabellenformat die Spalte hinzuzufügen  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Rufen Sie die **hinzufügen** Methode der **GridTableStylesCollection** Objekt, das Tabellenformat das Datenraster hinzugefügt.  
  
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
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
