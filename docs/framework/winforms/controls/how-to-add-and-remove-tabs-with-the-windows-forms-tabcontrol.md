---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms'
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
ms.openlocfilehash: eb3c59a29c9539bcba8827e1a1e9ea807ed44826
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640740"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="b1bc3-102">Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1bc3-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="b1bc3-103">Standardmäßig eine <xref:System.Windows.Forms.TabControl> Steuerelement enthält zwei <xref:System.Windows.Forms.TabPage> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="b1bc3-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="b1bc3-104">Sie können auf zugreifen, diese mit der Tabulatortaste die <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b1bc3-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="b1bc3-105">Programmgesteuertes Hinzufügen eine Registerkarte</span><span class="sxs-lookup"><span data-stu-id="b1bc3-105">To add a tab programmatically</span></span>  
  
-   <span data-ttu-id="b1bc3-106">Verwenden der <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b1bc3-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="b1bc3-107">Das programmgesteuerte Entfernen von einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="b1bc3-107">To remove a tab programmatically</span></span>  
  
-   <span data-ttu-id="b1bc3-108">Verwenden Sie zum Entfernen ausgewählte Registerkarten der <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b1bc3-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="b1bc3-109">- oder - </span><span class="sxs-lookup"><span data-stu-id="b1bc3-109">-or-</span></span>  
  
-   <span data-ttu-id="b1bc3-110">Verwenden Sie zum Entfernen aller Registerkarten der <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b1bc3-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b1bc3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1bc3-111">See also</span></span>
- [<span data-ttu-id="b1bc3-112">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b1bc3-112">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="b1bc3-113">Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="b1bc3-113">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="b1bc3-114">Vorgehensweise: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="b1bc3-114">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)
- [<span data-ttu-id="b1bc3-115">Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1bc3-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
