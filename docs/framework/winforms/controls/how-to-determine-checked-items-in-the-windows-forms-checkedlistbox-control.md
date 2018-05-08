---
title: 'Gewusst wie: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 98b4ef7c4ac73e1560bd5c68f22898e46585d082
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Gewusst wie: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement von Windows Forms
Bei der Darstellung von Daten in einer Windows Forms <xref:System.Windows.Forms.CheckedListBox> -Steuerelement, Sie können entweder die Auflistung durchlaufen gespeichert, der <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> Eigenschaft oder das Durchlaufen der Liste mithilfe der <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> Methode, um zu bestimmen, welche Elemente aktiviert sind. Die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> Methode akzeptiert eine Elementindexnummer als Argument und gibt `true` oder `false`. Im Gegensatz zur, was zu erwarten die <xref:System.Windows.Forms.ListBox.SelectedItems%2A> und <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> Eigenschaften bestimmen nicht überprüft werden, welche Elemente; sie bestimmen, welche Elemente hervorgehoben sind.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement  
  
1.  Durchlaufen der <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> -Auflistung, beginnend mit 0, da die Auflistung nullbasiert ist. Beachten Sie, dass diese Methode Ihnen die Artikelnummer in der Liste der aktivierten Elemente, nicht die gesamte Liste zurückgibt. Wenn das erste Element in der Liste nicht aktiviert ist, und das zweite Element aktiviert ist, der folgenden Code Text wie anzeigen "Checked Item 1 = MyListItem2".  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x <= checkedListBox1.CheckedItems.Count - 1 ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
    MessageBox.Show (s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x <= checkedListBox1->CheckedItems->Count - 1; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - ODER  
  
2.  Durchlaufen der <xref:System.Windows.Forms.CheckedListBox.Items%2A> -Auflistung, beginnend mit 0, da die Auflistung nullbasiert, ist, und rufen die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> Methode für jedes Element. Beachten Sie, dass diese Methode gibt Ihnen die Artikelnummer in der gesamten Liste, wenn das erste Element die Liste nicht aktiviert ist und das zweite Element aktiviert ist, enthält es etwa wie "Element 2 = MyListItem2".  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
