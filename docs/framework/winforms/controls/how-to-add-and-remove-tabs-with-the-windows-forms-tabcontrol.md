---
title: 'Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 938dbb4ae695f22d6daff417fbf7176800420aae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525603"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms
Wird standardmäßig ein <xref:System.Windows.Forms.TabControl> Steuerelement enthält zwei <xref:System.Windows.Forms.TabPage> Steuerelemente. Sie können auf diesen Registerkarten über zugreifen die <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.  
  
### <a name="to-add-a-tab-programmatically"></a>So fügen Sie eine Registerkarte programmgesteuert hinzu  
  
-   Verwenden der <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a>So entfernen Sie eine Registerkarte programmgesteuert  
  
-   Verwenden Sie zum Entfernen ausgewählte Registerkarten der <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.  
  
     - oder -   
  
-   Verwenden Sie zum Entfernen aller Registerkarten der <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das TabControl-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [Gewusst wie: Deaktivieren von Registerkarten](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
