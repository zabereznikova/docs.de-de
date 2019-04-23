---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 723e05803b1f7d2bc56476248987085dbe5e23f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101600"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="82301-102">Vorgehensweise: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="82301-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="82301-103">Standardmäßig eine <xref:System.Windows.Forms.TabControl> Steuerelement enthält zwei <xref:System.Windows.Forms.TabPage> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="82301-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="82301-104">Sie können auf zugreifen, diese mit der Tabulatortaste die <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="82301-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="82301-105">Programmgesteuertes Hinzufügen eine Registerkarte</span><span class="sxs-lookup"><span data-stu-id="82301-105">To add a tab programmatically</span></span>  
  
-   <span data-ttu-id="82301-106">Verwenden der <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="82301-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="82301-107">Das programmgesteuerte Entfernen von einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="82301-107">To remove a tab programmatically</span></span>  
  
-   <span data-ttu-id="82301-108">Verwenden Sie zum Entfernen ausgewählte Registerkarten der <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="82301-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="82301-109">- oder - </span><span class="sxs-lookup"><span data-stu-id="82301-109">-or-</span></span>  
  
-   <span data-ttu-id="82301-110">Verwenden Sie zum Entfernen aller Registerkarten der <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="82301-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82301-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82301-111">See also</span></span>

- [<span data-ttu-id="82301-112">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="82301-112">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="82301-113">Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="82301-113">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="82301-114">Vorgehensweise: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="82301-114">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="82301-115">Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="82301-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
