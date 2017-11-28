---
title: 'Gewusst wie: Anpassen der Teilstriche auf einem Schieberegler'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d266d85e10ca8e77cd32338096cf3a3b761c188
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>Gewusst wie: Anpassen der Teilstriche auf einem Schieberegler
In diesem Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.Slider> -Steuerelement mit Teilstrichen.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.Primitives.TickBar> wird angezeigt, wenn Sie festlegen, die <xref:System.Windows.Controls.Slider.TickPlacement%2A> -Eigenschaft auf einen anderen Wert als <xref:System.Windows.Controls.Primitives.TickPlacement.None>, dies ist der Standardwert.  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.Slider> mit einem <xref:System.Windows.Controls.Primitives.TickBar> , zeigt Markierungen Teilstrichen. Die <xref:System.Windows.Controls.Slider.TickPlacement%2A> und <xref:System.Windows.Controls.Slider.TickFrequency%2A> Eigenschaften definieren die Position der Teilstriche und das Intervall zwischen ihnen. Beim Verschieben der <xref:System.Windows.Controls.Primitives.Thumb>, den Wert der in QuickInfos der <xref:System.Windows.Controls.Slider>. Die <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> Eigenschaft definiert, wo die QuickInfos angezeigt. Die <xref:System.Windows.Controls.Primitives.Thumb> -Bewegungen, die an die Position der Teilstriche entsprechen, da <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> festgelegt ist, um `true`.  
  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.Slider.Ticks%2A> Eigenschaft zum Erstellen von Teilstrichen entlang der <xref:System.Windows.Controls.Slider> in unregelmäßigen Intervallen.  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Slider>  
 <xref:System.Windows.Controls.Primitives.TickBar>  
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>  
 [Slider How-to Topics (Vorgehensweisen für Schieberegler)](http://msdn.microsoft.com/en-us/534be86c-afb2-425d-8186-631278a9925e)
