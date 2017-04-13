---
title: "Gewusst wie: Ausblenden von ToolStripMenuItems | Microsoft Docs"
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
  - "Ausblenden von Menüelementen"
  - "Menüelemente, Ausblenden"
  - "Menüs, Ausblenden von Menüelementen"
  - "MenuStrip-Steuerelement [Windows Forms], Ausblenden von Menüelementen"
  - "ToolStripMenuItems, Ausblenden"
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Ausblenden von ToolStripMenuItems
Durch das Ausblenden von Menüelementen können Sie die Benutzeroberfläche der Anwendung steuern und die verfügbaren Benutzerbefehle einschränken.  Häufig möchten Sie ein komplettes Menü ausblenden, wenn alle darin enthaltenen Menüelemente nicht verfügbar sind.  Dies ist weniger verwirrend für den Benutzer.  Des Weiteren möchten Sie das Menü oder Menüelement möglicherweise nicht nur ausblenden, sondern auch deaktivieren, da das Ausblenden den Benutzer nicht daran hindert, einen Menübefehl über eine Tastenkombination aufzurufen.  
  
### So blenden Sie ein Menüelement programmgesteuert aus  
  
-   Fügen Sie in der Methode, in der Sie die Eigenschaften des Menüelements festlegen, Code hinzu, um die <xref:System.Windows.Forms.ToolStripItem.Visible%2A>\-Eigenschaft auf `false` festzulegen.  
  
    ```vb  
    MenuItem3.Visible = False  
  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>   
 <xref:System.Windows.Forms.MenuStrip>   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)   
 [Gewusst wie: Deaktivieren von ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)