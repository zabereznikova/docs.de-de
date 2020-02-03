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
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="855e9-102">Gewusst wie: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="855e9-102">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="855e9-103">Beim darstellen von Daten in einem Windows Forms <xref:System.Windows.Forms.CheckedListBox>-Steuerelement können Sie entweder die Auflistung durchlaufen, die in der <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>-Eigenschaft gespeichert ist, oder die Liste durchlaufen, indem Sie die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>-Methode verwenden, um zu bestimmen, welche Elemente geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="855e9-103">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="855e9-104">Die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>-Methode nimmt eine Element Indexnummer als Argument an und gibt `true` oder `false`zurück.</span><span class="sxs-lookup"><span data-stu-id="855e9-104">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="855e9-105">Anders als erwartet können die Eigenschaften <xref:System.Windows.Forms.ListBox.SelectedItems%2A> und <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> nicht bestimmen, welche Elemente geprüft werden. Sie bestimmen, welche Elemente hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="855e9-105">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="855e9-106">So bestimmen Sie aktivierte Elemente in einem CheckedListBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="855e9-106">To determine checked items in a CheckedListBox control</span></span>  
  
1. <span data-ttu-id="855e9-107">Iterieren Sie die <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> Auflistung, beginnend bei 0, da die Auflistung NULL basiert.</span><span class="sxs-lookup"><span data-stu-id="855e9-107">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="855e9-108">Beachten Sie, dass diese Methode die Element Nummer in der Liste der aktivierten Elemente und nicht die Gesamtliste enthält.</span><span class="sxs-lookup"><span data-stu-id="855e9-108">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="855e9-109">Wenn das erste Element in der Liste nicht aktiviert ist und das zweite Element aktiviert ist, zeigt der nachfolgende Code z. b. Text wie "aktiviertes Element 1 = MyListItem2" an.</span><span class="sxs-lookup"><span data-stu-id="855e9-109">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
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
  
     - <span data-ttu-id="855e9-110">oder –</span><span class="sxs-lookup"><span data-stu-id="855e9-110">or -</span></span>  
  
2. <span data-ttu-id="855e9-111">Durchlaufen Sie die <xref:System.Windows.Forms.CheckedListBox.Items%2A> Auflistung, beginnend bei 0, da die Auflistung NULL basiert, und nennen Sie die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>-Methode für jedes Element.</span><span class="sxs-lookup"><span data-stu-id="855e9-111">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="855e9-112">Beachten Sie, dass diese Methode die Element Nummer in der Gesamtliste enthält. wenn das erste Element in der Liste nicht aktiviert und das zweite Element aktiviert ist, wird etwa "Item 2 = MyListItem2" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="855e9-112">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="855e9-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="855e9-113">See also</span></span>

- [<span data-ttu-id="855e9-114">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="855e9-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
