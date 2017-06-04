---
title: "Gewusst wie: Hinzuf&#252;gen von Men&#252;elementen zu einem ContextMenuStrip | Microsoft Docs"
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
  - "Kontextmenüs, Hinzufügen von Menüelementen"
  - "ContextMenuStrips, Hinzufügen von Menüelementen"
  - "Kontextmenüs, Hinzufügen von Elementen"
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Hinzuf&#252;gen von Men&#252;elementen zu einem ContextMenuStrip
Einem <xref:System.Windows.Forms.ContextMenuStrip> können sowohl ein einzelnes als auch mehrere Menüelemente gleichzeitig hinzugefügt werden.  
  
### So fügen Sie einem ContextMenuStrip ein einzelnes Menüelement hinzu  
  
-   Verwenden Sie die <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>\-Methode, um einem <xref:System.Windows.Forms.ContextMenuStrip> ein einzelnes Menüelement hinzuzufügen.  
  
     \[Visual Basic\]  
  
    ```  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### So fügen Sie einem ContextMenuStrip mehrere Menüelemente hinzu  
  
-   Verwenden Sie die <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> \-Methode, um einem <xref:System.Windows.Forms.ContextMenuStrip> mehrere Menüelemente hinzuzufügen.  
  
     \[Visual Basic\]  
  
    ```  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## Siehe auch  
 [ContextMenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)