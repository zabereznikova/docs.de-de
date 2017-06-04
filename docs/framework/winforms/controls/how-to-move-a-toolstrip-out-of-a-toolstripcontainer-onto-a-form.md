---
title: "Gewusst wie: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular | Microsoft Docs"
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
  - "ToolStrip-Steuerelement [Windows Forms], Überordnung für Formulare"
  - "Windows Forms, Überordnen von ToolStrip-Steuerelementen"
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular
Mithilfe der folgenden Prozedur können Sie einen <xref:System.Windows.Forms.ToolStrip> aus einem <xref:System.Windows.Forms.ToolStripContainer> auf ein Formular verschieben.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So verschieben Sie einen ToolStrip aus einem ToolStripContainer auf ein Formular  
  
1.  Wählen Sie das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement aus.  
  
2.  Schneiden Sie den <xref:System.Windows.Forms.ToolStrip> aus, indem Sie STRG\+X drücken, oder klicken Sie mit der rechten Maustaste auf den <xref:System.Windows.Forms.ToolStrip>, und wählen Sie im Kontextmenü **Ausschneiden** aus.  
  
3.  Wählen Sie das Formular aus.  
  
4.  Fügen Sie den <xref:System.Windows.Forms.ToolStrip> ein, indem Sie STRG\+V drücken oder im Menü **Bearbeiten** die Option **Einfügen** auswählen.  
  
5.  Legen Sie die <xref:System.Windows.Forms.ToolStrip.Dock%2A>\-Eigenschaft des <xref:System.Windows.Forms.ToolStrip> auf **Top** fest.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripContainer>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)