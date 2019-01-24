---
title: 'Vorgehensweise: Anpassen der Teilstriche auf einem Schieberegler'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: b6ade07b0b4c04578d2523d6d8ba992b8b2d31f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696671"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>Vorgehensweise: Anpassen der Teilstriche auf einem Schieberegler
Dieses Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Slider> -Steuerelement mit Teilstrichen.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.Primitives.TickBar> angezeigt wird, wenn Sie festlegen, die <xref:System.Windows.Controls.Slider.TickPlacement%2A> Eigenschaft, um einen anderen Wert als <xref:System.Windows.Controls.Primitives.TickPlacement.None>, dies ist der Standardwert.  
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Slider> mit einem <xref:System.Windows.Controls.Primitives.TickBar> , dass die Anzeige von Teilstrichen. Die <xref:System.Windows.Controls.Slider.TickPlacement%2A> und <xref:System.Windows.Controls.Slider.TickFrequency%2A> Eigenschaften definieren die Position der Teilstriche und das Intervall zwischen ihnen. Beim Verschieben der <xref:System.Windows.Controls.Primitives.Thumb>, QuickInfos anzeigen, den Wert des der <xref:System.Windows.Controls.Slider>. Die <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> Eigenschaft definiert, in dem die QuickInfo angezeigt. Die <xref:System.Windows.Controls.Primitives.Thumb> -Bewegungen entsprechen der Position der Teilstriche da <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> nastaven NA hodnotu `true`.  
  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.Slider.Ticks%2A> Eigenschaft Tick Marks entlang erstellen die <xref:System.Windows.Controls.Slider> in unregelmäßigen Intervallen.  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [Slider How-to Topics (Vorgehensweisen für Schieberegler)](https://msdn.microsoft.com/library/534be86c-afb2-425d-8186-631278a9925e)
