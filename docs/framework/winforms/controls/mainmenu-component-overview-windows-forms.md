---
title: "&#220;bersicht &#252;ber die MainMenu-Komponente (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MenuItem"
  - "MainMenu"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MainMenu-Steuerelement [Windows Forms], Informationen über das MainMenu-Steuerelement"
  - "Menüs"
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber die MainMenu-Komponente (Windows&#160;Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen das <xref:System.Windows.Forms.MainMenu>\-Steuerelement und das <xref:System.Windows.Forms.ContextMenu>\-Steuerelement früherer Versionen und erweitern dieses um Funktionen, jedoch werden <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> aus Gründen der Abwärtskompatibilität und, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Durch die <xref:System.Windows.Forms.MainMenu>\-Komponente in Windows Forms wird zur Laufzeit ein Menü angezeigt.  Alle Untermenüs des Hauptmenüs und einzelne Elemente sind <xref:System.Windows.Forms.MenuItem>\-Objekte.  
  
## Haupteigenschaften  
 Sie können ein Menüelement als Standardelement kennzeichnen, indem Sie die <xref:System.Windows.Forms.MenuItem.DefaultItem%2A>\-Eigenschaft auf `true` festlegen.  Sobald auf das Menü geklickt wird, wird das Standardelement fett dargestellt.  Die <xref:System.Windows.Forms.MenuItem.Checked%2A>\-Eigenschaft des Menüelements lautet entweder `true` oder `false`. Sie gibt an, ob ein Menüelement ausgewählt ist.  Über die <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>\-Eigenschaft des Menüelements wird die Darstellung des ausgewählten Elements angepasst: Hat <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> die Einstellung `true`, wird neben dem Element ein Optionsfeld angezeigt, und hat <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> die Einstellung `false`, wird neben dem Element ein Häkchen angezeigt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.MainMenu>   
 <xref:System.Windows.Forms.Menu>   
 <xref:System.Windows.Forms.MenuItem>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)