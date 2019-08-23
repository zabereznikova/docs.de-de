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
ms.openlocfilehash: f92b742c3f6feec72e5b3150204d7d984636281d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934092"
---
# <a name="handling-user-input"></a><span data-ttu-id="5c8d7-102">Behandeln von Benutzereingaben</span><span class="sxs-lookup"><span data-stu-id="5c8d7-102">Handling User Input</span></span>
<span data-ttu-id="5c8d7-103">Dieses Thema beschreibt die Haupt Tastatur-und Mausereignisse, <xref:System.Windows.Forms.Control?displayProperty=nameWithType>die von bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5c8d7-104">Beim Bearbeiten eines Ereignisses sollten Autoren von Steuerelementen die geschützte Methode `On`*EventName* überschreiben, statt einen Delegaten an das Ereignis anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="5c8d7-105">Zum Überprüfen der Ereignisse siehe [Auslösen von Ereignissen aus einer Komponente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="5c8d7-105">For a review of events, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c8d7-106">Wenn einem Ereignis keine Daten zugeordnet sind, wird eine Instanz der Basisklasse <xref:System.EventArgs> als Argument an die `On`EventName-Methode übermittelt.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="5c8d7-107">Tastaturereignisse</span><span class="sxs-lookup"><span data-stu-id="5c8d7-107">Keyboard Events</span></span>  
 <span data-ttu-id="5c8d7-108">Die gängigen Tastatur Ereignisse, die von Ihrem Steuerelement <xref:System.Windows.Forms.Control.KeyDown>behandelt <xref:System.Windows.Forms.Control.KeyPress>werden können <xref:System.Windows.Forms.Control.KeyUp>, sind, und.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="5c8d7-109">Ereignisname</span><span class="sxs-lookup"><span data-stu-id="5c8d7-109">Event Name</span></span>|<span data-ttu-id="5c8d7-110">Zu überschreibende Methode</span><span class="sxs-lookup"><span data-stu-id="5c8d7-110">Method to Override</span></span>|<span data-ttu-id="5c8d7-111">Beschreibung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c8d7-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="5c8d7-112">Wird nur ausgelöst, wenn anfangs eine Taste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="5c8d7-113">Wird jedes Mal ausgelöst, wenn eine Taste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="5c8d7-114">Wenn eine Taste angehalten wird, wird <xref:System.Windows.Forms.Control.KeyPress> ein-Ereignis mit der Wiederholungsrate ausgelöst, die vom Betriebssystem festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="5c8d7-115">Wird ausgelöst, wenn eine Taste losgelassen wird.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="5c8d7-116">Das Bearbeiten von Tastatureingaben ist wesentlich komplexer als das Überschreiben der Ereignisse in der obigen Tabelle und würde Rahmen dieses Themas sprengen.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="5c8d7-117">Weitere Informationen finden Sie unter [Benutzereingaben in Windows Forms](../user-input-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5c8d7-117">For more information, see [User Input in Windows Forms](../user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="5c8d7-118">Mausereignisse</span><span class="sxs-lookup"><span data-stu-id="5c8d7-118">Mouse Events</span></span>  
 <span data-ttu-id="5c8d7-119">Die Mausereignisse, die von Ihrem Steuerelement <xref:System.Windows.Forms.Control.MouseDown>behandelt werden können, <xref:System.Windows.Forms.Control.MouseMove>sind, <xref:System.Windows.Forms.Control.MouseUp> <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, und.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="5c8d7-120">Ereignisname</span><span class="sxs-lookup"><span data-stu-id="5c8d7-120">Event Name</span></span>|<span data-ttu-id="5c8d7-121">Zu überschreibende Methode</span><span class="sxs-lookup"><span data-stu-id="5c8d7-121">Method to Override</span></span>|<span data-ttu-id="5c8d7-122">Beschreibung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c8d7-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="5c8d7-123">Wird ausgelöst, wenn sich der Mauszeiger über dem Steuerelement befindet und eine Maustaste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="5c8d7-124">Wird ausgelöst, wenn der Mauszeiger zunächst auf den Bereich des Steuerelements trifft.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="5c8d7-125">Wird ausgelöst, wenn der Mauszeiger über das Steuerelement bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="5c8d7-126">Wird ausgelöst, wenn der Mauszeiger den Bereich des Steuerelements verlässt.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="5c8d7-127">Wird ausgelöst, wenn der Mauszeiger in den Bereich des Steuerelements wechselt.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="5c8d7-128">Wird ausgelöst, wenn die Maustaste losgelassen wird, während sich der Mauszeiger über dem Steuerelement befindet oder den Bereich des Steuerelements verlässt.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="5c8d7-129">Das folgende Code Fragment zeigt ein Beispiel für das über <xref:System.Windows.Forms.Control.MouseDown> Schreiben des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="5c8d7-130">Das folgende Code Fragment zeigt ein Beispiel für das über <xref:System.Windows.Forms.Control.MouseMove> Schreiben des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="5c8d7-131">Das folgende Code Fragment zeigt ein Beispiel für das über <xref:System.Windows.Forms.Control.MouseUp> Schreiben des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="5c8d7-132">Den gesamten Quellcode für das `FlashTrackBar` Beispiel finden [Sie unter Gewusst wie: Erstellt ein Windows Forms Steuerelement, das](how-to-create-a-windows-forms-control-that-shows-progress.md)den Fortschritt anzeigt.</span><span class="sxs-lookup"><span data-stu-id="5c8d7-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c8d7-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c8d7-133">See also</span></span>

- [<span data-ttu-id="5c8d7-134">Ereignisse in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="5c8d7-134">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="5c8d7-135">Definieren eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c8d7-135">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="5c8d7-136">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="5c8d7-136">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="5c8d7-137">Benutzereingaben in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c8d7-137">User Input in Windows Forms</span></span>](../user-input-in-windows-forms.md)
