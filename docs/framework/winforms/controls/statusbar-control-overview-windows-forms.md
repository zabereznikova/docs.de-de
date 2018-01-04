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
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="b4a72-102">Übersicht über das StatusBar-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b4a72-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="b4a72-103">Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Funktionen hinzufügen der <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> steuert; allerdings die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für die Abwärtskompatibilität und für zukünftige Verwendung beibehalten, wenn Sie Wählen Sie aus.</span><span class="sxs-lookup"><span data-stu-id="b4a72-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="b4a72-104">Windows Forms [StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) wird auf Formularen als Bereich, in der Regel am unteren Rand eines Fensters, in dem eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann angezeigt verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4a72-104">The Windows Forms [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="b4a72-105"><xref:System.Windows.Forms.StatusBar>Steuerelemente können Status Statusleistenbereiche mit Text enthalten, Text oder Symbole, um anzugeben, Status oder eine Reihe von Symbolen in einer Animation, die darauf hinweisen, dass ein Prozess ausgeführt wird. z. B. [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] , der angibt, das das Dokument gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b4a72-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="b4a72-106">Verwenden das StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b4a72-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="b4a72-107">Internet Explorer verwendet eine Statusleiste, um die URL einer Seite anzugeben, wenn die Maus über den Link wird ein; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] erhalten Sie Informationen zu Seite Speicherort, den Abschnitt Speicherort und Bearbeitungsmodi z. B. Überschreibmodus und revisionsnachverfolgung; und [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] verwendet die Statusleiste, z. B. mitteilen, wie die andockbare bearbeitet gedockt von Windows als angedockt oder unverankert.</span><span class="sxs-lookup"><span data-stu-id="b4a72-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] gives you information on page location, section location, and editing modes such as overtype and revision tracking; and [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="b4a72-108">Sie können eine einzelne Nachricht auf der Statusleiste anzeigen, indem Sie die Einstellung der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft, um `false` (Standard) und die Einstellung der <xref:System.Windows.Forms.StatusBar.Text%2A> Eigenschaft der Statusleiste auf den Text in der Statusleiste angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b4a72-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="b4a72-109">Bereiche zum Anzeigen von mehr als eine Art von Informationen durch Festlegen die Statusleiste unterteilen der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft `true` und mithilfe der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> Methode <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="b4a72-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a72-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4a72-110">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="b4a72-111">Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="b4a72-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
