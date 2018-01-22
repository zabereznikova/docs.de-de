---
title: 'Gewusst wie: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97d65abf38ee434218fa9bec0d8a9cade31fb687
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="9b0a1-102">Gewusst wie: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular</span><span class="sxs-lookup"><span data-stu-id="9b0a1-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="9b0a1-103">Verwenden Sie das folgende Verfahren zum Verschieben einer <xref:System.Windows.Forms.ToolStrip> aus einem <xref:System.Windows.Forms.ToolStripContainer> auf ein Formular.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b0a1-104">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9b0a1-105">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9b0a1-106">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="9b0a1-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="9b0a1-107">Verschieben ein ToolStrip aus einem ToolStripContainer auf ein Formular</span><span class="sxs-lookup"><span data-stu-id="9b0a1-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1.  <span data-ttu-id="9b0a1-108">Wählen Sie das <xref:System.Windows.Forms.ToolStrip>-Steuerelement aus.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2.  <span data-ttu-id="9b0a1-109">Ausschneiden der <xref:System.Windows.Forms.ToolStrip> durch Drücken von STRG + X drücken oder mit der rechten Maustaste die <xref:System.Windows.Forms.ToolStrip> , und wählen Sie **Ausschneiden** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3.  <span data-ttu-id="9b0a1-110">Wählen Sie das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-110">Select the form.</span></span>  
  
4.  <span data-ttu-id="9b0a1-111">Fügen Sie der <xref:System.Windows.Forms.ToolStrip> durch Drücken von STRG + V, oder wählen Sie **einfügen** aus der **bearbeiten** Menü.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5.  <span data-ttu-id="9b0a1-112">Festlegen der <xref:System.Windows.Forms.ToolStrip.Dock%2A> Eigenschaft von der <xref:System.Windows.Forms.ToolStrip> auf **oben**.</span><span class="sxs-lookup"><span data-stu-id="9b0a1-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b0a1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b0a1-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [<span data-ttu-id="9b0a1-114">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9b0a1-114">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
