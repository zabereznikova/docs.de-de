---
title: "Übersicht über das StatusBar-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df8e6b8484cf3b35c684445445ddc41adc358698
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="statusbar-control-overview-windows-forms"></a>Übersicht über das StatusBar-Steuerelement (Windows Forms)
> [!IMPORTANT]
>  Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Funktionen hinzufügen der <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> steuert; allerdings die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für die Abwärtskompatibilität und für zukünftige Verwendung beibehalten, wenn Sie Wählen Sie aus.  
  
 Windows Forms [StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) wird auf Formularen als Bereich, in der Regel am unteren Rand eines Fensters, in dem eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann angezeigt verwendet. <xref:System.Windows.Forms.StatusBar>Steuerelemente können Status Statusleistenbereiche mit Text enthalten, Text oder Symbole, um anzugeben, Status oder eine Reihe von Symbolen in einer Animation, die darauf hinweisen, dass ein Prozess ausgeführt wird. z. B. [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] , der angibt, das das Dokument gespeichert wird.  
  
## <a name="using-the-statusbar-control"></a>Verwenden das StatusBar-Steuerelement  
 Internet Explorer verwendet eine Statusleiste, um die URL einer Seite anzugeben, wenn die Maus über den Link wird ein; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] erhalten Sie Informationen zu Seite Speicherort, den Abschnitt Speicherort und Bearbeitungsmodi z. B. Überschreibmodus und revisionsnachverfolgung; und [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] verwendet die Statusleiste, z. B. mitteilen, wie die andockbare bearbeitet gedockt von Windows als angedockt oder unverankert.  
  
 Sie können eine einzelne Nachricht auf der Statusleiste anzeigen, indem Sie die Einstellung der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft, um `false` (Standard) und die Einstellung der <xref:System.Windows.Forms.StatusBar.Text%2A> Eigenschaft der Statusleiste auf den Text in der Statusleiste angezeigt werden sollen. Bereiche zum Anzeigen von mehr als eine Art von Informationen durch Festlegen die Statusleiste unterteilen der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft `true` und mithilfe der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> Methode <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
