---
title: 'Vorgehensweise: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 190b53a248a77f03dd5d8cb13cb59a439fa9960d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157624"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="7efeb-102">Vorgehensweise: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7efeb-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="7efeb-103">Sie können die Windows-Formulare verwenden <xref:System.Windows.Forms.ErrorProvider> Komponente, um die Spaltenfehler innerhalb eines Datasets oder anderen Datenquelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7efeb-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="7efeb-104">Für eine <xref:System.Windows.Forms.ErrorProvider> Komponente zum Anzeigen der Datenfehler in einem Formular, es muss keine werden direkt mit einem Steuerelement verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="7efeb-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="7efeb-105">Sobald sie mit einer Datenquelle gebunden ist, kann es ein Fehlersymbol neben jedem Steuerelement anzeigen, die an die gleiche Datenquelle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="7efeb-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7efeb-106">Wenn Sie über die ErrorProvider ändern <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> und <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> Eigenschaften zur Laufzeit, verwenden Sie die <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> Methode, um Konflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7efeb-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="7efeb-107">Zum Anzeigen der Datenfehler</span><span class="sxs-lookup"><span data-stu-id="7efeb-107">To display data errors</span></span>  
  
1.  <span data-ttu-id="7efeb-108">Binden Sie die Komponente an einer bestimmten Spalte in eine Datentabelle.</span><span class="sxs-lookup"><span data-stu-id="7efeb-108">Bind the component to a specific column within a data table.</span></span>  
  
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
  
2.  <span data-ttu-id="7efeb-109">Legen Sie die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> Eigenschaft, um das Formular.</span><span class="sxs-lookup"><span data-stu-id="7efeb-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  <span data-ttu-id="7efeb-110">Die Position des aktuellen Datensatzes auf einer Zeile, die einem Spaltenfehler festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7efeb-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7efeb-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7efeb-111">See also</span></span>

- [<span data-ttu-id="7efeb-112">Übersicht über die ErrorProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="7efeb-112">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="7efeb-113">Vorgehensweise: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7efeb-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](display-error-icons-for-form-validation-with-wf-errorprovider.md)
