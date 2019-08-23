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
ms.openlocfilehash: f361526c44f8fbb9ab282fe15ae109b67e8f01dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922751"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="11e30-102">Vorgehensweise: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten</span><span class="sxs-lookup"><span data-stu-id="11e30-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="11e30-103">Sie können und <xref:System.Windows.Forms.ListBox> an <xref:System.Windows.Forms.ComboBox> Daten binden, um Aufgaben wie das Durchsuchen von Daten in einer Datenbank, das Eingeben neuer Daten oder das Bearbeiten vorhandener Daten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="11e30-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="11e30-104">So binden Sie ein ComboBox-oder ListBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="11e30-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="11e30-105">Legen Sie `DataSource` die-Eigenschaft auf ein Datenquellen Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="11e30-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="11e30-106">Mögliche Datenquellen sind eine <xref:System.Windows.Forms.BindingSource> gebundene Datenquelle, eine Datentabelle, eine Datenansicht, ein DataSet, ein Datenansichts-Manager, ein Array oder eine beliebige Klasse, <xref:System.Collections.IList> die die Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="11e30-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="11e30-107">Weitere Informationen finden Sie [unter von Windows Forms unterstützte Datenquellen](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="11e30-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="11e30-108">Wenn Sie an eine Tabelle binden, legen Sie die `DisplayMember` -Eigenschaft auf den Namen einer Spalte in der Datenquelle fest.</span><span class="sxs-lookup"><span data-stu-id="11e30-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="11e30-109">\- oder –</span><span class="sxs-lookup"><span data-stu-id="11e30-109">\- or -</span></span>  
  
     <span data-ttu-id="11e30-110">Wenn Sie an eine <xref:System.Collections.IList>binden, legen Sie den Anzeigemember auf eine öffentliche Eigenschaft des Typs in der Liste fest.</span><span class="sxs-lookup"><span data-stu-id="11e30-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="11e30-111">Wenn Sie an eine Datenquelle gebunden sind, die die <xref:System.ComponentModel.IBindingList> -Schnittstelle nicht implementiert (z <xref:System.Collections.ArrayList>. b.), werden die Daten des gebundenen Steuer Elements nicht aktualisiert, wenn die Datenquelle aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="11e30-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="11e30-112">Wenn Sie z. b. ein Kombinations Feld an ein <xref:System.Collections.ArrayList> -Element gebunden haben und Daten <xref:System.Collections.ArrayList>zu hinzugefügt werden, werden diese neuen Elemente nicht im Kombinations Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11e30-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="11e30-113">Sie können jedoch erzwingen, dass das Kombinations Feld aktualisiert wird, indem Sie <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> die <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> -Methode und die-Methode <xref:System.Windows.Forms.BindingContext> für die Instanz der-Klasse aufrufen, an die das Steuerelement gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="11e30-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e30-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11e30-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="11e30-115">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="11e30-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="11e30-116">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="11e30-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="11e30-117">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="11e30-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
