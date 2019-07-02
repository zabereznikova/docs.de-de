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
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="9934d-102">Übersicht über das StatusBar-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9934d-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="9934d-103">Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Hinzufügen von Funktionen, die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> -Steuerelemente jedoch die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie Wählen Sie aus.</span><span class="sxs-lookup"><span data-stu-id="9934d-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="9934d-104">Die Windows-Formulare [StatusBar-Steuerelement](statusbar-control-windows-forms.md) wird in Formularen verwendet ein Bereich, in der Regel angezeigt wird, am unteren Rand eines Fensters, in denen eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="9934d-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="9934d-105"><xref:System.Windows.Forms.StatusBar> -Steuerelemente können Status Statusleistenbereiche mit Text enthalten, die Text oder Symbolen, um anzugeben, Status oder eine Reihe von Symbolen in einer Animation, die angeben, dass ein Prozess ausgeführt wird. Beispielsweise ist Microsoft Word gibt an, dass das Dokument gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9934d-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="9934d-106">Verwenden das StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9934d-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="9934d-107">Internet Explorer verwendet eine Statusleiste, um die URL einer Seite anzugeben, wenn die Maus über den Hyperlink wird; Microsoft Word, erhalten Sie Informationen auf seitenstandort, Abschnitt Speicherort und Bearbeiten von Modi, z. B. überschreiben und revisionsnachverfolgung; und Visual Studio verwendet die Statusleiste, wie Sie mitteilen, wie andockbare Fenster angedockt oder unverankert gedockt werden.</span><span class="sxs-lookup"><span data-stu-id="9934d-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="9934d-108">Sie können eine einzelne Nachricht in der Statusleiste anzeigen, indem Sie die Einstellung der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft `false` (Standard) und die <xref:System.Windows.Forms.StatusBar.Text%2A> Eigenschaft der Statusleiste auf den Text in der Statusleiste angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9934d-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="9934d-109">Sie können die Statusleiste in Bereichen zum Anzeigen von mehr als eine Art von Informationen durch Festlegen von unterteilen der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft `true` und Verwenden der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> -Methode der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="9934d-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9934d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9934d-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="9934d-111">Vorgehensweise: Bestimmen Sie, welchen Bereich im StatusBar-Steuerelement von Windows Forms geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="9934d-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
