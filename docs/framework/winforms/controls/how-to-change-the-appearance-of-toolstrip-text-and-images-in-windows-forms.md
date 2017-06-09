---
title: "Gewusst wie: &#196;ndern der Darstellung von ToolStrip-Text und -Bildern in Windows Forms | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Symbolleisten"
  - "Symbolleisten [Windows Forms], Darstellung"
  - "Symbolleisten [Windows Forms], Bilder"
  - "Symbolleisten [Windows Forms], Text"
  - "ToolStrip-Steuerelement [Windows Forms], Darstellung"
  - "ToolStrip-Steuerelement [Windows Forms], Bilder"
  - "ToolStrip-Steuerelement [Windows Forms], Text"
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: &#196;ndern der Darstellung von ToolStrip-Text und -Bildern in Windows Forms
Sie können steuern, ob Text und Bilder auf einem <xref:System.Windows.Forms.ToolStripItem> angezeigt werden und wie sie relativ zueinander und zum <xref:System.Windows.Forms.ToolStrip> angeordnet werden.  
  
### So definieren Sie, was auf einem ToolStripItem angezeigt wird  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>\-Eigenschaft auf den gewünschten Wert fest.  Mögliche Werte sind `Image`, `ImageAndText`, `None` und `Text`.  Der Standardwert ist `ImageAndText`.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
  
    ```  
  
### So richten Sie Text auf einem ToolStripItem aus  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A>\-Eigenschaft auf den gewünschten Wert fest.  Mögliche Werte sind beliebige Kombinationen aus Oben, Mitte und Unten sowie Links, Zentriert und Rechts.  Der Standardwert ist `MiddleCenter`.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
  
    ```  
  
### So richten Sie ein Bild auf einem ToolStripItem aus  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>\-Eigenschaft auf den gewünschten Wert fest.  Mögliche Werte sind beliebige Kombinationen aus Oben, Mitte und Unten sowie Links, Zentriert und Rechts.  Der Standardwert ist `MiddleLeft`.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
  
    ```  
  
### So definieren Sie, wie ToolStripItem\-Text und \-Bilder relativ zueinander angezeigt werden  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>\-Eigenschaft auf den gewünschten Wert fest.  Mögliche Werte sind `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage` und `TextBeforeImage`.  Die Standardeinstellung ist `ImageBeforeText`.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Architektur des ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Zusammenfassung der ToolStrip\-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)