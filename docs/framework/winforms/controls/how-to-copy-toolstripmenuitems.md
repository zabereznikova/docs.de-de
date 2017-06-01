---
title: "Gewusst wie: Kopieren von ToolStripMenuItems | Microsoft Docs"
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
  - "Menüelemente, kopieren und einfügen"
  - "MenuStrip-Steuerelement [Windows Forms], Anordnen von Elementen"
  - "ToolStripMenuItems, kopieren und einfügen"
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Kopieren von ToolStripMenuItems
Zur Entwurfszeit können Sie ganze Menüs der obersten Ebene und ihre Untermenüelemente an eine andere Stelle auf dem <xref:System.Windows.Forms.MenuStrip> kopieren. Die können auch einzelne Menüelemente zwischen Menüs der obersten Ebene kopieren oder die Position von Menüelementen innerhalb eines Menüs ändern.  
  
### So kopieren Sie ein Menü der obersten Ebene und seine Untermenüelemente an eine andere Position der obersten Ebene  
  
1.  Klicken Sie mit der linken Maustaste auf das Menü, das Sie kopieren möchten, und drücken Sie STRG\+C, oder klicken Sie mit der rechten Maustaste, und wählen Sie **Kopieren** aus dem Kontextmenü aus.  
  
2.  Klicken Sie mit der linken Maustaste auf das Menü der obersten Ebene, das sich hinter der beabsichtigten neuen Position befindet, und drücken Sie STRG\+V, oder klicken Sie mit der rechten Maustaste auf das Menüelement der obersten Ebene, das sich vor der beabsichtigten neuen Position befindet, und wählen Sie **Einfügen** aus dem Kontextmenü aus.  
  
     Das kopierte Menü wird vor dem ausgewählten Menü der obersten Ebene eingefügt.  
  
### So kopieren Sie ein Menü der obersten Ebene und seine Untermenüelemente an einen Ablageort  
  
1.  Klicken Sie mit der linken Maustaste auf das Menü, das Sie verschieben möchten, und drücken Sie STRG\+C, oder klicken Sie mit der rechten Maustaste, und wählen Sie **Kopieren** aus dem Kontextmenü aus.  
  
2.  Klicken Sie im Zielmenü der obersten Ebene mit der linken Maustaste auf das Untermenüelement, das sich oberhalb der beabsichtigten neuen Position befindet, und drücken Sie STRG\+V, oder klicken Sie mit der rechten Maustaste auf das Untermenüelement, das sich oberhalb der beabsichtigten neuen Position befindet,und wählen Sie aus dem Kontextmenü **Einfügen** aus.  
  
     Das kopierte Menü wird vor dem ausgewählten Untermenüelement eingefügt.  
  
### So kopieren Sie ein Untermenüelement in ein anderes Menü  
  
1.  Klicken Sie mit der linken Maustaste auf das Untermenüelement, das Sie kopieren möchten, und drücken Sie STRG\+C, oder klicken Sie mit der rechten Maustaste auf das Untermenüelement, und wählen Sie **Kopieren** aus dem Kontextmenü aus.  
  
2.  Klicken Sie mit der linken Maustaste auf das Menü, das das ausgeschnittene Untermenüelement aufnehmen soll.  
  
3.  Klicken Sie mit der linken Maustaste auf das Untermenüelement, das sich vor der beabsichtigten neuen Position befindet, und drücken Sie STRG\+V, oder klicken Sie mit der rechten Maustaste auf das Untermenüelement, das sich vor der beabsichtigten neuen Position befindet, und wählen Sie **Einfügen** aus dem Kontextmenü aus.  
  
     Das kopierte Untermenüelement wird vor dem ausgewählten Untermenüelement eingefügt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)