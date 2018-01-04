---
title: "Gewusst wie: Animieren der Durchlässigkeit eines Elements oder eines Pinsels"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3b750e6ee21c8347d3896ec290f0ff564cc0a2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a><span data-ttu-id="fe316-102">Gewusst wie: Animieren der Durchlässigkeit eines Elements oder eines Pinsels</span><span class="sxs-lookup"><span data-stu-id="fe316-102">How to: Animate the Opacity of an Element or Brush</span></span>
<span data-ttu-id="fe316-103">Um ein FrameworkElement ein-und auszublenden, können Sie animieren seine <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft oder Sie können dem animiert werden soll die <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft von der <xref:System.Windows.Media.Brush> (oder Pinsel) verwendet, um es zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="fe316-103">To make a framework element fade in and out of view, you can animate its <xref:System.Windows.UIElement.Opacity%2A> property or you can animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Brush> (or brushes) used to paint it.</span></span> <span data-ttu-id="fe316-104">Animieren das Element Deckkraft vereinfacht und seine untergeordneten Elemente einblenden und ausblenden, aber Animieren des Pinsels, der zum Zeichnen des Elements verwendet wird, können Sie präziser ausgeblendet, welcher Teil des Elements wird.</span><span class="sxs-lookup"><span data-stu-id="fe316-104">Animating the element's opacity makes it and its children fade in and out of view, but animating the brush used to paint the element enables you to be more selective about which portion of the element fades.</span></span> <span data-ttu-id="fe316-105">Sie können z. B. die Deckkraft eines Pinsels zum Zeichnen des Hintergrunds einer Schaltfläche verwendet animieren.</span><span class="sxs-lookup"><span data-stu-id="fe316-105">For example, you could animate the opacity of a brush used to paint a button's background.</span></span> <span data-ttu-id="fe316-106">Dies würde dazu führen, dass der Hintergrund der Schaltfläche zum ein-und Ausblenden der Ansicht, lassen Sie den Text vollständig deckend.</span><span class="sxs-lookup"><span data-stu-id="fe316-106">This would cause the button's background to fade in and out of view, while leaving its text fully opaque.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe316-107">Animieren der <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.Brush> bietet Leistungsvorteile gegenüber der Animierung der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft eines Elements.</span><span class="sxs-lookup"><span data-stu-id="fe316-107">Animating the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.Brush> provides performance benefits over animating the <xref:System.Windows.UIElement.Opacity%2A> property of an element.</span></span>  
  
 <span data-ttu-id="fe316-108">Im folgenden Beispiel werden zwei Schaltflächen animiert, damit sie ein-und auszublenden.</span><span class="sxs-lookup"><span data-stu-id="fe316-108">In the following example, two buttons are animated so that they fade in and out of view.</span></span> <span data-ttu-id="fe316-109">Die Deckkraft des ersten <xref:System.Windows.Controls.Button> wird von animiert `1.0` auf `0.0` über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden.</span><span class="sxs-lookup"><span data-stu-id="fe316-109">The Opacity of the first <xref:System.Windows.Controls.Button> is animated from `1.0` to `0.0` over a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> of five seconds.</span></span> <span data-ttu-id="fe316-110">Die zweite Schaltfläche wird ebenfalls animiert, aber die Deckkraft des Pinsels geändert, die zum Zeichnen verwendet seine <xref:System.Windows.Controls.Control.Background%2A> anstatt die Deckkraft der gesamte Schaltfläche animiert wird.</span><span class="sxs-lookup"><span data-stu-id="fe316-110">The second button is also animated, but the Opacity of the SolidColorBrush used to paint its <xref:System.Windows.Controls.Control.Background%2A> is animated rather than the opacity of the entire button.</span></span> <span data-ttu-id="fe316-111">Wenn das Beispiel ausgeführt wird, wird die erste Schaltfläche vollständig in und aus der Ansicht ausgeblendet, während nur der Hintergrund der zweiten Schaltfläche ein-und ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe316-111">When the example is run, the first button completely fades in and out of view, while only the background of the second button fades in and out of view.</span></span> <span data-ttu-id="fe316-112">Text und Rahmen bleiben vollständig deckend ist.</span><span class="sxs-lookup"><span data-stu-id="fe316-112">Its text and border remain fully opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe316-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe316-113">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 <span data-ttu-id="fe316-114">Code wurde aus diesem Beispiel ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="fe316-114">Code has been omitted from this example.</span></span> <span data-ttu-id="fe316-115">Im vollständige Beispiel wird auch gezeigt, wie die Deckkraft des Animieren einer <xref:System.Windows.Media.Color> innerhalb einer <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="fe316-115">The full sample also shows how to animate the opacity of a <xref:System.Windows.Media.Color> within a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="fe316-116">Das vollständige Beispiel finden Sie unter der [animieren die Deckkraft einer Element-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159968).</span><span class="sxs-lookup"><span data-stu-id="fe316-116">For the full sample, see the [Animating the Opacity of an Element Sample](http://go.microsoft.com/fwlink/?LinkID=159968).</span></span>
