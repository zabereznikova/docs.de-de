---
title: "Gewusst wie: Ändern der Canvas-Größe mithilfe eines Ziehpunkts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c73509d58112e47f707e82243005bfdf9edca151
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Gewusst wie: Ändern der Canvas-Größe mithilfe eines Ziehpunkts
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Controls.Primitives.Thumb> Steuerelement, um die Größe einer <xref:System.Windows.Controls.Canvas> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.Primitives.Thumb> Steuerelement verfügt über Drag-Funktionen, die verwendet werden kann, verschieben oder Steuerelemente anpassen, indem Sie die Überwachung der <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> und <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> Ereignisse der <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 Der Benutzer einen Ziehvorgang beginnt, durch Drücken die linke Maustaste gedrückt, wenn der Mauszeiger über dem <xref:System.Windows.Controls.Primitives.Thumb> Steuerelement. Der Ziehvorgang fortgesetzt wird, solange die linke Maustaste gedrückt ist. Während des Ziehvorgangs die <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> mehr als einmal auftreten kann. Jedes Mal, es tritt auf, die <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> -Klasse stellt die Änderung an der Position, die die Änderung der Position des Mauszeigers entspricht. Wenn der Benutzer die linke Maustaste loslässt, wird der Ziehvorgang beendet. Der Ziehvorgang bietet nur die neue Koordinaten; Es wird nicht automatisch neu positionieren, der <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.Primitives.Thumb> steuern, d. h. das untergeordnete Element von einem <xref:System.Windows.Controls.Canvas> Steuerelement. Der Ereignishandler für die <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> Ereignis enthält die Logik zum Verschieben der <xref:System.Windows.Controls.Primitives.Thumb> und Ändern der Größe der <xref:System.Windows.Controls.Canvas>. Die Ereignishandler für die <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> und <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> Ereignis ändern der Farbe der <xref:System.Windows.Controls.Primitives.Thumb> während eines Ziehvorgangs ein. Das folgende Beispiel definiert die <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> Ereignishandler, der verschiebt der <xref:System.Windows.Controls.Primitives.Thumb> und passt seine Größe der <xref:System.Windows.Controls.Canvas> als Antwort auf eine Bewegung der Maus.  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> -Ereignishandler.  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> -Ereignishandler.  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Das vollständige Beispiel finden Sie unter [Thumb Drag Functionality Sample](http://go.microsoft.com/fwlink/?LinkID=160042).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Primitives.Thumb>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
