---
title: "&#220;bersicht &#252;ber das StatusBar-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "StatusBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Statusleisten"
  - "StatusBar-Steuerelement [Windows Forms], Informationen über das StatusBar-Steuerelement"
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber das StatusBar-Steuerelement (Windows&#160;Forms)
> [!IMPORTANT]
>  Obwohl die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> durch die Steuerelemente <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> ersetzt und funktionell erweitert werden, werden die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Das Windows Forms [StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) wird in Formularen als \(normalerweise unten im Fenster angezeigter\) Bereich verwendet, in dem Anwendungen verschiedene Arten von Statusinformationen ausgeben können.  <xref:System.Windows.Forms.StatusBar>\-Steuerelemente können Statusleistenbereiche mit Text oder Symbolen enthalten, die den Status angeben. Sie können auch eine Reihe von Symbolen in einer Animation enthalten, die anzeigen, dass ein Prozess ausgeführt wird, wie beispielsweise die Animation beim Speichern eines Dokuments in [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)].  
  
## Verwenden des StatusBar\-Steuerelements  
 Der Internet Explorer zeigt in der Statusleiste die URL einer Seite an, wenn der Mauszeiger über Links bewegt wird. [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] zeigt Informationen über die Seitenzahl, die Abschnittsnummer und die Bearbeitungsmodi \(z. B. Überschreiben und Änderungsverfolgung\) an, und [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] gibt in der Statusleiste kontextabhängige Informationen an. So werden Sie z. B. darüber informiert, wie andockbare Fenster entweder gedockt oder nicht gedockt verwendet werden.  
  
 Sie können eine einzelne Meldung auf der Statusleiste anzeigen, indem Sie für die <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>\-Eigenschaft `false` \(die Standardeinstellung\) festlegen und die <xref:System.Windows.Forms.StatusBar.Text%2A>\-Eigenschaft der Statusleiste auf den Text festlegen, der in der Statusleiste angezeigt werden soll.  Die Statusleiste kann in Bereiche unterteilt werden, um mehrere Arten von Informationen anzuzeigen. Legen Sie dazu für die <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>\-Eigenschaft `true` fest, und verwenden Sie die <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A>\-Methode von <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar\-Steuerelement in Windows Forms geklickt wurde](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)