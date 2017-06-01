---
title: "Gewusst wie: &#196;ndern der Canvas-Gr&#246;&#223;e mithilfe eines Ziehpunkts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Canvas-Steuerelement"
  - "Steuerelemente, Canvas"
  - "Steuerelemente, Ziehpunkt"
  - "Ändern der Größe des Canvas-Steuerelements"
  - "Thumb-Steuerelement"
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: &#196;ndern der Canvas-Gr&#246;&#223;e mithilfe eines Ziehpunkts
In diesem Beispiel wird dargestellt, wie Sie mithilfe eines <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelements die Größe von <xref:System.Windows.Controls.Canvas>\-Steuerelementen ändern können.  
  
## Beispiel  
 Das <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelement bietet eine Ziehfunktionalität, mit der sich Steuerelemente verschieben oder in der Größe ändern lassen, indem die Ereignisse <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> und <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> von <xref:System.Windows.Controls.Primitives.Thumb> überwacht werden.  
  
 Der Benutzer startet einen Ziehvorgang, indem er die linke Maustaste drückt, während sich der Mauszeiger über dem <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelement befindet.  Der Ziehvorgang dauert so lange an, wie die linke Maustaste gedrückt bleibt.  Während des Ziehvorgangs kann <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> mehr als einmal auftreten.  Bei jedem Auftreten zeigt die <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs>\-Klasse die jeweilige Positionsänderung des verschobenen Mauszeigers an.  Wenn der Benutzer die linke Maustaste loslässt, wird der Ziehvorgang beendet.  Der Ziehvorgang gibt nur neue Koordinaten an, das <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelement wird jedoch nicht automatisch neu positioniert.  
  
 Im folgenden Beispiel ist ein <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelement dargestellt, das das untergeordnete Element eines <xref:System.Windows.Controls.Canvas>\-Steuerelements ist.  Der Ereignishandler für dessen <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>\-Ereignis enthält die Programmlogik zum Verschieben des <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelements und zum Ändern der Größe des <xref:System.Windows.Controls.Canvas>\-Steuerelements.  Die Ereignishandler für die Ereignisse <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> und <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> ändern die Farbe des <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelements während eines Ziehvorgangs.  Im folgenden Beispiel wird das <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelement definiert.  
  
 [!code-xml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 Im folgende Beispiel wird der <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>\-Ereignishandler dargestellt, der das <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelement verschiebt und die Größe des <xref:System.Windows.Controls.Canvas>\-Steuerelements bei einer Mausbewegung ändert.  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 Im folgenden Beispiel wird der <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>\-Ereignishandler dargestellt.  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 Im folgenden Beispiel wird der <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>\-Ereignishandler dargestellt.  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für das Ziehen mir der Ziehpunktfunktion](http://go.microsoft.com/fwlink/?LinkID=160042).  
  
## Siehe auch  
 <xref:System.Windows.Controls.Primitives.Thumb>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>