---
title: ComboBox-Steuerelement oder ListBox-Steuerelement an Daten binden
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
ms.openlocfilehash: 99d9b53b32d6faae888b134d4ed486980c05a75b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742035"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="51095-102">Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten</span><span class="sxs-lookup"><span data-stu-id="51095-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="51095-103">Sie können die <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> an Daten binden, um Aufgaben wie das Durchsuchen von Daten in einer Datenbank, das Eingeben neuer Daten oder das Bearbeiten vorhandener Daten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="51095-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="51095-104">So binden Sie ein ComboBox-oder ListBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="51095-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="51095-105">Legen Sie die `DataSource`-Eigenschaft auf ein Datenquellen Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="51095-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="51095-106">Mögliche Datenquellen sind ein <xref:System.Windows.Forms.BindingSource> an Daten gebundene Daten, eine Datentabelle, eine Datenansicht, ein DataSet, ein Datenansichts-Manager, ein Array oder eine beliebige Klasse, die die <xref:System.Collections.IList>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="51095-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="51095-107">Weitere Informationen finden Sie [unter von Windows Forms unterstützte Datenquellen](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="51095-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="51095-108">Wenn Sie an eine Tabelle binden, legen Sie die `DisplayMember`-Eigenschaft auf den Namen einer Spalte in der Datenquelle fest.</span><span class="sxs-lookup"><span data-stu-id="51095-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="51095-109">\- oder –</span><span class="sxs-lookup"><span data-stu-id="51095-109">\- or -</span></span>  
  
     <span data-ttu-id="51095-110">Wenn Sie an eine <xref:System.Collections.IList>binden, legen Sie den Anzeigemember auf eine öffentliche Eigenschaft des Typs in der Liste fest.</span><span class="sxs-lookup"><span data-stu-id="51095-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="51095-111">Wenn Sie an eine Datenquelle gebunden sind, die die <xref:System.ComponentModel.IBindingList>-Schnittstelle nicht implementiert (z. b. eine <xref:System.Collections.ArrayList>), werden die Daten des gebundenen Steuer Elements nicht aktualisiert, wenn die Datenquelle aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="51095-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="51095-112">Wenn Sie z. b. ein Kombinations Feld haben, das an einen <xref:System.Collections.ArrayList> gebunden ist, und dem <xref:System.Collections.ArrayList>Daten hinzugefügt werden, werden diese neuen Elemente nicht im Kombinations Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51095-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="51095-113">Sie können jedoch erzwingen, dass das Kombinations Feld aktualisiert wird, indem Sie die Methoden <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> und <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> für die Instanz der <xref:System.Windows.Forms.BindingContext> Klasse aufrufen, an die das Steuerelement gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="51095-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51095-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51095-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="51095-115">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="51095-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="51095-116">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51095-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="51095-117">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="51095-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
