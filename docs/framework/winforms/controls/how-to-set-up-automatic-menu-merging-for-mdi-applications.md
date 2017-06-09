---
title: "Gewusst wie: Einrichten des automatischem Zusammenf&#252;hrens von Men&#252;s f&#252;r MDI-Anwendungen (Multiple Document Interface) | Microsoft Docs"
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
  - "MenuStrip, Zusammenführen"
  - "Zusammenführen, von Menüs, automatisch"
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Einrichten des automatischem Zusammenf&#252;hrens von Men&#252;s f&#252;r MDI-Anwendungen (Multiple Document Interface)
Im folgenden Verfahren werden die grundlegenden Schritte zum Einrichten des automatischen Zusammenführens in MDI\-Anwendungen \(Multiple Document Interface\) mit <xref:System.Windows.Forms.MenuStrip> beschrieben.  
  
### So richten Sie das automatische Zusammenführen von Menüs ein  
  
1.  Erstellen Sie das übergeordnete MDI\-Formular, indem Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>\-Eigenschaft auf `true` festlegen.  
  
2.  Fügen Sie dem übergeordneten MDI\-Element einen <xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie die <xref:System.Windows.Forms.Form.MainMenuStrip%2A>\-Eigenschaft auf diesen <xref:System.Windows.Forms.MenuStrip> fest.  
  
3.  Erstellen Sie ein untergeordnetes MDI\-Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.MdiParent%2A>\-Eigenschaft auf den Namen des übergeordneten Formulars fest.  
  
4.  Fügen Sie dem untergeordneten MDI\-Formular einen <xref:System.Windows.Forms.MenuStrip> hinzu.  
  
5.  Legen Sie im untergeordneten Formular die <xref:System.Windows.Forms.ToolStripItem.Visible%2A>\-Eigenschaft <xref:System.Windows.Forms.MenuStrip> auf `false` fest.  
  
6.  Fügen Sie dem <xref:System.Windows.Forms.MenuStrip> des untergeordneten Formulars, den Sie mit dem <xref:System.Windows.Forms.MenuStrip> des übergeordneten Formulars zusammenführen möchten, Menüelemente hinzu, wenn das untergeordnete Formular aktiviert ist.  
  
7.  Verwenden Sie die <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A>\-Eigenschaft der Menüelemente im <xref:System.Windows.Forms.MenuStrip> des untergeordneten Formulars, um zu steuern, wie sie mit dem übergeordneten Formular zusammengeführt werden.  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)