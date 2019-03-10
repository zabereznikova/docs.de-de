---
title: 'Vorgehensweise: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 6202ac758d2cbf599c7e48a31ed2804608c70977
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705387"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Vorgehensweise: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms
Sie können die Windows-Formulare verwenden <xref:System.Windows.Forms.ErrorProvider> Komponente, um die Spaltenfehler innerhalb eines Datasets oder anderen Datenquelle anzuzeigen. Für eine <xref:System.Windows.Forms.ErrorProvider> Komponente zum Anzeigen der Datenfehler in einem Formular, es muss keine werden direkt mit einem Steuerelement verknüpft ist. Sobald sie mit einer Datenquelle gebunden ist, kann es ein Fehlersymbol neben jedem Steuerelement anzeigen, die an die gleiche Datenquelle gebunden ist.  
  
> [!NOTE]
>  Wenn Sie über die ErrorProvider ändern <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> und <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> Eigenschaften zur Laufzeit, verwenden Sie die <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> Methode, um Konflikte zu vermeiden.  
  
### <a name="to-display-data-errors"></a>Zum Anzeigen der Datenfehler  
  
1.  Binden Sie die Komponente an einer bestimmten Spalte in eine Datentabelle.  
  
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
  
3.  Die Position des aktuellen Datensatzes auf einer Zeile, die einem Spaltenfehler festgelegt.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über die ErrorProvider-Komponente](errorprovider-component-overview-windows-forms.md)
- [Vorgehensweise: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)
