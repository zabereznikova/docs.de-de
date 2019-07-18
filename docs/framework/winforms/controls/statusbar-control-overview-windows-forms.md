---
title: Übersicht über das StatusBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: 4e1816ef221641f5ad54fb429442ed43289b592a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505423"
---
# <a name="statusbar-control-overview-windows-forms"></a>Übersicht über das StatusBar-Steuerelement (Windows Forms)
> [!IMPORTANT]
>  Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Hinzufügen von Funktionen, die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> -Steuerelemente jedoch die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie Wählen Sie aus.  
  
 Die Windows-Formulare [StatusBar-Steuerelement](statusbar-control-windows-forms.md) wird in Formularen verwendet ein Bereich, in der Regel angezeigt wird, am unteren Rand eines Fensters, in denen eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann. <xref:System.Windows.Forms.StatusBar> -Steuerelemente können Status Statusleistenbereiche mit Text enthalten, die Text oder Symbolen, um anzugeben, Status oder eine Reihe von Symbolen in einer Animation, die angeben, dass ein Prozess ausgeführt wird. Beispielsweise ist Microsoft Word gibt an, dass das Dokument gespeichert.  
  
## <a name="using-the-statusbar-control"></a>Verwenden das StatusBar-Steuerelement  
 Internet Explorer verwendet eine Statusleiste, um die URL einer Seite anzugeben, wenn die Maus über den Hyperlink wird; Microsoft Word, erhalten Sie Informationen auf seitenstandort, Abschnitt Speicherort und Bearbeiten von Modi, z. B. überschreiben und revisionsnachverfolgung; und Visual Studio verwendet die Statusleiste, wie Sie mitteilen, wie andockbare Fenster angedockt oder unverankert gedockt werden.  
  
 Sie können eine einzelne Nachricht in der Statusleiste anzeigen, indem Sie die Einstellung der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft `false` (Standard) und die <xref:System.Windows.Forms.StatusBar.Text%2A> Eigenschaft der Statusleiste auf den Text in der Statusleiste angezeigt werden sollen. Sie können die Statusleiste in Bereichen zum Anzeigen von mehr als eine Art von Informationen durch Festlegen von unterteilen der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft `true` und Verwenden der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> -Methode der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Vorgehensweise: Bestimmen Sie, welchen Bereich im StatusBar-Steuerelement von Windows Forms geklickt wurde](determine-which-panel-wf-statusbar-control-was-clicked.md)
