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
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="86da5-102">Gewusst wie: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86da5-102">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="86da5-103">Wenn Sie Daten in <xref:System.Windows.Forms.CheckedListBox> einem Windows Forms-Steuerelement darstellen, können <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> Sie entweder die in der <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> Eigenschaft gespeicherte Auflistung durchlaufen oder die Liste mithilfe der Methode durchlaufen, um zu bestimmen, welche Elemente überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="86da5-103">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="86da5-104">Die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> Methode nimmt eine Elementindexnummer `true` als `false`Argument und gibt oder zurück.</span><span class="sxs-lookup"><span data-stu-id="86da5-104">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="86da5-105">Im Gegensatz zu dem, <xref:System.Windows.Forms.ListBox.SelectedItems%2A> <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> was Sie erwarten, bestimmen die und Eigenschaften nicht, welche Elemente überprüft werden. sie bestimmen, welche Elemente hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="86da5-105">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="86da5-106">So ermitteln Sie geprüfte Elemente in einem CheckedListBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="86da5-106">To determine checked items in a CheckedListBox control</span></span>  
  
1. <span data-ttu-id="86da5-107">Durchlaufen der <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> Auflistung, beginnend bei 0, da die Auflistung auf Null basiert.</span><span class="sxs-lookup"><span data-stu-id="86da5-107">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="86da5-108">Beachten Sie, dass diese Methode Ihnen die Artikelnummer in der Liste der geprüften Elemente und nicht die Gesamtliste angibt.</span><span class="sxs-lookup"><span data-stu-id="86da5-108">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="86da5-109">Wenn also das erste Element in der Liste nicht aktiviert ist und das zweite Element aktiviert ist, wird der folgende Code Text wie "Checked Item 1 = MyListItem2" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86da5-109">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
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
  
     - <span data-ttu-id="86da5-110">oder –</span><span class="sxs-lookup"><span data-stu-id="86da5-110">or -</span></span>  
  
2. <span data-ttu-id="86da5-111">Gehen Sie <xref:System.Windows.Forms.CheckedListBox.Items%2A> durch die Auflistung, beginnend bei 0, da <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> die Auflistung nullbasiert ist, und rufen Sie die Methode für jedes Element auf.</span><span class="sxs-lookup"><span data-stu-id="86da5-111">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="86da5-112">Beachten Sie, dass diese Methode Ihnen die Artikelnummer in der Gesamtliste gibt, wenn also das erste Element in der Liste nicht aktiviert ist und das zweite Element aktiviert ist, wird etwa "Artikel 2 = MyListItem2" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86da5-112">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="86da5-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86da5-113">See also</span></span>

- [<span data-ttu-id="86da5-114">Steuerelemente in Windows Forms zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="86da5-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
