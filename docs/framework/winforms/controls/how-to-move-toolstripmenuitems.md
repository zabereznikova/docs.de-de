---
title: "Gewusst wie: Verschieben von ToolStripMenuItems | Microsoft Docs"
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
  - "Menüelemente, Ausschneiden und Einfügen"
  - "Menüelemente, Ziehen und Ablegen"
  - "Menüelemente, Verschieben"
  - "Menüs, Anordnen von Elementen"
  - "MenuStrip-Steuerelement [Windows Forms], Anordnen von Elementen"
  - "ToolStripMenuItems, Ausschneiden und Einfügen"
  - "ToolStripMenuItems, Ziehen und Ablegen"
  - "ToolStripMenuItems, Verschieben"
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Verschieben von ToolStripMenuItems
Zur Entwurfszeit können Sie komplette Menüs der obersten Ebene und ihre Menüelemente an eine andere Stelle im <xref:System.Windows.Forms.MenuStrip> verschieben.  Außerdem können Sie einzelne Menüelemente zwischen Menüs der obersten Ebene verschieben oder die Position von Menüelementen in einem Menü ändern.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So verschieben Sie ein Menü der obersten Ebene und seine Menüelemente an eine andere Stelle der obersten Ebene  
  
1.  Klicken Sie, und halten Sie die linke Maustaste auf dem Menü gedrückt, das Sie verschieben möchten.  
  
2.  Ziehen Sie die Einfügemarke zu dem Menü der obersten Ebene, das sich vor der gewünschten Position befindet, und lassen Sie die linke Maustaste los.  
  
     Das ausgewählte Menü wird rechts neben der Einfügemarke verschoben.  
  
### So verschieben Sie ein Menü der obersten Ebene und seine Menüelemente an eine Dropdownposition  
  
1.  Klicken Sie mit der linken Maustaste auf das Menü, das Sie verschieben möchten, und drücken Sie STRG\+X, oder klicken Sie mit der rechten Maustaste auf das Menü, und wählen Sie im Kontextmenü **Ausschneiden** aus.  
  
2.  Klicken Sie im Zielmenü der obersten Ebene mit der linken Maustaste auf das Menüelement, das sich über der gewünschten Position befindet, und drücken Sie STRG\+V, oder klicken Sie mit der rechten Maustaste auf das Menüelement, das sich über der gewünschten Position befindet, und wählen Sie im Kontextmenü **Einfügen** aus.  
  
     Das ausgeschnittene Menü wird nach dem ausgewählten Menüelement eingefügt.  
  
### So verschieben Sie ein Menüelement innerhalb eines Menüs mit dem Elementauflistungs\-Editor  
  
1.  Klicken Sie mit der rechten Maustaste auf das Menü, in dem das Menüelement enthalten ist, das Sie verschieben möchten.  
  
2.  Wählen Sie im Kontextmenü **DropDownItems bearbeiten** aus.  
  
3.  Klicken Sie im **Elementauflistungs\-Editor** mit der linken Maustaste auf das Menüelement, das Sie verschieben möchten.  
  
4.  Drücken Sie die NACH\-OBEN\- und die NACH UNTEN\-PFEILTASTE, um das Menüelement innerhalb des Menüs zu verschieben.  
  
5.  Klicken Sie auf **OK**.  
  
### So verschieben Sie ein Menüelement innerhalb eines Menüs mit der Tastatur  
  
1.  Drücken Sie die ALT\-TASTE, und halten Sie sie gedrückt.  
  
2.  Klicken Sie, und halten Sie die linke Maustaste auf dem Menüelement gedrückt, das Sie verschieben möchten.  
  
3.  Ziehen Sie das Menüelement an die neue Position, und lassen Sie die linke Maustaste los.  
  
### So verschieben Sie ein Menüelement in ein anderes Menü  
  
1.  Klicken Sie mit der linken Maustaste auf das Menüelement, das Sie verschieben möchten, und drücken Sie STRG\+X, oder klicken Sie mit der rechten Maustaste auf das Menüelement, und wählen Sie im Kontextmenü **Ausschneiden** aus.  
  
2.  Klicken Sie mit der linken Maustaste auf das Menü, das das ausgeschnittene Menüelement enthalten soll.  
  
3.  Klicken Sie mit der linken Maustaste auf das Menüelement, das sich vor der gewünschten Position befindet, und drücken Sie STRG\+V, oder klicken Sie mit der rechten Maustaste auf das Menüelement, das sich vor der gewünschten Position befindet, und wählen Sie im Kontextmenü **Einfügen** aus.  
  
     Das ausgeschnittene Menüelement wird nach dem ausgewählten Menüelement eingefügt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)