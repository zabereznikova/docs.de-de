---
title: Hinzufügen und Entfernen von Registerkarten mit TabControl
description: Erfahren Sie, wie Sie Registerkarten mit dem Windows Forms TabControl-Steuerelement hinzufügen und entfernen, das zwei TabPage-Steuerelemente enthält. Greifen Sie über die TabPages-Eigenschaft auf diese Registerkarten zu.
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
ms.openlocfilehash: 7e67d0bbc13bd7d9c8835dc6fb9b9c5c9333b8bf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618076"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="bd735-104">Vorgehensweise: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd735-104">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="bd735-105">Standardmäßig enthält ein- <xref:System.Windows.Forms.TabControl> Steuerelement zwei-Steuer <xref:System.Windows.Forms.TabPage> Elemente.</span><span class="sxs-lookup"><span data-stu-id="bd735-105">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="bd735-106">Sie können über die-Eigenschaft auf diese Registerkarten zugreifen <xref:System.Windows.Forms.TabControl.TabPages%2A> .</span><span class="sxs-lookup"><span data-stu-id="bd735-106">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="bd735-107">So fügen Sie eine Registerkarte Programm gesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="bd735-107">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="bd735-108">Verwenden Sie die- <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> Methode der- <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bd735-108">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="bd735-109">So entfernen Sie eine Registerkarte Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="bd735-109">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="bd735-110">Um die ausgewählten Registerkarten zu entfernen, verwenden Sie die- <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> Methode der- <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bd735-110">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="bd735-111">- oder -</span><span class="sxs-lookup"><span data-stu-id="bd735-111">-or-</span></span>  
  
- <span data-ttu-id="bd735-112">Um alle Registerkarten zu entfernen, verwenden Sie die- <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> Methode der- <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bd735-112">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bd735-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd735-113">See also</span></span>

- [<span data-ttu-id="bd735-114">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="bd735-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="bd735-115">Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="bd735-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="bd735-116">Vorgehensweise: Deaktivieren von Registerkartenseiten</span><span class="sxs-lookup"><span data-stu-id="bd735-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="bd735-117">Vorgehensweise: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd735-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
