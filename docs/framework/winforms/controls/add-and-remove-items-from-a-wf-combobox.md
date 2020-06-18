---
title: Hinzufügen und Entfernen von Elementen aus einem ComboBox-, ListBox-oder CheckedListBox-Steuerelement
ms.date: 03/30/2017
description: Erfahren Sie, wie Sie eine Windows Forms ComboBox-, ListBox-und CheckedListBox-Steuerelemente einfach und ohne Datenbindung hinzufügen und entfernen.
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
ms.openlocfilehash: f3701257bbe410bf03c4c21700705e87b581bf2e
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904441"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="574cc-103">Vorgehensweise: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="574cc-103">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="574cc-104">Elemente können einem Windows Forms Kombinations Feld, einem Listenfeld oder einem aktivierten Listenfeld auf verschiedene Weise hinzugefügt werden, da diese Steuerelemente an eine Vielzahl von Datenquellen gebunden werden können.</span><span class="sxs-lookup"><span data-stu-id="574cc-104">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="574cc-105">In diesem Thema wird jedoch die einfachste Methode veranschaulicht, und es ist keine Datenbindung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="574cc-105">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="574cc-106">Die angezeigten Elemente sind normalerweise Zeichen folgen. Allerdings kann ein beliebiges-Objekt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="574cc-106">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="574cc-107">Der im-Steuerelement angezeigte Text ist der Wert, der von der-Methode des-Objekts zurückgegeben wird `ToString` .</span><span class="sxs-lookup"><span data-stu-id="574cc-107">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="574cc-108">So fügen Sie Elemente hinzu</span><span class="sxs-lookup"><span data-stu-id="574cc-108">To add items</span></span>  
  
1. <span data-ttu-id="574cc-109">Fügen Sie die Zeichenfolge oder das Objekt der Liste hinzu, indem Sie die- `Add` Methode der- `ObjectCollection` Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="574cc-109">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="574cc-110">Auf die Auflistung wird mithilfe der- `Items` Eigenschaft verwiesen:</span><span class="sxs-lookup"><span data-stu-id="574cc-110">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="574cc-111">ODER</span><span class="sxs-lookup"><span data-stu-id="574cc-111">or -</span></span>  
  
2. <span data-ttu-id="574cc-112">Fügen Sie die Zeichenfolge oder das Objekt am gewünschten Punkt in der Liste mit der- `Insert` Methode ein:</span><span class="sxs-lookup"><span data-stu-id="574cc-112">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="574cc-113">ODER</span><span class="sxs-lookup"><span data-stu-id="574cc-113">or -</span></span>  
  
3. <span data-ttu-id="574cc-114">Weisen Sie der Auflistung ein gesamtes Array zu `Items` :</span><span class="sxs-lookup"><span data-stu-id="574cc-114">Assign an entire array to the `Items` collection:</span></span>  
  
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
  
### <a name="to-remove-an-item"></a><span data-ttu-id="574cc-115">So entfernen Sie ein Element</span><span class="sxs-lookup"><span data-stu-id="574cc-115">To remove an item</span></span>  
  
1. <span data-ttu-id="574cc-116">`Remove`Zum Löschen von Elementen die-oder-Methode aufzurufen `RemoveAt` .</span><span class="sxs-lookup"><span data-stu-id="574cc-116">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="574cc-117">`Remove`verfügt über ein Argument, das das zu entfern gende Element angibt.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="574cc-117">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="574cc-118">entfernt das Element mit der angegebenen Indexnummer.</span><span class="sxs-lookup"><span data-stu-id="574cc-118">removes the item with the specified index number.</span></span>  
  
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
  
### <a name="to-remove-all-items"></a><span data-ttu-id="574cc-119">So entfernen Sie alle Elemente</span><span class="sxs-lookup"><span data-stu-id="574cc-119">To remove all items</span></span>  
  
1. <span data-ttu-id="574cc-120">Ruft die- `Clear` Methode auf, um alle Elemente aus der Auflistung zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="574cc-120">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="574cc-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="574cc-121">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="574cc-122">Vorgehensweise: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="574cc-122">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="574cc-123">Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?</span><span class="sxs-lookup"><span data-stu-id="574cc-123">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="574cc-124">Steuerelemente in Windows Forms zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="574cc-124">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
