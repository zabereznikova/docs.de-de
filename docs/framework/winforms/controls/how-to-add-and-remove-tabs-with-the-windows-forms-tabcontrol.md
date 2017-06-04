---
title: "Gewusst wie: Hinzuf&#252;gen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Registerkarten"
  - "TabControl-Steuerelement [Windows Forms], Hinzufügen und Entfernen von Registerkarten"
  - "TabPage-Steuerelement"
  - "Registerkarten, Hinzufügen zu Seiten"
  - "Registerkarten, Entfernen aus Seiten"
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Hinzuf&#252;gen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows&#160;Forms
Standardmäßig enthält ein <xref:System.Windows.Forms.TabControl>\-Steuerelement zwei <xref:System.Windows.Forms.TabPage>\-Steuerelemente.  Sie können über die <xref:System.Windows.Forms.TabControl.TabPages%2A>\-Eigenschaft auf diese Registerkarten zugreifen.  
  
### So fügen Sie eine Registerkarte programmgesteuert hinzu  
  
-   Verwenden Sie die <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A>\-Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A>\-Eigenschaft.  
  
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
  
### So entfernen Sie eine Registerkarte programmgesteuert  
  
-   Um ausgewählte Registerkarten zu entfernen, verwenden Sie die <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A>\-Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A>\-Eigenschaft.  
  
     \- oder \-  
  
-   Um alle Registerkarten zu entfernen, verwenden Sie die <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A>\-Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A>\-Eigenschaft.  
  
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
  
## Siehe auch  
 [Übersicht über das TabControl\-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Gewusst wie: Deaktivieren von Registerkarten](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Gewusst wie: Ändern der Darstellung der TabControl\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)