---
title: "Gewusst wie: Anpassen der Teilstriche auf einem Schieberegler | Microsoft Docs"
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
  - "TickBar"
  - "Schieberegler-Steuerelement erstellen mit TickBar"
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Anpassen der Teilstriche auf einem Schieberegler
In diesem Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.Slider> Steuerelement, das Teilstriche angezeigt werden.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.Primitives.TickBar> zeigt beim Festlegen der <xref:System.Windows.Controls.Slider.TickPlacement%2A> -Eigenschaft auf einen anderen Wert als <xref:System.Windows.Controls.Primitives.TickPlacement>, dies ist der Standardwert.  
  
 Das folgende Beispiel zeigt, wie Sie erstellen ein <xref:System.Windows.Controls.Slider> mit einer <xref:System.Windows.Controls.Primitives.TickBar> , zeigt ein aktivieren. Die <xref:System.Windows.Controls.Slider.TickPlacement%2A> und <xref:System.Windows.Controls.Slider.TickFrequency%2A> Eigenschaften definieren die Position der Teilstriche und das Intervall zwischen ihnen. Beim Verschieben der <xref:System.Windows.Controls.Primitives.Thumb>, QuickInfo zeigt den Wert für die <xref:System.Windows.Controls.Slider>. Die <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> -Eigenschaft definiert, wo die QuickInfos angezeigt. Die <xref:System.Windows.Controls.Primitives.Thumb> Bewegung an die Position der Teilstriche entsprechen, da <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> Wert `true`.  
  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.Slider.Ticks%2A> -Eigenschaft Tick entlang der <xref:System.Windows.Controls.Slider> in unregelmäßigen Intervallen.  
  
 [!code-xml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Slider>   
 <xref:System.Windows.Controls.Primitives.TickBar>   
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>   
 [Schieberegler Gewusst-wie-Themen](http://msdn.microsoft.com/de-de/534be86c-afb2-425d-8186-631278a9925e)