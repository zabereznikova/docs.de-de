---
title: "Gewusst wie: Hinzuf&#252;gen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "CheckedListBox-Steuerelement [Windows Forms], Hinzufügen und Entfernen von Elementen"
  - "Kombinationsfelder, Hinzufügen von Elementen"
  - "Kombinationsfelder, Entfernen von Elementen"
  - "ComboBox-Steuerelement [Windows Forms], Hinzufügen und Entfernen von Elementen"
  - "Listenfelder, Hinzufügen von Elementen"
  - "Listenfelder, Entfernen von Elementen"
  - "ListBox-Steuerelement [Windows Forms], Hinzufügen und Entfernen von Elementen"
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Hinzuf&#252;gen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows&#160;Forms
Es gibt verschiedene Möglichkeiten, Kombinationsfeldern, Listenfeldern oder aktivierten Listenfeldern in Windows Forms Elemente hinzuzufügen, da diese Steuerelemente an verschiedene Datenquellen gebunden werden können.  Hier wird jedoch die einfachste Methode beschrieben, die keine Datenbindung voraussetzt.  Bei den angezeigten Elementen handelt es sich normalerweise um Zeichenfolgen, es können jedoch beliebige Objekte verwendet werden.  Der im Steuerelement angezeigte Text ist der Wert, der von der `ToString` \-Methode des Objekts zurückgegeben wird.  
  
### So fügen Sie Elemente hinzu  
  
1.  Fügen Sie die Zeichenfolge oder das Objekt mit der `Add`\-Methode der `ObjectCollection`\-Klasse zu der Liste hinzu.  Mit der `Items` \-Eigenschaft wird auf die Auflistung verwiesen:  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     – oder –  
  
2.  Fügen Sie die Zeichenfolge oder das Objekt mit der `Insert` \-Methode an der gewünschten Stelle in der Liste ein:  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     – oder –  
  
3.  Weisen Sie der `Items` \-Auflistung ein ganzes Array zu:  
  
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
  
### So entfernen Sie ein Element  
  
1.  Rufen Sie zum Löschen von Elementen die `Remove` \-Methode oder die `RemoveAt` \-Methode auf.  
  
     `Remove`  verfügt über ein Argument, das das zu entfernende Element angibt. `RemoveAt`  entfernt das Element mit der angegebenen Indexnummer.  
  
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
  
### So entfernen Sie alle Elemente  
  
1.  Rufen Sie die `Clear`\-Methode auf, um alle Elemente aus der Auflistung zu entfernen:  
  
    ```vb  
    ListBox1.Items.Clear()  
  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [Gewusst wie: Sortieren des Inhalts eines ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [Steuerelemente in Windows Forms zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)