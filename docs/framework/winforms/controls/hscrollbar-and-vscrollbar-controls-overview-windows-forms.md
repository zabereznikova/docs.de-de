---
title: "Übersicht über das HScrollBar-Steuerelement und das VScrollBar-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8fbdb3778959d1691200cde49e485d8a63c6e645
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="70b5c-102">Übersicht über das HScrollBar-Steuerelement und das VScrollBar-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="70b5c-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="70b5c-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> Steuerelemente werden verwendet, um die einfache Navigation in einer langen Liste von Elementen oder eine große Menge an Informationen entweder horizontal oder vertikal innerhalb einer Anwendung bzw. eines Steuerelements bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="70b5c-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="70b5c-104">Bildlaufleisten sind ein häufiges Element der Windows-Schnittstelle, damit die <xref:System.Windows.Forms.ScrollBar> Steuerelement wird häufig mit Steuerelementen, die nicht von abgeleitet sind, verwendet der <xref:System.Windows.Forms.ScrollableControl> Klasse.</span><span class="sxs-lookup"><span data-stu-id="70b5c-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="70b5c-105">Ebenso viele Entwickler wählen, integriert der <xref:System.Windows.Forms.ScrollBar> gesteuert werden, wenn ihre eigenen Benutzersteuerelemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="70b5c-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="70b5c-106">Die <xref:System.Windows.Forms.HScrollBar> (horizontal) und <xref:System.Windows.Forms.VScrollBar> (vertikal) funktionieren unabhängig von anderen Steuerelementen und verfügen über ihre eigenen Satz von Ereignissen, Eigenschaften und Methoden.</span><span class="sxs-lookup"><span data-stu-id="70b5c-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <span data-ttu-id="70b5c-107"><xref:System.Windows.Forms.ScrollBar>Steuerelemente sind nicht identisch mit den integrierten Bildlaufleisten, die Textfelder, Kombinationsfelder oder MDI-Formulare zugeordnet sind (die <xref:System.Windows.Forms.TextBox> Steuerelement verfügt über eine <xref:System.Windows.Forms.TextBox.ScrollBars%2A> Eigenschaft anzeigen oder Ausblenden von Bildlaufleisten, die dem Steuerelement zugeordnet sind).</span><span class="sxs-lookup"><span data-stu-id="70b5c-107"><xref:System.Windows.Forms.ScrollBar> controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="70b5c-108">Die <xref:System.Windows.Forms.ScrollBar> steuert die Verwendung der <xref:System.Windows.Forms.ScrollBar.Scroll> Ereignis zum Überwachen von der Verschiebung des Bildlauffelds (auch als Ziehpunkt bezeichnet) entlang der Bildlaufleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="70b5c-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="70b5c-109">Mithilfe der <xref:System.Windows.Forms.ScrollBar.Scroll> Ereignis ermöglicht den Zugriff auf den Wert der Scroll Bar gezogen wird.</span><span class="sxs-lookup"><span data-stu-id="70b5c-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="70b5c-110">Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="70b5c-110">Value Property</span></span>  
 <span data-ttu-id="70b5c-111">Die <xref:System.Windows.Forms.ScrollBar.Value%2A> -Eigenschaft (d. h. in der Standardeinstellung 0) ist ein `integer` Wert, der die Position des Bildlauffelds auf der Bildlaufleiste.</span><span class="sxs-lookup"><span data-stu-id="70b5c-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="70b5c-112">Die Position des Bildlauffelds auf den Mindestwert ist, verschoben in die linke Position (für horizontale Bildlaufleisten) oder die obere Position (für die vertikalen Schiebeleisten).</span><span class="sxs-lookup"><span data-stu-id="70b5c-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="70b5c-113">Wenn das Bildlauffeld auf der maximale Wert, der verschoben, die sich ganz rechts oder untere Position ist.</span><span class="sxs-lookup"><span data-stu-id="70b5c-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="70b5c-114">Auf ähnliche Weise fügt ein Wert in der Mitte zwischen dem unteren und oberen Ende des Bereichs führenden Rand des Bildlauffelds in der Mitte der Bildlaufleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="70b5c-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="70b5c-115">Benutzer kann mit Mausklicks so ändern Sie den Wert der Bildlaufleiste an, das Bildlauffeld auch auf einen beliebigen Punkt auf der Leiste ziehen.</span><span class="sxs-lookup"><span data-stu-id="70b5c-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="70b5c-116">Der resultierende Wert hängt von der Position des Bildlauffelds allerdings handelt es sich immer innerhalb des Bereichs von der <xref:System.Windows.Forms.ScrollBar.Minimum%2A> auf <xref:System.Windows.Forms.ScrollBar.Maximum%2A> Eigenschaften, die vom Benutzer festgelegt.</span><span class="sxs-lookup"><span data-stu-id="70b5c-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="70b5c-117">LargeChange und SmallChange-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="70b5c-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="70b5c-118">Wenn der Benutzer die Bild-auf oder Bild-ab-Taste drückt oder in der Schiebeleiste auf beiden Seiten des Bildlauffelds, klickt auf die <xref:System.Windows.Forms.ScrollBar.Value%2A> Eigenschaft ändert sich entsprechend der im festgelegte Wert die <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="70b5c-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="70b5c-119">Tasten oder auf eine der Schaltflächen der Bildlaufleiste, wenn der Benutzer eine der Pfeiltasten drückt die <xref:System.Windows.Forms.ScrollBar.Value%2A> Eigenschaft ändert sich entsprechend der im festgelegte Wert die <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="70b5c-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b5c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70b5c-120">See Also</span></span>  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [<span data-ttu-id="70b5c-121">Ergänzungen für Windows Forms für .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="70b5c-121">Additions to Windows Forms for the .NET Framework 2.0</span></span>](http://msdn.microsoft.com/library/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [<span data-ttu-id="70b5c-122">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="70b5c-122">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
