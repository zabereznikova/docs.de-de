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
ms.workload: dotnet
ms.openlocfilehash: d21d2950ed228bf588a202419c222ee86dde5b0d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="8e518-102">Gewusst wie: Anpassen der Teilstriche auf einem Schieberegler</span><span class="sxs-lookup"><span data-stu-id="8e518-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="8e518-103">In diesem Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.Slider> -Steuerelement mit Teilstrichen.</span><span class="sxs-lookup"><span data-stu-id="8e518-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e518-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e518-104">Example</span></span>  
 <span data-ttu-id="8e518-105">Die <xref:System.Windows.Controls.Primitives.TickBar> wird angezeigt, wenn Sie festlegen, die <xref:System.Windows.Controls.Slider.TickPlacement%2A> -Eigenschaft auf einen anderen Wert als <xref:System.Windows.Controls.Primitives.TickPlacement.None>, dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="8e518-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="8e518-106">Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.Slider> mit einem <xref:System.Windows.Controls.Primitives.TickBar> , zeigt Markierungen Teilstrichen.</span><span class="sxs-lookup"><span data-stu-id="8e518-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="8e518-107">Die <xref:System.Windows.Controls.Slider.TickPlacement%2A> und <xref:System.Windows.Controls.Slider.TickFrequency%2A> Eigenschaften definieren die Position der Teilstriche und das Intervall zwischen ihnen.</span><span class="sxs-lookup"><span data-stu-id="8e518-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="8e518-108">Beim Verschieben der <xref:System.Windows.Controls.Primitives.Thumb>, den Wert der in QuickInfos der <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="8e518-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="8e518-109">Die <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> Eigenschaft definiert, wo die QuickInfos angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e518-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="8e518-110">Die <xref:System.Windows.Controls.Primitives.Thumb> -Bewegungen, die an die Position der Teilstriche entsprechen, da <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> festgelegt ist, um `true`.</span><span class="sxs-lookup"><span data-stu-id="8e518-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="8e518-111">Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.Slider.Ticks%2A> Eigenschaft zum Erstellen von Teilstrichen entlang der <xref:System.Windows.Controls.Slider> in unregelmäßigen Intervallen.</span><span class="sxs-lookup"><span data-stu-id="8e518-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8e518-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e518-112">See Also</span></span>  
 <xref:System.Windows.Controls.Slider>  
 <xref:System.Windows.Controls.Primitives.TickBar>  
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>  
 [<span data-ttu-id="8e518-113">Slider How-to Topics (Vorgehensweisen für Schieberegler)</span><span class="sxs-lookup"><span data-stu-id="8e518-113">Slider How-to Topics</span></span>](http://msdn.microsoft.com/library/534be86c-afb2-425d-8186-631278a9925e)
