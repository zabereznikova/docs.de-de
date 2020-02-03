---
title: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5854f7e6be759daeb604458ea8554d3c98ed39c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743243"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Gewusst wie: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement von Windows Forms
Beim darstellen von Daten in einem Windows Forms <xref:System.Windows.Forms.CheckedListBox>-Steuerelement können Sie entweder die Auflistung durchlaufen, die in der <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>-Eigenschaft gespeichert ist, oder die Liste durchlaufen, indem Sie die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>-Methode verwenden, um zu bestimmen, welche Elemente geprüft werden. Die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>-Methode nimmt eine Element Indexnummer als Argument an und gibt `true` oder `false`zurück. Anders als erwartet können die Eigenschaften <xref:System.Windows.Forms.ListBox.SelectedItems%2A> und <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> nicht bestimmen, welche Elemente geprüft werden. Sie bestimmen, welche Elemente hervorgehoben werden.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>So bestimmen Sie aktivierte Elemente in einem CheckedListBox-Steuerelement  
  
1. Iterieren Sie die <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> Auflistung, beginnend bei 0, da die Auflistung NULL basiert. Beachten Sie, dass diese Methode die Element Nummer in der Liste der aktivierten Elemente und nicht die Gesamtliste enthält. Wenn das erste Element in der Liste nicht aktiviert ist und das zweite Element aktiviert ist, zeigt der nachfolgende Code z. b. Text wie "aktiviertes Element 1 = MyListItem2" an.  
  
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
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - oder –  
  
2. Durchlaufen Sie die <xref:System.Windows.Forms.CheckedListBox.Items%2A> Auflistung, beginnend bei 0, da die Auflistung NULL basiert, und nennen Sie die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>-Methode für jedes Element. Beachten Sie, dass diese Methode die Element Nummer in der Gesamtliste enthält. wenn das erste Element in der Liste nicht aktiviert und das zweite Element aktiviert ist, wird etwa "Item 2 = MyListItem2" angezeigt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
