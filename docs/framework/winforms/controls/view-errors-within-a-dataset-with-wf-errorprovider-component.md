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
ms.openlocfilehash: 3dbd2ccca607869a6f28bc5b3bd1c9f0769db9f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950081"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="6da3b-102">Vorgehensweise: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6da3b-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="6da3b-103">Sie können die Windows Forms <xref:System.Windows.Forms.ErrorProvider> Komponente verwenden, um Spalten Fehler in einem DataSet oder einer anderen Datenquelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6da3b-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="6da3b-104">Damit eine <xref:System.Windows.Forms.ErrorProvider> -Komponente Datenfehler in einem Formular anzeigt, muss Sie nicht direkt einem-Steuerelement zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6da3b-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="6da3b-105">Nachdem Sie an eine Datenquelle gebunden wurde, kann Sie ein Fehler Symbol neben jedem Steuerelement anzeigen, das an dieselbe Datenquelle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="6da3b-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6da3b-106">Wenn Sie die-und <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> -Eigenschaften des Fehler Anbieters zur Laufzeit ändern, sollten Sie die <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> -Methode verwenden, um Konflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6da3b-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="6da3b-107">So zeigen Sie Datenfehler an</span><span class="sxs-lookup"><span data-stu-id="6da3b-107">To display data errors</span></span>  
  
1. <span data-ttu-id="6da3b-108">Binden Sie die Komponente an eine bestimmte Spalte innerhalb einer Datentabelle.</span><span class="sxs-lookup"><span data-stu-id="6da3b-108">Bind the component to a specific column within a data table.</span></span>  
  
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
  
2. <span data-ttu-id="6da3b-109">Legen Sie <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> die-Eigenschaft auf das Formular fest.</span><span class="sxs-lookup"><span data-stu-id="6da3b-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. <span data-ttu-id="6da3b-110">Legen Sie die Position des aktuellen Datensatzes auf eine Zeile fest, die einen Spalten Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="6da3b-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6da3b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6da3b-111">See also</span></span>

- [<span data-ttu-id="6da3b-112">Übersicht über die ErrorProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="6da3b-112">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="6da3b-113">Vorgehensweise: Anzeigen von Fehler Symbolen für die Formular Validierung mit der Windows Forms ErrorProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="6da3b-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](display-error-icons-for-form-validation-with-wf-errorprovider.md)
