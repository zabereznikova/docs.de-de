---
title: Übersicht über das StatusBar-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: b0b97bc3cb0291871e1fd113d82d0b480b53cdba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742865"
---
# <a name="statusbar-control-overview-windows-forms"></a>Übersicht über das StatusBar-Steuerelement (Windows Forms)
> [!IMPORTANT]
> Die Steuerelemente <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> ersetzen und fügen Funktionen zum <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelementen hinzu. die <xref:System.Windows.Forms.StatusBar>-und <xref:System.Windows.Forms.StatusBarPanel>-Steuerelemente werden jedoch sowohl für Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie sich entscheiden.  
  
 Das Windows Forms [StatusBar-Steuer](statusbar-control-windows-forms.md) Element wird in Formularen als Bereich verwendet, der normalerweise am unteren Rand eines Fensters angezeigt wird, in dem eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann. <xref:System.Windows.Forms.StatusBar> Steuerelemente können über Status leisten Panels verfügen, in denen Text oder Symbole angezeigt werden, um den Zustand anzugeben, oder eine Reihe von Symbolen in einer Animation, die darauf hinweisen, dass ein Prozess funktioniert. beispielsweise Microsoft Word, das angibt, dass das Dokument gespeichert wird.  
  
## <a name="using-the-statusbar-control"></a>Verwenden des StatusBar-Steuer Elements  
 Internet Explorer verwendet eine Statusleiste, um die URL einer Seite anzugeben, wenn mit dem Mauszeiger auf den Link geklickt wird. Microsoft Word bietet Ihnen Informationen zu Seiten Speicherort, Abschnitts Speicherort und Bearbeitungsmodi, z. b. über Schreib und Revisions Nachverfolgung. und Visual Studio verwendet die Statusleiste, um kontextbezogene Informationen anzugeben, z. b. um zu erfahren, wie andockbare Fenster entweder als angedockt oder unverankert geändert werden.  
  
 Sie können eine einzelne Meldung auf der Statusleiste anzeigen, indem Sie die <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>-Eigenschaft auf `false` (Standardeinstellung) festlegen und die <xref:System.Windows.Forms.StatusBar.Text%2A>-Eigenschaft der Statusleiste auf den Text festlegen, der in der Statusleiste angezeigt werden soll. Sie können die Statusleiste in Bereiche aufteilen, um mehr als eine Art von Informationen anzuzeigen, indem Sie die <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>-Eigenschaft auf `true` festlegen und die <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A>-Methode der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde](determine-which-panel-wf-statusbar-control-was-clicked.md)
