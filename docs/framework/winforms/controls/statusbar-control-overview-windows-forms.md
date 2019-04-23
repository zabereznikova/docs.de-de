---
title: Übersicht über das StatusBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: 5fdefa7d7e7c7ef543f677be7beb61dfee54e077
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077315"
---
# <a name="statusbar-control-overview-windows-forms"></a>Übersicht über das StatusBar-Steuerelement (Windows Forms)
> [!IMPORTANT]
>  Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Hinzufügen von Funktionen, die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> -Steuerelemente jedoch die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie Wählen Sie aus.  
  
 Die Windows-Formulare [StatusBar-Steuerelement](statusbar-control-windows-forms.md) wird in Formularen verwendet ein Bereich, in der Regel angezeigt wird, am unteren Rand eines Fensters, in denen eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann. <xref:System.Windows.Forms.StatusBar> -Steuerelemente können Status Statusleistenbereiche mit Text enthalten, die Text oder Symbolen, um anzugeben, Status oder eine Reihe von Symbolen in einer Animation, die angeben, dass ein Prozess ausgeführt wird. z. B. [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] , der angibt, das das Dokument gespeichert wird.  
  
## <a name="using-the-statusbar-control"></a>Verwenden das StatusBar-Steuerelement  
 Internet Explorer verwendet eine Statusleiste, um die URL einer Seite anzugeben, wenn die Maus über den Hyperlink wird; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] ermöglicht es Ihnen Informationen auf der Seite Speicherort, Abschnitt Speicherort und Modi bearbeiten, wie z. B. überschreiben und revisionsnachverfolgung; und Visual Studio wird verwendet, die Statusleiste, wie Sie darüber informiert wie andockbare Fenster gedockt angedockt oder unverankert.  
  
 Sie können eine einzelne Nachricht in der Statusleiste anzeigen, indem Sie die Einstellung der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft `false` (Standard) und die <xref:System.Windows.Forms.StatusBar.Text%2A> Eigenschaft der Statusleiste auf den Text in der Statusleiste angezeigt werden sollen. Sie können die Statusleiste in Bereichen zum Anzeigen von mehr als eine Art von Informationen durch Festlegen von unterteilen der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft `true` und Verwenden der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> -Methode der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Vorgehensweise: Bestimmen Sie, welchen Bereich im StatusBar-Steuerelement von Windows Forms geklickt wurde](determine-which-panel-wf-statusbar-control-was-clicked.md)
