---
title: 'Vorgehensweise: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: b869898a20008343b6c6cbe4bc7e399fc86fb232
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306052"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="d9726-102">Vorgehensweise: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten</span><span class="sxs-lookup"><span data-stu-id="d9726-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="d9726-103">Sie binden die <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> auf Daten für Aufgaben wie das Durchsuchen von Daten in einer Datenbank eingeben neuer Daten, oder Bearbeiten vorhandener Daten.</span><span class="sxs-lookup"><span data-stu-id="d9726-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="d9726-104">Zum Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="d9726-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="d9726-105">Legen Sie die `DataSource` Eigenschaft, um ein Datenquellenobjekt.</span><span class="sxs-lookup"><span data-stu-id="d9726-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="d9726-106">Mögliche Datenquellen umfassen eine <xref:System.Windows.Forms.BindingSource> an Daten, einer Datentabelle, eine Data source View, ein Dataset gebunden ist, eine Datenansicht Manager, ein Array oder eine beliebige Klasse, die implementiert die <xref:System.Collections.IList> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d9726-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="d9726-107">Weitere Informationen finden Sie unter [von Windows Forms unterstützte Datenquellen](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d9726-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="d9726-108">Wenn Sie in eine Tabelle binden, legen Sie die `DisplayMember` -Eigenschaft auf den Namen einer Spalte in der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="d9726-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="d9726-109">\- oder –</span><span class="sxs-lookup"><span data-stu-id="d9726-109">\- or -</span></span>  
  
     <span data-ttu-id="d9726-110">Wenn Sie eine Bindung eine <xref:System.Collections.IList>, legen Sie eine öffentliche Eigenschaft des Typs in der Liste der Anzeigemember.</span><span class="sxs-lookup"><span data-stu-id="d9726-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d9726-111">Wenn Sie eine Datenquelle gebunden sind, die nicht implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle, z. B. eine <xref:System.Collections.ArrayList>, Daten für das gebundene Steuerelement werden nicht aktualisiert werden, wenn die Datenquelle aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d9726-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="d9726-112">Z. B. Wenn Sie über ein Kombinationsfeld gebunden ein <xref:System.Collections.ArrayList> und Daten werden hinzugefügt, um die <xref:System.Collections.ArrayList>, diese neue Elemente werden nicht im Kombinationsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d9726-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="d9726-113">Sie können jedoch erzwingen, dass im Kombinationsfeld aktualisiert werden, durch den Aufruf der <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> und <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> Methoden für die Instanz der <xref:System.Windows.Forms.BindingContext> Klasse an die das Steuerelement gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="d9726-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9726-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9726-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="d9726-115">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="d9726-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="d9726-116">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9726-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="d9726-117">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="d9726-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
