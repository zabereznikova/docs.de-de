---
title: Hinzufügen und Entfernen von Registerkarten mit TabControl
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: 8292d8441f9b47334b98736cf3282c846673dbb4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732720"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="bb6c0-102">Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb6c0-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="bb6c0-103">Standardmäßig enthält ein <xref:System.Windows.Forms.TabControl>-Steuerelement zwei <xref:System.Windows.Forms.TabPage>-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="bb6c0-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="bb6c0-104">Sie können über die <xref:System.Windows.Forms.TabControl.TabPages%2A>-Eigenschaft auf diese Registerkarten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bb6c0-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="bb6c0-105">So fügen Sie eine Registerkarte Programm gesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="bb6c0-105">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="bb6c0-106">Verwenden Sie die <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A>-Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bb6c0-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="bb6c0-107">So entfernen Sie eine Registerkarte Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="bb6c0-107">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="bb6c0-108">Um die ausgewählten Registerkarten zu entfernen, verwenden Sie die <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A>-Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bb6c0-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="bb6c0-109">\- oder -</span><span class="sxs-lookup"><span data-stu-id="bb6c0-109">-or-</span></span>  
  
- <span data-ttu-id="bb6c0-110">Um alle Registerkarten zu entfernen, verwenden Sie die <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A>-Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bb6c0-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bb6c0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb6c0-111">See also</span></span>

- [<span data-ttu-id="bb6c0-112">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="bb6c0-112">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="bb6c0-113">Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="bb6c0-113">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="bb6c0-114">Gewusst wie: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="bb6c0-114">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="bb6c0-115">Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb6c0-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
