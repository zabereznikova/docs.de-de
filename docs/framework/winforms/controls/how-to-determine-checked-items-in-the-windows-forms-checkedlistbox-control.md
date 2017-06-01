---
title: "Gewusst wie: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement von Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kontrollkästchen, Feststellen des aktivierten Zustands"
  - "CheckedListBox-Steuerelement [Windows Forms], Feststellen des aktivierten Zustands"
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement von Windows&#160;Forms
Wenn Daten in einem <xref:System.Windows.Forms.CheckedListBox>\-Steuerelement von Windows Forms dargestellt werden, können Sie die in der <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>\-Eigenschaft gespeicherte Auflistung durchgehen oder die Liste schrittweise mit der <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>\-Methode durcharbeiten, um zu bestimmen, welche Elemente aktiviert sind.  Die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>\-Methode verwendet eine Elementindexnummer als Argument und gibt `true` oder `false` zurück.  Anders als der Name vermuten lässt, bestimmen die <xref:System.Windows.Forms.ListBox.SelectedItems%2A>\-Eigenschaft und <xref:System.Windows.Forms.ListBox.SelectedIndices%2A>\-Eigenschaft nicht die Elemente, die aktiviert werden, sondern die Elemente, die hervorgehoben werden.  
  
### So bestimmen Sie die aktivierten Elemente in einem CheckedListBox\-Steuerelement  
  
1.  Gehen Sie die <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>\-Auflistung schrittweise durch. Sie beginnen dabei mit 0, da die Auflistung nullbasiert ist.  Beachten Sie, dass diese Methode die Elementnummer in der Liste der aktivierten Elemente angibt, nicht die der Gesamtliste.  Demnach zeigt der untenstehende Code den Text "Checked Item 1 \= MyListItem2" an, wenn das zweite Element in der Liste aktiviert ist und das erste nicht.  
  
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
  
     – oder –  
  
2.  Gehen Sie die <xref:System.Windows.Forms.CheckedListBox.Items%2A>\-Auflistung schrittweise durch. Beginnen Sie dabei mit 0, da die Auflistung nullbasiert ist, und rufen Sie bei jedem Element die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>\-Methode auf.  Beachten Sie, dass diese Methode die Elementnummer in der Gesamtliste zurückgibt. Wenn also das zweite Element in der Liste aktiviert ist und das erste nicht, zeigt der Code "Item 2 \= MyListItem2" an.  
  
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
  
## Siehe auch  
 [Steuerelemente in Windows Forms zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)