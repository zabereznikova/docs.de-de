---
title: Bestimmen von geprüften Elementen im CheckedListBox-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5d93a63e9c1c6aae91ecfe83590c59450a565afe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182189"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Gewusst wie: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement von Windows Forms
Wenn Sie Daten in <xref:System.Windows.Forms.CheckedListBox> einem Windows Forms-Steuerelement darstellen, können <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> Sie entweder die in der <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> Eigenschaft gespeicherte Auflistung durchlaufen oder die Liste mithilfe der Methode durchlaufen, um zu bestimmen, welche Elemente überprüft werden. Die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> Methode nimmt eine Elementindexnummer `true` als `false`Argument und gibt oder zurück. Im Gegensatz zu dem, <xref:System.Windows.Forms.ListBox.SelectedItems%2A> <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> was Sie erwarten, bestimmen die und Eigenschaften nicht, welche Elemente überprüft werden. sie bestimmen, welche Elemente hervorgehoben werden.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>So ermitteln Sie geprüfte Elemente in einem CheckedListBox-Steuerelement  
  
1. Durchlaufen der <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> Auflistung, beginnend bei 0, da die Auflistung auf Null basiert. Beachten Sie, dass diese Methode Ihnen die Artikelnummer in der Liste der geprüften Elemente und nicht die Gesamtliste angibt. Wenn also das erste Element in der Liste nicht aktiviert ist und das zweite Element aktiviert ist, wird der folgende Code Text wie "Checked Item 1 = MyListItem2" angezeigt.  
  
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
  
2. Gehen Sie <xref:System.Windows.Forms.CheckedListBox.Items%2A> durch die Auflistung, beginnend bei 0, da <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> die Auflistung nullbasiert ist, und rufen Sie die Methode für jedes Element auf. Beachten Sie, dass diese Methode Ihnen die Artikelnummer in der Gesamtliste gibt, wenn also das erste Element in der Liste nicht aktiviert ist und das zweite Element aktiviert ist, wird etwa "Artikel 2 = MyListItem2" angezeigt.  
  
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

- [Steuerelemente in Windows Forms zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
