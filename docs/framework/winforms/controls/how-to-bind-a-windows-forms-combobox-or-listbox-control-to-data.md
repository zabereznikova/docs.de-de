---
title: 'Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten'
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6193e4cc86a470f046c220dc21150e0fc0bf792a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="de4a1-102">Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten</span><span class="sxs-lookup"><span data-stu-id="de4a1-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="de4a1-103">Sie können Binden der <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> auf Daten zu Aufgaben wie das Durchsuchen von Daten in einer Datenbank, neue Daten eingeben oder Bearbeiten vorhandener Daten.</span><span class="sxs-lookup"><span data-stu-id="de4a1-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="de4a1-104">So binden ein Kombinations- oder Listenfeld-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="de4a1-104">To bind a ComboBox or ListBox control</span></span>  
  
1.  <span data-ttu-id="de4a1-105">Legen Sie die `DataSource` -Eigenschaft auf ein Datenquellenobjekt.</span><span class="sxs-lookup"><span data-stu-id="de4a1-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="de4a1-106">Mögliche Datenquellen umfassen eine <xref:System.Windows.Forms.BindingSource> an Daten, eine Datentabelle, eine Data source View, ein Dataset gebunden ist, eine Datenansicht-Manager, ein Array oder jede Klasse, implementiert die <xref:System.Collections.IList> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="de4a1-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="de4a1-107">Weitere Informationen finden Sie unter [von Windows Forms unterstützte Datenquellen](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="de4a1-107">For more information, see [Data Sources Supported by Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="de4a1-108">Wenn Sie in eine Tabelle binden, legen Sie die `DisplayMember` -Eigenschaft auf den Namen einer Spalte in der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="de4a1-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="de4a1-109">\- oder –</span><span class="sxs-lookup"><span data-stu-id="de4a1-109">\- or -</span></span>  
  
     <span data-ttu-id="de4a1-110">Wenn Sie eine Bindung an eine <xref:System.Collections.IList>, legen Sie eine öffentliche Eigenschaft des Typs in der Liste der Anzeigemember.</span><span class="sxs-lookup"><span data-stu-id="de4a1-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    >  <span data-ttu-id="de4a1-111">Wenn Sie eine Datenquelle gebunden sind, die nicht implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle, wie ein <xref:System.Collections.ArrayList>, das gebundene Steuerelement Daten werden nicht aktualisiert werden, wenn die Datenquelle aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="de4a1-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="de4a1-112">Z. B. Wenn Sie über ein Kombinationsfeld gebunden zu einer <xref:System.Collections.ArrayList> und Daten hinzugefügt werden die <xref:System.Collections.ArrayList>, diese neuen Elemente nicht im Kombinationsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de4a1-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="de4a1-113">Allerdings können Sie erzwingen, das Kombinationsfeld aufrufen aktualisiert werden die <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> und <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> Methoden für die Instanz die <xref:System.Windows.Forms.BindingContext> Klasse, die das Steuerelement gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="de4a1-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4a1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de4a1-114">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="de4a1-115">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="de4a1-115">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="de4a1-116">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de4a1-116">Data Binding and Windows Forms</span></span>](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="de4a1-117">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="de4a1-117">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
