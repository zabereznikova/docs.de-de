---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: bd6614c76c63a44a7367ac7c7113c4db260c9a02
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322731"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="0cfd7-102">Vorgehensweise: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0cfd7-102">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="0cfd7-103">Elemente können ein Windows Forms-Kombinationsfeld, Listenfeld hinzugefügt werden oder Listenfeld in einer Vielzahl von Möglichkeiten, nicht überprüft, da diese Steuerelemente an eine Vielzahl von Datenquellen gebunden werden können.</span><span class="sxs-lookup"><span data-stu-id="0cfd7-103">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="0cfd7-104">Allerdings wird in diesem Thema zeigt die einfachste Methode, und erfordert keine Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="0cfd7-104">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="0cfd7-105">Die angezeigten Elemente sind im Allgemeinen Zeichenfolgen. Allerdings kann ein Objekt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cfd7-105">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="0cfd7-106">Der Text, der im Steuerelement angezeigt wird, wird den Rückgabewert von des Objekts `ToString` Methode.</span><span class="sxs-lookup"><span data-stu-id="0cfd7-106">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="0cfd7-107">Hinzufügen von Elementen</span><span class="sxs-lookup"><span data-stu-id="0cfd7-107">To add items</span></span>  
  
1. <span data-ttu-id="0cfd7-108">Fügen Sie der Zeichenfolge oder ein Objekt zur Liste mit den `Add` Methode der `ObjectCollection` Klasse.</span><span class="sxs-lookup"><span data-stu-id="0cfd7-108">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="0cfd7-109">Die Auflistung enthält einen Verweis auf die `Items` Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="0cfd7-109">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="0cfd7-110">ODER</span><span class="sxs-lookup"><span data-stu-id="0cfd7-110">or -</span></span>  
  
2. <span data-ttu-id="0cfd7-111">Fügen Sie der Zeichenfolge oder das Objekt an der gewünschten Stelle in der Liste mit den `Insert` Methode:</span><span class="sxs-lookup"><span data-stu-id="0cfd7-111">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="0cfd7-112">ODER</span><span class="sxs-lookup"><span data-stu-id="0cfd7-112">or -</span></span>  
  
3. <span data-ttu-id="0cfd7-113">Weisen Sie ein gesamtes Array, das die `Items` Auflistung:</span><span class="sxs-lookup"><span data-stu-id="0cfd7-113">Assign an entire array to the `Items` collection:</span></span>  
  
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
  
### <a name="to-remove-an-item"></a><span data-ttu-id="0cfd7-114">So entfernen Sie ein Element</span><span class="sxs-lookup"><span data-stu-id="0cfd7-114">To remove an item</span></span>  
  
1. <span data-ttu-id="0cfd7-115">Rufen Sie die `Remove` oder `RemoveAt` Methode, um Elemente zu löschen.</span><span class="sxs-lookup"><span data-stu-id="0cfd7-115">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="0cfd7-116">`Remove` hat ein Argument, der angibt, der zu entfernenden Elements.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="0cfd7-116">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="0cfd7-117">Entfernt das Element mit der angegebenen Indexnummer.</span><span class="sxs-lookup"><span data-stu-id="0cfd7-117">removes the item with the specified index number.</span></span>  
  
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
  
### <a name="to-remove-all-items"></a><span data-ttu-id="0cfd7-118">So entfernen Sie alle Elemente</span><span class="sxs-lookup"><span data-stu-id="0cfd7-118">To remove all items</span></span>  
  
1. <span data-ttu-id="0cfd7-119">Rufen Sie die `Clear` Methode, um alle Elemente aus der Auflistung zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="0cfd7-119">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0cfd7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cfd7-120">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="0cfd7-121">Vorgehensweise: Sortieren des Inhalts einer Windows Forms-ComboBox-, ListBox- oder CheckedListBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0cfd7-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="0cfd7-122">Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?</span><span class="sxs-lookup"><span data-stu-id="0cfd7-122">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="0cfd7-123">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="0cfd7-123">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
