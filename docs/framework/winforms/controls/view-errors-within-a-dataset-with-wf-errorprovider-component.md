---
title: "Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms"
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
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28c90df258db8480f68eea05f922b36f30d81a3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms
Sie können Windows Forms <xref:System.Windows.Forms.ErrorProvider> Komponente Spaltenfehler innerhalb eines Datasets oder anderen Datenquelle anzeigen. Für ein <xref:System.Windows.Forms.ErrorProvider> Komponente, bei der Datenfehler anzuzeigen, die in einem Formular keine werden direkt mit einem Steuerelement verknüpft ist. Sobald es an eine Datenquelle gebunden ist, können sie ein Fehlersymbol neben jedem Steuerelement anzeigen, die an die gleiche Datenquelle gebunden ist.  
  
> [!NOTE]
>  Wenn Sie dem ErrorProvider ändern <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> und <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> Eigenschaften zur Laufzeit, verwenden Sie die <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> Methode, um Konflikte zu vermeiden.  
  
### <a name="to-display-data-errors"></a>Daten angezeigt werden sollen  
  
1.  Binden Sie die Komponente zu einer bestimmten Spalte in einer Datentabelle.  
  
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
  
2.  Legen Sie die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> Eigenschaft, um das Formular.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  Die Position des aktuellen Datensatzes auf eine Zeile, die ein Spaltenfehler enthält, festgelegt.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die ErrorProvider-Komponente](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
