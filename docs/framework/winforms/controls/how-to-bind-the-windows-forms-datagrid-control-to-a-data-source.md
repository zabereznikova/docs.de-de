---
title: "Gewusst wie: Binden des DataGrid-Steuerelements in Windows&#160;Forms an eine Datenquelle | Microsoft Docs"
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
  - "Gebundene Steuerelemente"
  - "Gebundene Steuerelemente, DataGrid-Steuerelement"
  - "Datenbindung, DataGrid-Steuerelement"
  - "Datengebundene Steuerelemente, DataGrid"
  - "DataGrid-Steuerelement [Windows Forms], Datenbindung"
  - "Datasets [Windows Forms], Binden an DataGrid-Steuerelement"
  - "Windows Forms-Steuerelemente, Datenbindung"
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Binden des DataGrid-Steuerelements in Windows&#160;Forms an eine Datenquelle
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Das <xref:System.Windows.Forms.DataGrid>\-Steuerelement in Windows Forms wurde speziell für die Anzeige von Informationen aus einer Datenquelle entwickelt.  Zur Laufzeit binden Sie das Steuerelement, indem Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode aufrufen.  Daten können aus einer Vielzahl von Datenquellen angezeigt werden. Die gebräuchlichsten sind jedoch DataSets und Datenansichten.  
  
### So stellen Sie programmgesteuert eine Datenbindung an ein DataGrid\-Steuerelement her  
  
1.  Schreiben Sie Code, um das DataSet aufzufüllen.  
  
     Wenn es sich bei der Datenquelle um ein DataSet oder eine auf einer DataSet\-Tabelle beruhende Datenansicht handelt, fügen Sie dem Formular Code zum Füllen des DataSets hinzu.  
  
     Der genaue Code richtet sich dabei danach, woher das DataSet die Daten bezieht.  Wenn ein Dataset direkt aus einer Datenbank gefüllt wird, wird üblicherweise die `Fill` \-Methode eines Datenadapters aufgerufen, wie in folgendem Beispiel, in dem das Dataset `DsCategories1` gefüllt wird:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Bei einem Dataset, das aus einem XML\-Webdienst gefüllt wird, wird in der Regel eine Instanz des Dienstes im Code erstellt und anschließend eine seiner Methoden aufgerufen, die ein Dataset zurückgibt.  Dann führen Sie das Dataset aus dem XML\-Webdienst mit dem lokalen Dataset zusammen.  Im folgenden Beispiel wird gezeigt, wie Sie eine Instanz des XML\-Webdienstes `CategoriesService` erstellen, die zugehörige `GetCategories`\-Methode aufrufen und das sich daraus ergebende DataSet mit dem lokalen DataSet `DsCategories1` zusammenführen:  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2.  Rufen Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode des <xref:System.Windows.Forms.DataGrid>\-Steuerelements auf, und übergeben Sie dabei die Datenquelle und ein Datenmember.  Wenn nicht explizit ein Datenmember übergeben werden muss, übergeben Sie eine leere Zeichenfolge.  
  
    > [!NOTE]
    >  Beim erstmaligen Binden des Datenblatts können Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft des Steuerelements festlegen.  Diese Einstellungen können jedoch nicht mehr zurückgesetzt werden, nachdem sie festgelegt sind.  Deshalb ist es empfehlenswert, stattdessen immer die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode zu verwenden.  
  
     Im folgenden Beispiel wird gezeigt, wie Sie eine Bindung an die Tabelle Customers im Dataset `DsCustomers1` programmgesteuert herstellen:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Wenn sich außer der Tabelle Customers keine weiteren Tabellen im Dataset befinden, können Sie das Datenblatt auch folgendermaßen binden:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  \(Optional\) Weisen Sie dem Raster die gewünschten Tabellen\- und Spaltenformate zu.  Die Tabelle wird zwar auch ohne Tabellenformate angezeigt, jedoch mit einer minimalen Formatierung und allen vorhandenen Spalten.  
  
## Siehe auch  
 [Übersicht über das DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Datenbindung in Web Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)