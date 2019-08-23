---
title: Übersicht über das StatusBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: bd58d4c70e3a3c88e57fe242957f669d1944fd71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964436"
---
# <a name="statusbar-control-overview-windows-forms"></a>Übersicht über das StatusBar-Steuerelement (Windows Forms)
> [!IMPORTANT]
> Das <xref:System.Windows.Forms.StatusStrip> - <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelement und das-Steuerelement <xref:System.Windows.Forms.StatusBar> ersetzen und fügen Funktionen zu den <xref:System.Windows.Forms.StatusBar> Steuer <xref:System.Windows.Forms.StatusBarPanel> Elementen und <xref:System.Windows.Forms.StatusBarPanel> hinzu. die Steuerelemente und werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, St.  
  
 Das Windows Forms [StatusBar-Steuer](statusbar-control-windows-forms.md) Element wird in Formularen als Bereich verwendet, der normalerweise am unteren Rand eines Fensters angezeigt wird, in dem eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann. <xref:System.Windows.Forms.StatusBar>Steuerelemente können über Status leisten Panels verfügen, in denen Text oder Symbole angezeigt werden, um den Zustand anzugeben, oder eine Reihe von Symbolen in einer Animation, die darauf hinweisen, dass ein Prozess funktioniert. beispielsweise Microsoft Word, das angibt, dass das Dokument gespeichert wird.  
  
## <a name="using-the-statusbar-control"></a>Verwenden des StatusBar-Steuer Elements  
 Internet Explorer verwendet eine Statusleiste, um die URL einer Seite anzugeben, wenn mit dem Mauszeiger auf den Link geklickt wird. Microsoft Word bietet Ihnen Informationen zu Seiten Speicherort, Abschnitts Speicherort und Bearbeitungsmodi, z. b. über Schreib und Revisions Nachverfolgung. und Visual Studio verwendet die Statusleiste, um kontextbezogene Informationen anzugeben, z. b. um zu erfahren, wie andockbare Fenster entweder als angedockt oder unverankert geändert werden.  
  
 Sie können eine einzelne Meldung auf der Statusleiste anzeigen, indem Sie <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> die- `false` Eigenschaft auf festlegen (Standardeinstellung) <xref:System.Windows.Forms.StatusBar.Text%2A> und die-Eigenschaft der Statusleiste auf den Text festlegen, der in der Statusleiste angezeigt werden soll. Sie können die Statusleiste in Panels aufteilen, um mehr als eine Art von Informationen anzuzeigen, indem <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Sie die `true` -Eigenschaft auf <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> festlegen und <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>die-Methode von verwenden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Vorgehensweise: Legen Sie fest, auf welchem Bereich im Windows Forms StatusBar-Steuerelement geklickt wurde.](determine-which-panel-wf-statusbar-control-was-clicked.md)
