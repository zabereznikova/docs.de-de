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
ms.openlocfilehash: 80b873e81acc243ff61257bc305c4f782b5bf867
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351827"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Vorgehensweise: Ändern der Canvas-Größe mithilfe eines Ziehpunkts
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Controls.Primitives.Thumb> Steuerelement zum Ändern der Größe einer <xref:System.Windows.Controls.Canvas> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.Primitives.Thumb> Steuerelement bietet Drag-Funktionen, die zum Verschieben oder Ändern von Steuerelementen durch die Überwachung verwendet werden kann die <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> und <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> Ereignisse der <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 Der Benutzer einen Ziehvorgang beginnt, durch Drücken die linke Maustaste gedrückt, wenn der Mauszeiger über die <xref:System.Windows.Controls.Primitives.Thumb> Steuerelement. Der Ziehvorgang fortgesetzt, solange die linke Maustaste gedrückt ist. Während des Ziehvorgangs die <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> kann mehr als einmal auftreten. Jedes Mal, es wird, die <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> -Klasse stellt die Änderung an der Position, die die Änderung in die Position des Mauszeigers entspricht. Wenn der Benutzer die linke Maustaste loslässt, ist der Drag-Vorgang abgeschlossen. Der Ziehvorgang gibt nur die neue Koordinaten. Es wird nicht automatisch neu positionieren, die <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.Primitives.Thumb> steuern, d. h. das untergeordnete Element einer <xref:System.Windows.Controls.Canvas> Steuerelement. Der Ereignishandler für die <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> Ereignis enthält die Logik zum Verschieben der <xref:System.Windows.Controls.Primitives.Thumb> und Ändern der Größe der <xref:System.Windows.Controls.Canvas>. Die Ereignishandler für die <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> und <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> Ereignis ändern der Farbe der <xref:System.Windows.Controls.Primitives.Thumb> während eines Ziehvorgangs. Das folgende Beispiel definiert die <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> -Ereignishandler, die verschiebt die <xref:System.Windows.Controls.Primitives.Thumb> und ändert die Größe der <xref:System.Windows.Controls.Canvas> als Reaktion auf eine mausbewegung.  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> -Ereignishandler.  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> -Ereignishandler.  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für das Thumb-Steuerelement ziehen](https://go.microsoft.com/fwlink/?LinkID=160042).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
