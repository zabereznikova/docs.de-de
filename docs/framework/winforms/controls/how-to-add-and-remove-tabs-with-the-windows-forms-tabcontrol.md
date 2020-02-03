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
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms
Standardmäßig enthält ein <xref:System.Windows.Forms.TabControl>-Steuerelement zwei <xref:System.Windows.Forms.TabPage>-Steuerelemente. Sie können über die <xref:System.Windows.Forms.TabControl.TabPages%2A>-Eigenschaft auf diese Registerkarten zugreifen.  
  
### <a name="to-add-a-tab-programmatically"></a>So fügen Sie eine Registerkarte Programm gesteuert hinzu  
  
- Verwenden Sie die <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A>-Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A>-Eigenschaft.  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a>So entfernen Sie eine Registerkarte Programm gesteuert  
  
- Um die ausgewählten Registerkarten zu entfernen, verwenden Sie die <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A>-Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A>-Eigenschaft.  
  
     Oder  
  
- Um alle Registerkarten zu entfernen, verwenden Sie die <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A>-Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A>-Eigenschaft.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über das TabControl-Steuerelement](tabcontrol-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte](how-to-add-a-control-to-a-tab-page.md)
- [Gewusst wie: Deaktivieren von Registerkarten](how-to-disable-tab-pages.md)
- [Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
