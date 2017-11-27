---
title: "Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms"
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
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 96f18f02f82b0e7f9f517890ec963b43fa8d8f60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="c3e77-102">Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c3e77-102">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="c3e77-103">Elemente können hinzugefügt werden, um ein Windows Forms-Kombinationsfeld, Listenfeld oder Listenfeld eine Vielzahl von Möglichkeiten, nicht überprüft, da diese Steuerelemente an eine Vielzahl von Datenquellen gebunden werden können.</span><span class="sxs-lookup"><span data-stu-id="c3e77-103">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="c3e77-104">Allerdings wird in diesem Thema zeigt die einfachste Methode, und erfordert keine Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="c3e77-104">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="c3e77-105">Die angezeigten Elemente sind in der Regel Zeichenfolgen. Allerdings kann jedes Objekt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3e77-105">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="c3e77-106">Der im Steuerelement angezeigte Text ist der Wert, der von dem Objekt zurückgegebenen `ToString` Methode.</span><span class="sxs-lookup"><span data-stu-id="c3e77-106">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="c3e77-107">Hinzufügen von Elementen</span><span class="sxs-lookup"><span data-stu-id="c3e77-107">To add items</span></span>  
  
1.  <span data-ttu-id="c3e77-108">Fügen Sie der Zeichenfolge oder ein Objekt der Liste mithilfe der `Add` Methode der `ObjectCollection` Klasse.</span><span class="sxs-lookup"><span data-stu-id="c3e77-108">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="c3e77-109">Die Auflistung verwiesen wird, mithilfe der `Items` Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="c3e77-109">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="c3e77-110">ODER</span><span class="sxs-lookup"><span data-stu-id="c3e77-110">or -</span></span>  
  
2.  <span data-ttu-id="c3e77-111">Fügen Sie die Zeichenfolge oder das Objekt an der gewünschten Stelle in der Liste mit den `Insert` Methode:</span><span class="sxs-lookup"><span data-stu-id="c3e77-111">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="c3e77-112">ODER</span><span class="sxs-lookup"><span data-stu-id="c3e77-112">or -</span></span>  
  
3.  <span data-ttu-id="c3e77-113">Ein Array für die gesamte auf dem `Items` Auflistung:</span><span class="sxs-lookup"><span data-stu-id="c3e77-113">Assign an entire array to the `Items` collection:</span></span>  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="c3e77-114">So entfernen Sie ein Element</span><span class="sxs-lookup"><span data-stu-id="c3e77-114">To remove an item</span></span>  
  
1.  <span data-ttu-id="c3e77-115">Rufen Sie die `Remove` oder `RemoveAt` Methode, um Elemente zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c3e77-115">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="c3e77-116">`Remove`hat ein Argument, das das zu entfernende Element angibt.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="c3e77-116">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="c3e77-117">Entfernt das Element mit dem angegebenen Index zurück.</span><span class="sxs-lookup"><span data-stu-id="c3e77-117">removes the item with the specified index number.</span></span>  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a><span data-ttu-id="c3e77-118">So entfernen Sie alle Elemente</span><span class="sxs-lookup"><span data-stu-id="c3e77-118">To remove all items</span></span>  
  
1.  <span data-ttu-id="c3e77-119">Rufen Sie die `Clear` Methode, um alle Elemente aus der Auflistung zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="c3e77-119">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c3e77-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3e77-120">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [<span data-ttu-id="c3e77-121">Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c3e77-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="c3e77-122">Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?</span><span class="sxs-lookup"><span data-stu-id="c3e77-122">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [<span data-ttu-id="c3e77-123">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="c3e77-123">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
