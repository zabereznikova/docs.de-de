---
title: "Gewusst wie: Deaktivieren von ToolStripMenuItems | Microsoft Docs"
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
  - "Deaktivieren von Menüelementen"
  - "Menüelemente, Deaktivieren"
  - "Menüelemente, Aktivieren"
  - "Menüs, Deaktivieren von Menüelementen"
  - "ToolStripMenuItems, Deaktivieren"
  - "ToolStripMenuItems, Aktivieren"
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Deaktivieren von ToolStripMenuItems
Sie können die Befehle, die ein Benutzer ausführen kann, einschränken oder erweitern, indem Sie Menüelemente bei bestimmten Benutzeraktivitäten aktivieren oder deaktivieren.  Menüelemente sind bei der Erstellung standardmäßig aktiviert. Sie können diesen Zustand jedoch mithilfe der <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>\-Eigenschaft anpassen.  Diese Eigenschaft kann zur Entwurfszeit im **Eigenschaftenfenster** oder programmgesteuert über entsprechende Codeanweisungen geändert werden.  
  
### So deaktivieren Sie ein Menüelement programmgesteuert  
  
-   Fügen Sie in der Methode, in der Sie die Eigenschaften des Menüelements festlegen, Code hinzu, um die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>\-Eigenschaft auf `false` festzulegen.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  Durch Deaktivieren des ersten oder obersten Menüelements in einem Menü werden sämtliche Menüelemente im betreffenden Menü ausgeblendet, jedoch nicht deaktiviert.  Entsprechend werden durch Deaktivieren eines Menüelements mit Untermenüelementen die Untermenüelemente ausgeblendet, aber nicht deaktiviert.  Wenn der Benutzer keinen der Befehle in einem bestimmten Menü ausführen kann, sollte das gesamte Menü durch eine entsprechende Programmierung ausgeblendet und deaktiviert werden, um die Benutzeroberfläche übersichtlicher zu gestalten.  Sie sollten das Menü ausblenden und deaktivieren sowie jedes Element und Untermenüelement im Menü deaktivieren, da beim alleinigen Ausblenden nicht der Zugriff per Tastenkombination auf einen Menübefehl verhindert wird.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A>\-Eigenschaft eines Menüelements der obersten Ebene auf `false` fest, um das ganze Menü auszublenden.  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Gewusst wie: Ausblenden von ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)