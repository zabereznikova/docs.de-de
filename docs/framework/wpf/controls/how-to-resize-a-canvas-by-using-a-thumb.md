---
title: 'Vorgehensweise: Ändern der Canvas-Größe mithilfe eines Ziehpunkts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: 14942157429b029147d47e2f88428c56e66523d1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146353"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="fef7e-102">Vorgehensweise: Ändern der Canvas-Größe mithilfe eines Ziehpunkts</span><span class="sxs-lookup"><span data-stu-id="fef7e-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="fef7e-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Controls.Primitives.Thumb> Steuerelement zum Ändern der Größe einer <xref:System.Windows.Controls.Canvas> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fef7e-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fef7e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fef7e-104">Example</span></span>  
 <span data-ttu-id="fef7e-105">Die <xref:System.Windows.Controls.Primitives.Thumb> Steuerelement bietet Drag-Funktionen, die zum Verschieben oder Ändern von Steuerelementen durch die Überwachung verwendet werden kann die <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> und <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> Ereignisse der <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="fef7e-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="fef7e-106">Der Benutzer einen Ziehvorgang beginnt, durch Drücken die linke Maustaste gedrückt, wenn der Mauszeiger über die <xref:System.Windows.Controls.Primitives.Thumb> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fef7e-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="fef7e-107">Der Ziehvorgang fortgesetzt, solange die linke Maustaste gedrückt ist.</span><span class="sxs-lookup"><span data-stu-id="fef7e-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="fef7e-108">Während des Ziehvorgangs die <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> kann mehr als einmal auftreten.</span><span class="sxs-lookup"><span data-stu-id="fef7e-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="fef7e-109">Jedes Mal, es wird, die <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> -Klasse stellt die Änderung an der Position, die die Änderung in die Position des Mauszeigers entspricht.</span><span class="sxs-lookup"><span data-stu-id="fef7e-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="fef7e-110">Wenn der Benutzer die linke Maustaste loslässt, ist der Drag-Vorgang abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fef7e-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="fef7e-111">Der Ziehvorgang gibt nur die neue Koordinaten. Es wird nicht automatisch neu positionieren, die <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="fef7e-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="fef7e-112">Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.Primitives.Thumb> steuern, d. h. das untergeordnete Element einer <xref:System.Windows.Controls.Canvas> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fef7e-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="fef7e-113">Der Ereignishandler für die <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> Ereignis enthält die Logik zum Verschieben der <xref:System.Windows.Controls.Primitives.Thumb> und Ändern der Größe der <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="fef7e-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="fef7e-114">Die Ereignishandler für die <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> und <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> Ereignis ändern der Farbe der <xref:System.Windows.Controls.Primitives.Thumb> während eines Ziehvorgangs.</span><span class="sxs-lookup"><span data-stu-id="fef7e-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="fef7e-115">Das folgende Beispiel definiert die <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="fef7e-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="fef7e-116">Das folgende Beispiel zeigt die <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> -Ereignishandler, die verschiebt die <xref:System.Windows.Controls.Primitives.Thumb> und ändert die Größe der <xref:System.Windows.Controls.Canvas> als Reaktion auf eine mausbewegung.</span><span class="sxs-lookup"><span data-stu-id="fef7e-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="fef7e-117">Das folgende Beispiel zeigt die <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="fef7e-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="fef7e-118">Das folgende Beispiel zeigt die <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="fef7e-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="fef7e-119">Das vollständige Beispiel finden Sie unter [Beispiel für das Thumb-Steuerelement ziehen](https://go.microsoft.com/fwlink/?LinkID=160042).</span><span class="sxs-lookup"><span data-stu-id="fef7e-119">For the complete sample, see [Thumb Drag Functionality Sample](https://go.microsoft.com/fwlink/?LinkID=160042).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef7e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fef7e-120">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
