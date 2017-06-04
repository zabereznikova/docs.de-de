---
title: "Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows&#160;Forms | Microsoft Docs"
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
  - "Fehlermeldungen, Anzeigen in Datasets"
  - "ErrorProvider-Komponente [Windows Forms], Datasetfehler"
  - "Fehler [Windows Forms], Datasetfehler"
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows&#160;Forms
Mit der <xref:System.Windows.Forms.ErrorProvider>\-Komponente in Windows Forms können Sie Spaltenfehler innerhalb eines Datasets oder einer anderen Datenquelle anzeigen.  Eine <xref:System.Windows.Forms.ErrorProvider>\-Komponente muss nicht direkt einem Steuerelement zugeordnet sein, um Datenfehler auf einem Formular anzuzeigen.  Sobald es an eine Datenquelle gebunden ist, kann es neben jedem Steuerelement, das an dieselbe Datenquelle gebunden ist, ein Fehlersymbol anzeigen.  
  
> [!NOTE]
>  Wenn Sie die <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>\-Eigenschaft und die <xref:System.Windows.Forms.ErrorProvider.DataMember%2A>\-Eigenschaft der ErrorProvider\-Komponente zur Laufzeit ändern, sollten Sie die <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A>\-Methode verwenden, um Konflikte zu vermeiden.  
  
### So zeigen Sie Datenfehler an  
  
1.  Binden Sie die Komponente an eine bestimmte Spalte innerhalb einer Datentabelle.  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
  
    ```  
  
2.  Legen Sie für das Formular die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>\-Eigenschaft fest.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
  
    ```  
  
3.  Legen Sie als Position des aktuellen Datensatzes eine Zeile mit einem Spaltenfehler fest.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
  
    ```  
  
## Siehe auch  
 [Übersicht über die ErrorProvider\-Komponente](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)   
 [Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)