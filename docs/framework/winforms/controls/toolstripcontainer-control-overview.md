---
title: Übersicht über das ToolStripContainer-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: c279316c2a372a1498707b27ec8658813306304b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191262"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="74cb6-102">Übersicht über das ToolStripContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74cb6-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="74cb6-103">Ein <xref:System.Windows.Forms.ToolStripContainer> Bereiche auf die Links, rechts, oben und unten Seiten zum Positionieren und rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, und <xref:System.Windows.Forms.StatusStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="74cb6-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="74cb6-104">Mehrere <xref:System.Windows.Forms.ToolStrip>-Steuerelemente werden vertikal gestapelt, wenn sie im linken oder rechten <xref:System.Windows.Forms.ToolStripContainer> abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="74cb6-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="74cb6-105">Wenn Sie sie im oberen oder unteren <xref:System.Windows.Forms.ToolStripContainer> ablegen, werden sie horizontal gestapelt.</span><span class="sxs-lookup"><span data-stu-id="74cb6-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="74cb6-106">Sie können das zentrale <xref:System.Windows.Forms.ToolStripContentPanel> von <xref:System.Windows.Forms.ToolStripContainer> verwenden, um herkömmliche Steuerelemente auf dem Formular zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="74cb6-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="74cb6-107">Einige oder alle <xref:System.Windows.Forms.ToolStripContainer>-Steuerelemente sind zur Entwurfszeit direkt auswählbar und können gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="74cb6-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="74cb6-108">Jeder Bereich von einer <xref:System.Windows.Forms.ToolStripContainer> ist erweiterbar und reduzierbar und passt seine Größe an die darin enthaltenen Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="74cb6-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="74cb6-109">Wichtige ToolStripContainer-Member</span><span class="sxs-lookup"><span data-stu-id="74cb6-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="74cb6-110">Name</span><span class="sxs-lookup"><span data-stu-id="74cb6-110">Name</span></span>|<span data-ttu-id="74cb6-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74cb6-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="74cb6-112">Ruft den unteren Bereich des der <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="74cb6-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="74cb6-113">Ruft ab oder legt einen Wert, der angibt, ob der untere Bereich des der <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="74cb6-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="74cb6-114">Ruft den linken Bereich von der <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="74cb6-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="74cb6-115">Ruft einen Wert ab oder legt, ob der linke Bereich des der <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="74cb6-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="74cb6-116">Ruft den rechten Bereich von der <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="74cb6-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="74cb6-117">Ruft ab oder legt einen Wert, der angibt, ob der rechte Bereich des der <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="74cb6-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="74cb6-118">Ruft den oberen Bereich des der <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="74cb6-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="74cb6-119">Ruft ab oder legt einen Wert, der angibt, ob der obere Bereich des der <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="74cb6-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74cb6-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74cb6-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
