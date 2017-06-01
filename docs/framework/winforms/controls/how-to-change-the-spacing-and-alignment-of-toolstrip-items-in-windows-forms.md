---
title: "Gewusst wie: &#196;ndern der Abst&#228;nde und der Ausrichtung der ToolStrip-Elemente in Windows Forms | Microsoft Docs"
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
  - "Symbolleisten [Windows Forms], Ausrichten von Elementen"
  - "ToolStrip-Steuerelement [Windows Forms], Ausrichten von Elementen"
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: &#196;ndern der Abst&#228;nde und der Ausrichtung der ToolStrip-Elemente in Windows Forms
Das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement unterstützt vollständig Layoutfeatures wie Größenanpassung, die relativen Abstände von <xref:System.Windows.Forms.ToolStripItem>\-Steuerelementen zueinander, die Anordnung von Steuerelementen auf dem <xref:System.Windows.Forms.ToolStrip> und die relativen Abstände von Steuerelementen zum <xref:System.Windows.Forms.ToolStrip>.  
  
 Da der Standardwert der <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>\-Eigenschaft `true` ist, wird die Größe von Steuerelementen automatisch angepasst, sofern Sie die <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>\-Eigenschaft nicht auf `false` festlegen.  
  
### So passen Sie manuell die Größe eines ToolStripItem an  
  
1.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>\-Eigenschaft für das zugeordnete Steuerelement auf `false` fest.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
  
    ```  
  
2.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Size%2A>\-Eigenschaft für das zugeordnete <xref:System.Windows.Forms.ToolStripItem> wie gewünscht fest.  
  
### So legen Sie den Abstand eines ToolStripItem fest  
  
1.  Fügen Sie die gewünschten Werte in Pixel in die <xref:System.Windows.Forms.ToolStripItem.Margin%2A>\-Eigenschaft des zugeordneten Steuerelements ein.  
  
     Durch die Werte der <xref:System.Windows.Forms.ToolStripItem.Margin%2A>\-Eigenschaft wird der Abstand zwischen einem Element und seinen benachbarten Elementen in folgender Reihenfolge festgelegt: links, oben, rechts, unten.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
  
    ```  
  
### So richten Sie ein "ToolStripItem" rechts vom "ToolStrip" aus  
  
1.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>\-Eigenschaft für das zugeordnete Steuerelement auf <xref:System.Windows.Forms.ToolStripItemAlignment> fest.  In der Standardeinstellung ist <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> auf <xref:System.Windows.Forms.ToolStripItemAlignment> festgelegt, wodurch Steuerelemente links vom <xref:System.Windows.Forms.ToolStrip> ausgerichtet werden.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
  
    ```  
  
### So ordnen Sie ToolStrip\-Elemente auf dem ToolStrip an  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>\-Eigenschaft auf den gewünschten Wert von <xref:System.Windows.Forms.ToolStripLayoutStyle> fest.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.Control.Layout>   
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>   
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>   
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>   
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>   
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Architektur des ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Zusammenfassung der ToolStrip\-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)