---
title: Hinzufügen und Entfernen von Elementen aus einem ComboBox-, ListBox-oder CheckedListBox-Steuerelement
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
ms.openlocfilehash: 3a83d98af42386b566b4af7bc11ff383dea8fd6b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746303"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms
Elemente können einem Windows Forms Kombinations Feld, einem Listenfeld oder einem aktivierten Listenfeld auf verschiedene Weise hinzugefügt werden, da diese Steuerelemente an eine Vielzahl von Datenquellen gebunden werden können. In diesem Thema wird jedoch die einfachste Methode veranschaulicht, und es ist keine Datenbindung erforderlich. Die angezeigten Elemente sind normalerweise Zeichen folgen. Allerdings kann ein beliebiges-Objekt verwendet werden. Der im-Steuerelement angezeigte Text ist der Wert, der von der `ToString`-Methode des-Objekts zurückgegeben wird.  
  
### <a name="to-add-items"></a>So fügen Sie Elemente hinzu  
  
1. Fügen Sie die Zeichenfolge oder das Objekt der Liste hinzu, indem Sie die `Add`-Methode der `ObjectCollection`-Klasse verwenden. Auf die Auflistung wird mithilfe der `Items`-Eigenschaft verwiesen:  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - ODER  
  
2. Fügen Sie die Zeichenfolge oder das Objekt am gewünschten Punkt in der Liste mit der `Insert`-Methode ein:  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - ODER  
  
3. Weisen Sie der `Items` Auflistung ein gesamtes Array zu:  
  
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
  
### <a name="to-remove-an-item"></a>So entfernen Sie ein Element  
  
1. Ruft die `Remove`-oder `RemoveAt`-Methode auf, um Elemente zu löschen.  
  
     `Remove` verfügt über ein Argument, das das zu entfern gende Element angibt.`RemoveAt` entfernt das Element mit der angegebenen Indexnummer.  
  
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
  
### <a name="to-remove-all-items"></a>So entfernen Sie alle Elemente  
  
1. Ruft die `Clear`-Methode auf, um alle Elemente aus der Auflistung zu entfernen:  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
