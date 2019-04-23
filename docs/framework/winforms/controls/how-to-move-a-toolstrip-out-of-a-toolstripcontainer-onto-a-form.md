---
title: 'Vorgehensweise: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 9106a69ea9f28442da6e3270f7cf5abb9374b62d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335263"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="bc250-102">Vorgehensweise: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular</span><span class="sxs-lookup"><span data-stu-id="bc250-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="bc250-103">Verwenden Sie das folgende Verfahren zum Verschieben einer <xref:System.Windows.Forms.ToolStrip> aus einem <xref:System.Windows.Forms.ToolStripContainer> auf ein Formular.</span><span class="sxs-lookup"><span data-stu-id="bc250-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc250-104">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="bc250-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bc250-105">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bc250-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bc250-106">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="bc250-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="bc250-107">Verschieben ein ToolStrip aus einem ToolStripContainer auf ein Formular</span><span class="sxs-lookup"><span data-stu-id="bc250-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1. <span data-ttu-id="bc250-108">Wählen Sie das <xref:System.Windows.Forms.ToolStrip>-Steuerelement aus.</span><span class="sxs-lookup"><span data-stu-id="bc250-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2. <span data-ttu-id="bc250-109">Ausschneiden der <xref:System.Windows.Forms.ToolStrip> durch Drücken von STRG + X oder mit der rechten Maustaste die <xref:System.Windows.Forms.ToolStrip> , und wählen Sie **Ausschneiden** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="bc250-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3. <span data-ttu-id="bc250-110">Wählen Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="bc250-110">Select the form.</span></span>  
  
4. <span data-ttu-id="bc250-111">Fügen Sie der <xref:System.Windows.Forms.ToolStrip> durch Drücken von STRG + V, oder wählen Sie **einfügen** aus der **bearbeiten** Menü.</span><span class="sxs-lookup"><span data-stu-id="bc250-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5. <span data-ttu-id="bc250-112">Legen Sie die <xref:System.Windows.Forms.ToolStrip.Dock%2A> Eigenschaft der <xref:System.Windows.Forms.ToolStrip> zu **oben**.</span><span class="sxs-lookup"><span data-stu-id="bc250-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc250-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc250-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="bc250-114">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="bc250-114">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
