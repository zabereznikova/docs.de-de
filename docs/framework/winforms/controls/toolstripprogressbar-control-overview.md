---
title: Übersicht über das ToolStripProgressBar-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- ToolStripProgressBar
helpviewer_keywords:
- toolbars [Windows Forms], progress bars
- progress controls [Windows Forms]
- ToolStripProgressBar control [Windows Forms], about ToolStripProgressBar control
ms.assetid: ec3ab522-5fe4-4b4d-a551-bc19e84f4774
ms.openlocfilehash: 0ce2347be055cc1840341747f202125cbbf678c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537751"
---
# <a name="toolstripprogressbar-control-overview"></a><span data-ttu-id="0ff13-102">Übersicht über das ToolStripProgressBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0ff13-102">ToolStripProgressBar Control Overview</span></span>
<span data-ttu-id="0ff13-103">Die <xref:System.Windows.Forms.ToolStripProgressBar> kombiniert die rafting und Funktionen für das Rendern von allen <xref:System.Windows.Forms.ToolStrip> Steuerelemente mit seinen normalen Prozess Tracking-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="0ff13-103">The <xref:System.Windows.Forms.ToolStripProgressBar> combines the rafting and rendering functionality of all <xref:System.Windows.Forms.ToolStrip> controls with its typical process-tracking functionality.</span></span> <span data-ttu-id="0ff13-104">Ein <xref:System.Windows.Forms.ToolStripProgressBar> wird von den meisten Fällen gehostet <xref:System.Windows.Forms.StatusStrip>, und weniger häufig durch eine <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="0ff13-104">A <xref:System.Windows.Forms.ToolStripProgressBar> is most usually hosted by <xref:System.Windows.Forms.StatusStrip>, and less frequently by a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="0ff13-105">Obwohl <xref:System.Windows.Forms.ToolStripProgressBar> ersetzt und funktionell erweitert, um das Steuerelement in früheren Versionen <xref:System.Windows.Forms.ToolStripProgressBar> wird für Abwärtskompatibilität und für zukünftige Verwendung beibehalten, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="0ff13-105">Although <xref:System.Windows.Forms.ToolStripProgressBar> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolStripProgressBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
### <a name="important-toolstripprogressbar-members"></a><span data-ttu-id="0ff13-106">Wichtige ToolStripProgressBar-Member</span><span class="sxs-lookup"><span data-stu-id="0ff13-106">Important ToolStripProgressBar Members</span></span>  
  
|<span data-ttu-id="0ff13-107">name</span><span class="sxs-lookup"><span data-stu-id="0ff13-107">Name</span></span>|<span data-ttu-id="0ff13-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ff13-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripProgressBar.MarqueeAnimationSpeed%2A>|<span data-ttu-id="0ff13-109">Ruft ab oder legt einen Wert, der die Verzögerung zwischen den einzelnen darstellt <xref:System.Windows.Forms.ProgressBarStyle.Marquee> Update in Millisekunden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff13-109">Gets or sets a value representing the delay between each <xref:System.Windows.Forms.ProgressBarStyle.Marquee> display update, in milliseconds.</span></span>|  
|<xref:System.Windows.Forms.ProgressBar.Maximum%2A>|<span data-ttu-id="0ff13-110">Ruft ab oder legt die obere Grenze des Bereichs, der für diesen definiert ist <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="0ff13-110">Gets or sets the upper bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Minimum%2A>|<span data-ttu-id="0ff13-111">Ruft ab oder legt die untere Grenze des Bereichs, der für diesen definiert ist <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="0ff13-111">Gets or sets the lower bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Style%2A>|<span data-ttu-id="0ff13-112">Ruft ab oder legt den Stil fest, die die <xref:System.Windows.Forms.ToolStripProgressBar> verwendet, um den Status eines Vorgangs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0ff13-112">Gets or sets the style that the <xref:System.Windows.Forms.ToolStripProgressBar> uses to display the progress of an operation.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Value%2A>|<span data-ttu-id="0ff13-113">Ruft ab oder legt den aktuellen Wert für die <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="0ff13-113">Gets or sets the current value of the <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.PerformStep%2A>|<span data-ttu-id="0ff13-114">Erhöht die aktuelle Position der Statusanzeige um den Betrag der der <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0ff13-114">Advances the current position of the progress bar by the amount of the <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ff13-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ff13-115">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripProgressBar>
