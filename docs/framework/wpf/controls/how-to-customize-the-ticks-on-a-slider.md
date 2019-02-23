---
title: 'Vorgehensweise: Anpassen der Teilstriche auf einem Schieberegler'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 0317668bf4f6721af698e1a8b966493b2c127012
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746648"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="e64a3-102">Vorgehensweise: Anpassen der Teilstriche auf einem Schieberegler</span><span class="sxs-lookup"><span data-stu-id="e64a3-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="e64a3-103">Dieses Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Slider> -Steuerelement mit Teilstrichen.</span><span class="sxs-lookup"><span data-stu-id="e64a3-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e64a3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e64a3-104">Example</span></span>  
 <span data-ttu-id="e64a3-105">Die <xref:System.Windows.Controls.Primitives.TickBar> angezeigt wird, wenn Sie festlegen, die <xref:System.Windows.Controls.Slider.TickPlacement%2A> Eigenschaft, um einen anderen Wert als <xref:System.Windows.Controls.Primitives.TickPlacement.None>, dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="e64a3-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="e64a3-106">Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Slider> mit einem <xref:System.Windows.Controls.Primitives.TickBar> , dass die Anzeige von Teilstrichen.</span><span class="sxs-lookup"><span data-stu-id="e64a3-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="e64a3-107">Die <xref:System.Windows.Controls.Slider.TickPlacement%2A> und <xref:System.Windows.Controls.Slider.TickFrequency%2A> Eigenschaften definieren die Position der Teilstriche und das Intervall zwischen ihnen.</span><span class="sxs-lookup"><span data-stu-id="e64a3-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="e64a3-108">Beim Verschieben der <xref:System.Windows.Controls.Primitives.Thumb>, QuickInfos anzeigen, den Wert des der <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="e64a3-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="e64a3-109">Die <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> Eigenschaft definiert, in dem die QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e64a3-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="e64a3-110">Die <xref:System.Windows.Controls.Primitives.Thumb> -Bewegungen entsprechen der Position der Teilstriche da <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> nastaven NA hodnotu `true`.</span><span class="sxs-lookup"><span data-stu-id="e64a3-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="e64a3-111">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.Slider.Ticks%2A> Eigenschaft Tick Marks entlang erstellen die <xref:System.Windows.Controls.Slider> in unregelmäßigen Intervallen.</span><span class="sxs-lookup"><span data-stu-id="e64a3-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e64a3-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e64a3-112">See also</span></span>
- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- <span data-ttu-id="e64a3-113">[Vorgehensweise: Binden eines Schiebereglers an einen Eigenschaftswert](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e64a3-113">[How to: Bind a Slider to a Property Value](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span></span>
