---
title: ComboBox-Steuerelement oder ListBox-Steuerelement an Daten binden
description: Erfahren Sie, wie Sie die Windows Forms ComboBox und ListBox an Daten binden, um Aufgaben wie das Durchsuchen von Daten in einer Datenbank, das Eingeben neuer Daten oder das Bearbeiten vorhandener Daten auszuführen.
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
ms.openlocfilehash: 0c07dc90ddc91061c5f34b5a237082cb444e89d9
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324065"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="0f117-103">Vorgehensweise: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten</span><span class="sxs-lookup"><span data-stu-id="0f117-103">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="0f117-104">Sie können <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> an Daten binden, um Aufgaben wie das Durchsuchen von Daten in einer Datenbank, das Eingeben neuer Daten oder das Bearbeiten vorhandener Daten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0f117-104">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="0f117-105">So binden Sie ein ComboBox-oder ListBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0f117-105">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="0f117-106">Legen Sie die- `DataSource` Eigenschaft auf ein Datenquellen Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="0f117-106">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="0f117-107">Mögliche Datenquellen sind eine <xref:System.Windows.Forms.BindingSource> gebundene Datenquelle, eine Datentabelle, eine Datenansicht, ein DataSet, ein Datenansichts-Manager, ein Array oder eine beliebige Klasse, die die <xref:System.Collections.IList> Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="0f117-107">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="0f117-108">Weitere Informationen finden Sie [unter von Windows Forms unterstützte Datenquellen](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0f117-108">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="0f117-109">Wenn Sie an eine Tabelle binden, legen Sie die- `DisplayMember` Eigenschaft auf den Namen einer Spalte in der Datenquelle fest.</span><span class="sxs-lookup"><span data-stu-id="0f117-109">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="0f117-110">\- oder -</span><span class="sxs-lookup"><span data-stu-id="0f117-110">\- or -</span></span>  
  
     <span data-ttu-id="0f117-111">Wenn Sie an eine binden <xref:System.Collections.IList> , legen Sie den Anzeigemember auf eine öffentliche Eigenschaft des Typs in der Liste fest.</span><span class="sxs-lookup"><span data-stu-id="0f117-111">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="0f117-112">Wenn Sie an eine Datenquelle gebunden sind, die die-Schnittstelle nicht implementiert (z. b.) <xref:System.ComponentModel.IBindingList> <xref:System.Collections.ArrayList> , werden die Daten des gebundenen Steuer Elements nicht aktualisiert, wenn die Datenquelle aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0f117-112">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="0f117-113">Wenn Sie z. b. ein Kombinations Feld an ein-Element gebunden haben <xref:System.Collections.ArrayList> und Daten zu hinzugefügt <xref:System.Collections.ArrayList> werden, werden diese neuen Elemente nicht im Kombinations Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f117-113">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="0f117-114">Sie können jedoch erzwingen, dass das Kombinations Feld aktualisiert wird, indem Sie die <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> -Methode und die- <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> Methode für die Instanz der- <xref:System.Windows.Forms.BindingContext> Klasse aufrufen, an die das Steuerelement gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="0f117-114">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f117-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f117-115">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="0f117-116">Datenbindung in Web Forms</span><span class="sxs-lookup"><span data-stu-id="0f117-116">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="0f117-117">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f117-117">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="0f117-118">Steuerelemente in Windows Forms zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="0f117-118">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
