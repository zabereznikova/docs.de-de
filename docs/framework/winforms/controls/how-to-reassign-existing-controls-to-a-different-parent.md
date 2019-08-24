---
title: 'Vorgehensweise: Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 84e662e0bd2689115abe128c6442e4462eed3e18
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987044"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="6c7bf-102">Vorgehensweise: Neuzuweisen vorhandener Steuerelemente zu einem anderen übergeordneten Element</span><span class="sxs-lookup"><span data-stu-id="6c7bf-102">How to: Reassign existing controls to a different parent</span></span>

<span data-ttu-id="6c7bf-103">Sie können auf Ihrem Formular vorhandene Steuerelemente einem neuen Containersteuerelement zuordnen.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-103">You can assign controls that exist on your form to a new container control.</span></span>

1. <span data-ttu-id="6c7bf-104">Ziehen Sie in Visual Studio drei <xref:System.Windows.Forms.Button> Steuerelemente aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-104">In Visual Studio, drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span> <span data-ttu-id="6c7bf-105">Positionieren Sie sie nahe beieinander, ohne sie aber auszurichten.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-105">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="6c7bf-106">Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-106">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span> <span data-ttu-id="6c7bf-107">(Ziehen Sie das Symbol nicht auf das Formular.)</span><span class="sxs-lookup"><span data-stu-id="6c7bf-107">(Do not drag the icon onto the form.)</span></span>

3. <span data-ttu-id="6c7bf-108">Bewegen Sie den Mauszeiger in die Nähe der drei <xref:System.Windows.Forms.Button> -Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-108">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

   <span data-ttu-id="6c7bf-109">Der Mauszeiger nimmt die Form eines Fadenkreuzes an, an das das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-109">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="6c7bf-110">Klicken Sie, und halten Sie die Maustaste gedrückt.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-110">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="6c7bf-111">Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-111">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="6c7bf-112">Ziehen Sie die Kontur um die drei <xref:System.Windows.Forms.Button> -Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-112">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="6c7bf-113">Lassen Sie die Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-113">Release the mouse button.</span></span>

   <span data-ttu-id="6c7bf-114">Die drei <xref:System.Windows.Forms.Button> -Steuerelemente werden jetzt in das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement eingefügt.</span><span class="sxs-lookup"><span data-stu-id="6c7bf-114">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c7bf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c7bf-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="6c7bf-116">Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6c7bf-116">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="6c7bf-117">Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von Richtungslinien</span><span class="sxs-lookup"><span data-stu-id="6c7bf-117">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
