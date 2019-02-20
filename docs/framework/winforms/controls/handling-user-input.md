---
title: Behandeln von Benutzereingaben
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: 8c6319929d4b419cc0a2e1cfd097bfae7d997120
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2019
ms.locfileid: "56443002"
---
# <a name="handling-user-input"></a><span data-ttu-id="9e5e9-102">Behandeln von Benutzereingaben</span><span class="sxs-lookup"><span data-stu-id="9e5e9-102">Handling User Input</span></span>
<span data-ttu-id="9e5e9-103">In diesem Thema wird beschrieben, die wichtigsten Tastatur- und Mausereignisse Ereignisse gebotenen <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9e5e9-104">Beim Bearbeiten eines Ereignisses sollten Autoren von Steuerelementen die geschützte Methode `On`*EventName* überschreiben, statt einen Delegaten an das Ereignis anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="9e5e9-105">Zum Überprüfen der Ereignisse siehe [Auslösen von Ereignissen aus einer Komponente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="9e5e9-105">For a review of events, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e5e9-106">Wenn es keine Daten, die einem Ereignis, eine Instanz der Basisklasse zugeordneten sind <xref:System.EventArgs> wird als Argument übergeben, die `On` *EventName* Methode.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="9e5e9-107">Tastaturereignisse</span><span class="sxs-lookup"><span data-stu-id="9e5e9-107">Keyboard Events</span></span>  
 <span data-ttu-id="9e5e9-108">Sind die allgemeinen Tastaturereignisse, die das Steuerelement bearbeiten <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, und <xref:System.Windows.Forms.Control.KeyUp>.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="9e5e9-109">Ereignisname</span><span class="sxs-lookup"><span data-stu-id="9e5e9-109">Event Name</span></span>|<span data-ttu-id="9e5e9-110">Zu überschreibende Methode</span><span class="sxs-lookup"><span data-stu-id="9e5e9-110">Method to Override</span></span>|<span data-ttu-id="9e5e9-111">Beschreibung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9e5e9-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="9e5e9-112">Wird nur ausgelöst, wenn anfangs eine Taste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="9e5e9-113">Wird jedes Mal ausgelöst, wenn eine Taste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="9e5e9-114">Wenn eine Taste gedrückt gehalten wird, wird eine <xref:System.Windows.Forms.Control.KeyPress> Ereignis wird ausgelöst, auf die vom Betriebssystem definierten Wiederholungsrate.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="9e5e9-115">Wird ausgelöst, wenn eine Taste losgelassen wird.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9e5e9-116">Das Bearbeiten von Tastatureingaben ist wesentlich komplexer als das Überschreiben der Ereignisse in der obigen Tabelle und würde Rahmen dieses Themas sprengen.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="9e5e9-117">Weitere Informationen finden Sie unter [Benutzereingaben in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9e5e9-117">For more information, see [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="9e5e9-118">Mausereignisse</span><span class="sxs-lookup"><span data-stu-id="9e5e9-118">Mouse Events</span></span>  
 <span data-ttu-id="9e5e9-119">Die Mausereignisse, die das Steuerelement behandeln kann sind <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, und <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="9e5e9-120">Ereignisname</span><span class="sxs-lookup"><span data-stu-id="9e5e9-120">Event Name</span></span>|<span data-ttu-id="9e5e9-121">Zu überschreibende Methode</span><span class="sxs-lookup"><span data-stu-id="9e5e9-121">Method to Override</span></span>|<span data-ttu-id="9e5e9-122">Beschreibung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9e5e9-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="9e5e9-123">Wird ausgelöst, wenn sich der Mauszeiger über dem Steuerelement befindet und eine Maustaste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="9e5e9-124">Wird ausgelöst, wenn der Mauszeiger zunächst auf den Bereich des Steuerelements trifft.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="9e5e9-125">Wird ausgelöst, wenn der Mauszeiger über das Steuerelement bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="9e5e9-126">Wird ausgelöst, wenn der Mauszeiger den Bereich des Steuerelements verlässt.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="9e5e9-127">Wird ausgelöst, wenn der Mauszeiger in den Bereich des Steuerelements wechselt.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="9e5e9-128">Wird ausgelöst, wenn die Maustaste losgelassen wird, während sich der Mauszeiger über dem Steuerelement befindet oder den Bereich des Steuerelements verlässt.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="9e5e9-129">Das folgende Codefragment zeigt ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.MouseDown> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="9e5e9-130">Das folgende Codefragment zeigt ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.MouseMove> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="9e5e9-131">Das folgende Codefragment zeigt ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.MouseUp> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9e5e9-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="9e5e9-132">Für den vollständigen Quellcode für die `FlashTrackBar` zugreifen können, finden Sie unter [Vorgehensweise: Erstellen ein Windows Forms-Steuerelements, die Status anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="9e5e9-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5e9-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e5e9-133">See also</span></span>
- [<span data-ttu-id="9e5e9-134">Ereignisse in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="9e5e9-134">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)
- [<span data-ttu-id="9e5e9-135">Definieren eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9e5e9-135">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="9e5e9-136">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9e5e9-136">Events</span></span>](../../../../docs/standard/events/index.md)
- [<span data-ttu-id="9e5e9-137">Benutzereingaben in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9e5e9-137">User Input in Windows Forms</span></span>](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
