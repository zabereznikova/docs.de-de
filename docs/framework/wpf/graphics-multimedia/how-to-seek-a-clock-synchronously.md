---
title: 'Gewusst wie: Synchrones Suchen einer Uhr'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d158629b428bda8e7749df393ad0724225b5a0a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-seek-a-clock-synchronously"></a><span data-ttu-id="309a2-102">Gewusst wie: Synchrones Suchen einer Uhr</span><span class="sxs-lookup"><span data-stu-id="309a2-102">How to: Seek a Clock Synchronously</span></span>
<span data-ttu-id="309a2-103">Verwenden der <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> Methode, um synchron eine Uhr zu einem bestimmten Zeitpunkt zu suchen.</span><span class="sxs-lookup"><span data-stu-id="309a2-103">Use the <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> method to seek a clock to a specific point synchronously.</span></span> <span data-ttu-id="309a2-104">Das folgende Beispiel zeigt sowohl den <xref:System.Windows.Media.Animation.ClockController.Seek%2A> und <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> Methoden eine <xref:System.Windows.Media.Animation.ClockController>.</span><span class="sxs-lookup"><span data-stu-id="309a2-104">The following example demonstrates both the <xref:System.Windows.Media.Animation.ClockController.Seek%2A> and <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> methods of a <xref:System.Windows.Media.Animation.ClockController>.</span></span>  
  
 <span data-ttu-id="309a2-105">In diesem Beispiel wird gezeigt, wie die Suche eine <xref:System.Windows.Media.Animation.Clock>ist ein Beispiel zum Durchsuchen eines Storyboards finden Sie unter [ein Storyboard synchron Seek](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .</span><span class="sxs-lookup"><span data-stu-id="309a2-105">This example shows how to seek a <xref:System.Windows.Media.Animation.Clock>; for an example showing how to seek a storyboard, see [Seek a Storyboard Synchronously](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .</span></span>  
  
## <a name="example"></a><span data-ttu-id="309a2-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="309a2-106">Example</span></span>  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
