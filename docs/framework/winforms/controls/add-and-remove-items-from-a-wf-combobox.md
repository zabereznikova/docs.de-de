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
ms.workload: dotnet
ms.openlocfilehash: faf0422db9915806442ab96759d63e15ff98b813
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms
Elemente können hinzugefügt werden, um ein Windows Forms-Kombinationsfeld, Listenfeld oder Listenfeld eine Vielzahl von Möglichkeiten, nicht überprüft, da diese Steuerelemente an eine Vielzahl von Datenquellen gebunden werden können. Allerdings wird in diesem Thema zeigt die einfachste Methode, und erfordert keine Datenbindung. Die angezeigten Elemente sind in der Regel Zeichenfolgen. Allerdings kann jedes Objekt verwendet werden. Der im Steuerelement angezeigte Text ist der Wert, der von dem Objekt zurückgegebenen `ToString` Methode.  
  
### <a name="to-add-items"></a>Hinzufügen von Elementen  
  
1.  Fügen Sie der Zeichenfolge oder ein Objekt der Liste mithilfe der `Add` Methode der `ObjectCollection` Klasse. Die Auflistung verwiesen wird, mithilfe der `Items` Eigenschaft:  
  
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
  
2.  Fügen Sie die Zeichenfolge oder das Objekt an der gewünschten Stelle in der Liste mit den `Insert` Methode:  
  
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
  
3.  Ein Array für die gesamte auf dem `Items` Auflistung:  
  
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
  
1.  Rufen Sie die `Remove` oder `RemoveAt` Methode, um Elemente zu löschen.  
  
     `Remove`hat ein Argument, das das zu entfernende Element angibt.`RemoveAt` Entfernt das Element mit dem angegebenen Index zurück.  
  
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
  
1.  Rufen Sie die `Clear` Methode, um alle Elemente aus der Auflistung zu entfernen:  
  
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
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [Windows Forms-Steuerelemente zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
