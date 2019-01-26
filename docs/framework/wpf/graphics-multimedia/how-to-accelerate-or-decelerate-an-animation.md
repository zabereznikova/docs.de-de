---
title: 'Vorgehensweise: Beschleunigen oder Verlangsamen einer Animation'
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 28c7940b9a60f3bd485ba2aea77e6bc1ae5fec54
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2019
ms.locfileid: "55065842"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="00dde-102">Vorgehensweise: Beschleunigen oder Verlangsamen einer Animation</span><span class="sxs-lookup"><span data-stu-id="00dde-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="00dde-103">In diesem Beispiel wird veranschaulicht, wie Sie eine Animation zu beschleunigen und im Laufe der Zeit verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="00dde-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="00dde-104">Im folgenden Beispiel werden mehrere Rechtecke von Animationen mit verschiedenen animiert <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> und <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="00dde-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00dde-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00dde-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="00dde-106">In diesem Beispiel wurde Code ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="00dde-106">Code has been omitted from this example.</span></span> <span data-ttu-id="00dde-107">Den vollständigen Code finden Sie unter den [Zeitsteuerungsverhalten von Animationen (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) oder [Zeitsteuerungsverhalten "Animation" (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span><span class="sxs-lookup"><span data-stu-id="00dde-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
