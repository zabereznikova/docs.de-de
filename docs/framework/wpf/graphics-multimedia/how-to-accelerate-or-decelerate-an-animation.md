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
# <a name="how-to-accelerate-or-decelerate-an-animation"></a>Vorgehensweise: Beschleunigen oder Verlangsamen einer Animation
In diesem Beispiel wird veranschaulicht, wie Sie eine Animation zu beschleunigen und im Laufe der Zeit verlangsamen. Im folgenden Beispiel werden mehrere Rechtecke von Animationen mit verschiedenen animiert <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> und <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> Einstellungen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 In diesem Beispiel wurde Code ausgelassen. Den vollständigen Code finden Sie unter den [Zeitsteuerungsverhalten von Animationen (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) oder [Zeitsteuerungsverhalten "Animation" (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).
