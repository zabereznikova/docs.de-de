---
title: "Übersicht über das ToolStripContainer-Steuerelement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a1a4c9c77e1f347f95c0a5e17ab0d37e0013d6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="af72c-102">Übersicht über das ToolStripContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="af72c-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="af72c-103">Ein <xref:System.Windows.Forms.ToolStripContainer> weist Bereiche auf die Links, rechts, oben und unten Seiten zum Positionieren und rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, und <xref:System.Windows.Forms.StatusStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="af72c-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="af72c-104">Mehrere <xref:System.Windows.Forms.ToolStrip>-Steuerelemente werden vertikal gestapelt, wenn sie im linken oder rechten <xref:System.Windows.Forms.ToolStripContainer> abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="af72c-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="af72c-105">Wenn Sie sie im oberen oder unteren <xref:System.Windows.Forms.ToolStripContainer> ablegen, werden sie horizontal gestapelt.</span><span class="sxs-lookup"><span data-stu-id="af72c-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="af72c-106">Sie können das zentrale <xref:System.Windows.Forms.ToolStripContentPanel> von <xref:System.Windows.Forms.ToolStripContainer> verwenden, um herkömmliche Steuerelemente auf dem Formular zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="af72c-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="af72c-107">Einige oder alle <xref:System.Windows.Forms.ToolStripContainer>-Steuerelemente sind zur Entwurfszeit direkt auswählbar und können gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="af72c-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="af72c-108">Jeder Bereich von einer <xref:System.Windows.Forms.ToolStripContainer> ist erweiterbar und reduzierbar und passt seine Größe an die die darin enthaltenen Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="af72c-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="af72c-109">Wichtige ToolStripContainer-Member</span><span class="sxs-lookup"><span data-stu-id="af72c-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="af72c-110">name</span><span class="sxs-lookup"><span data-stu-id="af72c-110">Name</span></span>|<span data-ttu-id="af72c-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af72c-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="af72c-112">Ruft den unteren Bereich der <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="af72c-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="af72c-113">Ruft ab oder legt einen Wert, der angibt, ob im unteren Bereich, der die <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="af72c-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="af72c-114">Ruft den linken Bereich der <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="af72c-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="af72c-115">Ruft ab oder legt einen Wert, der angibt, ob der linke Bereich des der <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="af72c-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="af72c-116">Ruft den rechten Bereich der <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="af72c-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="af72c-117">Ruft ab oder legt einen Wert, der angibt, ob im rechten Bereich, der die <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="af72c-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="af72c-118">Ruft den oberen Bereich der <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="af72c-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="af72c-119">Ruft ab oder legt einen Wert, der angibt, ob der obere Bereich von der <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="af72c-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af72c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af72c-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>
