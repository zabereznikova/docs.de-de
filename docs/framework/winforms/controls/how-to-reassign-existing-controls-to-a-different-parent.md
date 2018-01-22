---
title: "Gewusst wie: Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26998c002591850c0af3c265ae88b10657343787
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="8104d-102">Gewusst wie: Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element</span><span class="sxs-lookup"><span data-stu-id="8104d-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="8104d-103">Sie können auf Ihrem Formular vorhandene Steuerelemente einem neuen Containersteuerelement zuordnen.</span><span class="sxs-lookup"><span data-stu-id="8104d-103">You can assign controls that exist on your form to a new container control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8104d-104">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="8104d-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8104d-105">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8104d-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8104d-106">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="8104d-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="8104d-107">Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element</span><span class="sxs-lookup"><span data-stu-id="8104d-107">To reassign existing controls to a different parent</span></span>  
  
1.  <span data-ttu-id="8104d-108">Ziehen Sie drei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="8104d-108">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>  
  
     <span data-ttu-id="8104d-109">Positionieren Sie sie nahe beieinander, ohne sie aber auszurichten.</span><span class="sxs-lookup"><span data-stu-id="8104d-109">Position them near to each other, but leave them unaligned.</span></span>  
  
2.  <span data-ttu-id="8104d-110">Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="8104d-110">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>  
  
     <span data-ttu-id="8104d-111">Ziehen Sie das Symbol nicht auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="8104d-111">Do not drag the icon onto the form.</span></span>  
  
3.  <span data-ttu-id="8104d-112">Bewegen Sie den Mauszeiger in die Nähe der drei <xref:System.Windows.Forms.Button> -Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="8104d-112">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
     <span data-ttu-id="8104d-113">Der Mauszeiger nimmt die Form eines Fadenkreuzes an, an das das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="8104d-113">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>  
  
4.  <span data-ttu-id="8104d-114">Klicken Sie, und halten Sie die Maustaste gedrückt.</span><span class="sxs-lookup"><span data-stu-id="8104d-114">Click and hold the mouse button.</span></span>  
  
5.  <span data-ttu-id="8104d-115">Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="8104d-115">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6.  <span data-ttu-id="8104d-116">Ziehen Sie die Kontur um die drei <xref:System.Windows.Forms.Button> -Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="8104d-116">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
7.  <span data-ttu-id="8104d-117">Lassen Sie die Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="8104d-117">Release the mouse button.</span></span>  
  
     <span data-ttu-id="8104d-118">Die drei <xref:System.Windows.Forms.Button> -Steuerelemente werden jetzt in das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement eingefügt.</span><span class="sxs-lookup"><span data-stu-id="8104d-118">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8104d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8104d-119">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="8104d-120">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8104d-120">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="8104d-121">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8104d-121">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="8104d-122">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="8104d-122">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
