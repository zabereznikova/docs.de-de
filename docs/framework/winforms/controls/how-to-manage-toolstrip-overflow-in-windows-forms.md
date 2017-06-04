---
title: "Gewusst wie: Umgang mit dem ToolStrip-&#220;berlauf in Windows Forms | Microsoft Docs"
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
  - "CanOverflow-Eigenschaft"
  - "Beispiele [Windows Forms], Symbolleisten"
  - "Overflow-Eigenschaft"
  - "Symbolleisten [Windows Forms], Verwalten von Überlauf"
  - "ToolStrip-Steuerelement [Windows Forms], Verwalten von Überlauf"
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Umgang mit dem ToolStrip-&#220;berlauf in Windows Forms
Wenn nicht alle Elemente in einem <xref:System.Windows.Forms.ToolStrip>\-Steuerelement in den zugewiesenen Bereich passen, können Sie die Überlauffunktion auf dem <xref:System.Windows.Forms.ToolStrip> aktivieren und das Überlaufverhalten bestimmter <xref:System.Windows.Forms.ToolStripItem>\-Elemente bestimmen.  
  
 Wenn Sie <xref:System.Windows.Forms.ToolStripItem>\-Elemente hinzufügen, die mehr Platz benötigen, als dem <xref:System.Windows.Forms.ToolStrip> anhand der aktuellen Größe des Formulars zugewiesen wurde, wird automatisch ein <xref:System.Windows.Forms.ToolStripOverflowButton> auf dem <xref:System.Windows.Forms.ToolStrip> angezeigt.  Der <xref:System.Windows.Forms.ToolStripOverflowButton> wird angezeigt, und es werden Elemente, für die der Überlauf aktiviert wurde, in das Überlauf\-Dropdownmenü verschoben.  Dadurch können Sie anpassen und Prioritäten dafür bestimmen, wie sich die <xref:System.Windows.Forms.ToolStrip>\-Elemente ordnungsgemäß an andere Formulargrößen anpassen.  Sie können auch das Aussehen der Elemente ändern, wenn diese in den Überlauf geraten, indem Sie die <xref:System.Windows.Forms.ToolStripItem.Placement%2A>\-Eigenschaft, die <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=fullName>\-Eigenschaft und das <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>\-Ereignis verwenden.  Wenn Sie das Formular entweder zur Entwurfszeit oder zur Laufzeit vergrößern, können mehr <xref:System.Windows.Forms.ToolStripItem>\-Elemente auf dem primären <xref:System.Windows.Forms.ToolStrip> angezeigt werden, und der <xref:System.Windows.Forms.ToolStripOverflowButton> wird möglicherweise ausgeblendet, bis Sie die Größe des Formulars reduzieren.  
  
### So aktivieren Sie den Überlauf für ein ToolStrip\-Steuerelement  
  
-   Stellen Sie sicher, dass die <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>\-Eigenschaft für den <xref:System.Windows.Forms.ToolStrip> nicht auf `false` festgelegt ist.  Die Standardeinstellung ist `True`.  
  
     Wenn <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> auf `True` festgelegt ist \(die Standardeinstellung\), wird ein <xref:System.Windows.Forms.ToolStripItem> zum Überlauf\-Dropdownmenü hinzugefügt, wenn der Inhalt des <xref:System.Windows.Forms.ToolStripItem> die Breite eines horizontalen <xref:System.Windows.Forms.ToolStrip> oder die Höhe eines vertikalen <xref:System.Windows.Forms.ToolStrip> überschreitet.  
  
### So legen Sie das Überlaufverhalten eines bestimmten ToolStripItem fest  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>\-Eigenschaft des <xref:System.Windows.Forms.ToolStripItem> auf den gewünschten Wert fest.  Mögliche Werte sind `Always`, `Never` und `AsNeeded`.  Der Standardwert ist`AsNeeded`.  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripOverflowButton>   
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>   
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Architektur des ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Zusammenfassung der ToolStrip\-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)