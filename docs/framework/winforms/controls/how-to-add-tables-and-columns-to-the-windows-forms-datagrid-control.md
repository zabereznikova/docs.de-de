---
title: "Gewusst wie: Hinzuf&#252;gen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Spalten [Windows Forms], Hinzufügen zum DataGrid-Steuerelement"
  - "DataGrid-Steuerelement [Windows Forms], Hinzufügen von Tabellen und Spalten"
  - "Tabellen [Windows Forms], Hinzufügen zum DataGrid-Steuerelement"
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Hinzuf&#252;gen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows&#160;Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Sie können Daten im <xref:System.Windows.Forms.DataGrid>\-Steuerelement von Windows Forms in Tabellen und Spalten anzeigen, indem Sie **DataGridTableStyle**\-Objekte erstellen und diese dem **GridTableStylesCollection**\-Objekt hinzufügen, auf das Sie mithilfe der **TableStyles**\-Eigenschaft des <xref:System.Windows.Forms.DataGrid>\-Steuerelements zugreifen können.  Jedes Tabellenformat zeigt den Inhalt einer beliebigen in der **MappingName**\-Eigenschaft des **DataGridTableStyle**\-Objekts festgelegten Datentabelle an.  Standardmäßig zeigt ein Tabellenformat, in dem keine Spaltenformate festgelegt sind, alle Spalten der Datentabelle an.  Sie können die angezeigten Spalten der Tabelle beschränken, indem Sie dem **GridColumnStylesCollection**\-Objekt, auf das mithilfe der **GridColumnsStyles**\-Eigenschaft eines jeden **DataGridTablesStyle**\-Objekts zugegriffen werden kann, **DataGridColumnStyle**\-Objekte hinzufügen.  
  
### So fügen Sie programmgesteuert eine Tabelle und eine Spalte hinzu  
  
1.  Um in der Tabelle Daten anzeigen zu können, müssen Sie das <xref:System.Windows.Forms.DataGrid>\-Steuerelement zunächst an ein DataSet binden.  Weitere Informationen finden Sie unter [Gewusst wie: Binden des DataGrid\-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Wenn Sie Spaltenformate programmgesteuert festlegen, erstellen Sie immer **DataGridColumnStyle**\-Objekte und fügen sie dem **GridColumnStylesCollection**\-Objekt hinzu, bevor Sie dem **GridTableStylesCollection**\-Objekt **DataGridTableStyle**\-Objekte hinzufügen.  Wenn Sie der Auflistung ein leeres **DataGridTableStyle**\-Objekt hinzufügen, werden **DataGridColumnStyle**\-Objekte automatisch erstellt.  In Folge dessen wird eine Ausnahme ausgelöst, wenn Sie versuchen, dem **GridColumnStylesCollection**\-Objekt neue **DataGridColumnStyle**\-Objekte mit doppelten **MappingName**\-Werten hinzuzufügen.  
  
2.  Deklarieren Sie ein neues Tabellenformat, und legen Sie seinen Zuordnungsnamen fest.  
  
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
  
3.  Deklarieren Sie ein neues Spaltenformat, und legen Sie seinen Zuordnungsnamen und weitere Eigenschaften fest.  
  
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
  
4.  Rufen Sie zum Hinzufügen der Spalte zum Tabellenformat die **Add**\-Methode des **GridColumnStylesCollection**\-Objekts auf  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Rufen Sie zum Hinzufügen der Spalte zum Datenraster die **Add**\-Methode des **GridTableStylesCollection**\-Objekts auf  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## Siehe auch  
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)