---
title: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement
description: Erfahren Sie, wie Sie überprüfte Elemente im Windows Forms CheckedListBox-Steuerelement ermitteln, indem Sie die Auflistung durchlaufen, die in der CheckedItems-Eigenschaft gespeichert ist.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: fd8845ef83da7406ff4f1468506a23e3f4d386a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618349"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="98339-103">Vorgehensweise: Bestimmen der aktivierten Elemente im CheckedListBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="98339-103">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="98339-104">Wenn Sie Daten in einem Windows Forms-Steuerelement darstellen <xref:System.Windows.Forms.CheckedListBox> , können Sie entweder die in der-Eigenschaft gespeicherte Auflistung durchlaufen <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> oder die Liste durchlaufen, indem Sie die-Methode verwenden, <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> um zu bestimmen, welche Elemente geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="98339-104">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="98339-105">Die <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> -Methode nimmt eine Element Indexnummer als Argument an und gibt `true` oder zurück `false` .</span><span class="sxs-lookup"><span data-stu-id="98339-105">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="98339-106">Im Gegensatz zu dem, was Sie möglicherweise erwarten, <xref:System.Windows.Forms.ListBox.SelectedItems%2A> bestimmen die-und- <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> Eigenschaften nicht, welche Elemente geprüft werden. Sie legen fest, welche Elemente hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="98339-106">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="98339-107">So bestimmen Sie aktivierte Elemente in einem CheckedListBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="98339-107">To determine checked items in a CheckedListBox control</span></span>  
  
1. <span data-ttu-id="98339-108">Iterieren Sie die Auflistung <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> , beginnend bei 0, da die Auflistung NULL basiert.</span><span class="sxs-lookup"><span data-stu-id="98339-108">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="98339-109">Beachten Sie, dass diese Methode die Element Nummer in der Liste der aktivierten Elemente und nicht die Gesamtliste enthält.</span><span class="sxs-lookup"><span data-stu-id="98339-109">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="98339-110">Wenn das erste Element in der Liste nicht aktiviert ist und das zweite Element aktiviert ist, zeigt der nachfolgende Code z. b. Text wie "aktiviertes Element 1 = MyListItem2" an.</span><span class="sxs-lookup"><span data-stu-id="98339-110">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
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
  
     - <span data-ttu-id="98339-111">ODER</span><span class="sxs-lookup"><span data-stu-id="98339-111">or -</span></span>  
  
2. <span data-ttu-id="98339-112">Durchlaufen Sie die Auflistung <xref:System.Windows.Forms.CheckedListBox.Items%2A> , beginnend bei 0, da die Auflistung NULL basiert ist, und die- <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> Methode für jedes Element aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="98339-112">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="98339-113">Beachten Sie, dass diese Methode die Element Nummer in der Gesamtliste enthält. wenn das erste Element in der Liste nicht aktiviert und das zweite Element aktiviert ist, wird etwa "Item 2 = MyListItem2" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98339-113">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98339-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98339-114">See also</span></span>

- [<span data-ttu-id="98339-115">Steuerelemente in Windows Forms zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="98339-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
