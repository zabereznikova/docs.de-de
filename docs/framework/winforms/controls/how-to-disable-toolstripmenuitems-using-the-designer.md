---
title: "Gewusst wie: Deaktivieren von ToolStripMenuItems mithilfe des Designers | Microsoft Docs"
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
  - "Menüelemente, Deaktivieren"
  - "Menüs, Deaktivieren von Elementen"
  - "MenuStrip-Steuerelement [Windows Forms], Deaktivieren von Menüelementen im Designer"
  - "ToolStripMenuItems, Deaktivieren im Designer"
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Deaktivieren von ToolStripMenuItems mithilfe des Designers
Sie können die Befehle, die ein Benutzer ausführen kann, einschränken oder erweitern, indem Sie Menüelemente bei bestimmten Benutzeraktivitäten aktivieren oder deaktivieren.  Menüelemente sind bei der Erstellung standardmäßig aktiviert. Sie können diesen Zustand jedoch mithilfe der <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>\-Eigenschaft anpassen.  Diese Eigenschaft kann zur Entwurfszeit im **Eigenschaftenfenster** oder programmgesteuert über entsprechende Codeanweisungen geändert werden.  Weitere Informationen hierzu finden Sie unter [Gewusst wie: Deaktivieren von ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So deaktivieren Sie ein Menüelement zur Entwurfszeit  
  
1.  Wählen Sie das Menüelement auf dem Formular aus, und legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>\-Eigenschaft auf `false` fest.  
  
    > [!TIP]
    >  Wenn Sie das erste bzw. das Menüelement der obersten Ebene in einem Menü deaktivieren, werden alle in dem Menü enthaltenen Menüelemente deaktiviert.  Entsprechend werden durch das Deaktivieren eines Menüelements, das Untermenüelemente aufweist, diese Untermenüelemente deaktiviert.  Wenn der Benutzer keinen der Befehle in einem bestimmten Menü ausführen kann, sollte das gesamte Menü durch eine entsprechende Programmierung ausgeblendet und deaktiviert werden, um die Benutzeroberfläche übersichtlicher zu gestalten.  Sie sollten das Menü ausblenden und deaktivieren, da der Zugriff auf einen Menübefehl über eine Tastenkombination durch das bloße Ausblenden nicht verhindert wird.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A>\-Eigenschaft eines Menüelements der obersten Ebene auf `false` fest, um das ganze Menü auszublenden.  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Gewusst wie: Ausblenden von ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)