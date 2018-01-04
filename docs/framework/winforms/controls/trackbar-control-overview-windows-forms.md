---
title: "Übersicht über das TrackBar-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e62fc49a8a08c79138df080246b99b6fe891162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="83c6a-102">Übersicht über das TrackBar-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="83c6a-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="83c6a-103">Windows Forms <xref:System.Windows.Forms.TrackBar> -Steuerelement (manchmal auch "Schiebereglersteuerung" genannt) wird verwendet, zum Navigieren durch eine große Menge an Informationen oder für eine numerische Einstellung visuell anpassen.</span><span class="sxs-lookup"><span data-stu-id="83c6a-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="83c6a-104">Die <xref:System.Windows.Forms.TrackBar> Steuerelement besteht aus zwei Teilen: dem Ziehpunkt, auch bekannt als ein Schieberegler, und die Teilstriche.</span><span class="sxs-lookup"><span data-stu-id="83c6a-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="83c6a-105">Der Ziehpunkt ist der Teil, das angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="83c6a-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="83c6a-106">Entspricht die Position der <xref:System.Windows.Forms.TrackBar.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="83c6a-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="83c6a-107">Die Teilstriche sind visuelle Indikatoren, die in regelmäßigen Abständen angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="83c6a-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="83c6a-108">Die Trackbar verschiebt, die Sie angeben, und horizontal oder vertikal ausgerichtet werden können.</span><span class="sxs-lookup"><span data-stu-id="83c6a-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="83c6a-109">Beispielsweise können Sie die Trackleiste verwenden, können Sie den Cursor Blink Rate oder mit dem Mauszeiger Geschwindigkeit für ein System steuern.</span><span class="sxs-lookup"><span data-stu-id="83c6a-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="83c6a-110">Wichtige Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="83c6a-110">Key Properties</span></span>  
 <span data-ttu-id="83c6a-111">Wichtigsten Eigenschaften der <xref:System.Windows.Forms.TrackBar> Steuerelement sind <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, und <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span><span class="sxs-lookup"><span data-stu-id="83c6a-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <span data-ttu-id="83c6a-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A>Gibt den Abstand der Teilstriche.</span><span class="sxs-lookup"><span data-stu-id="83c6a-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> is the spacing of the ticks.</span></span> <span data-ttu-id="83c6a-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A>und <xref:System.Windows.Forms.TrackBar.Maximum%2A> sind die kleinsten und größten Werte, die auf der Trackleiste dargestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="83c6a-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="83c6a-114">Zwei wichtige Eigenschaften sind <xref:System.Windows.Forms.TrackBar.SmallChange%2A> und <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span><span class="sxs-lookup"><span data-stu-id="83c6a-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="83c6a-115">Der Wert, der die <xref:System.Windows.Forms.TrackBar.SmallChange%2A> Eigenschaft ist die Anzahl von Positionen Ziehpunkt bewegt wird, müssen die links oder nach-rechts-Taste gedrückt.</span><span class="sxs-lookup"><span data-stu-id="83c6a-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="83c6a-116">Der Wert, der die <xref:System.Windows.Forms.TrackBar.LargeChange%2A> Eigenschaft ist die Anzahl von Positionen Ziehpunkt bewegt wird, nachdem die Bild-auf oder Bild-ab-Taste gedrückt, oder als Antwort auf Maus klickt auf der Trackleiste auf beiden Seiten des Ziehpunkts.</span><span class="sxs-lookup"><span data-stu-id="83c6a-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c6a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83c6a-117">See Also</span></span>  
 <xref:System.Windows.Forms.TrackBar>  
 [<span data-ttu-id="83c6a-118">TrackBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="83c6a-118">TrackBar Control</span></span>](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
