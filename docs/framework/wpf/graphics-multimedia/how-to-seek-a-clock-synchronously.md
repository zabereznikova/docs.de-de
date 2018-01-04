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
ms.workload: dotnet
ms.openlocfilehash: 90611e0b18e58e4c24b44e7c87cba56e4b0b01ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-seek-a-clock-synchronously"></a>Gewusst wie: Synchrones Suchen einer Uhr
Verwenden der <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> Methode, um synchron eine Uhr zu einem bestimmten Zeitpunkt zu suchen. Das folgende Beispiel zeigt sowohl den <xref:System.Windows.Media.Animation.ClockController.Seek%2A> und <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> Methoden eine <xref:System.Windows.Media.Animation.ClockController>.  
  
 In diesem Beispiel wird gezeigt, wie die Suche eine <xref:System.Windows.Media.Animation.Clock>ist ein Beispiel zum Durchsuchen eines Storyboards finden Sie unter [ein Storyboard synchron Seek](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
