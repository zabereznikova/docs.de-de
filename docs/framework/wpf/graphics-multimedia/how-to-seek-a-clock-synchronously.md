---
title: 'Vorgehensweise: Synchrones Suchen einer Uhr'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651258"
---
# <a name="how-to-seek-a-clock-synchronously"></a>Vorgehensweise: Synchrones Suchen einer Uhr
Verwenden der <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> Methode synchron eine Uhr zu einem bestimmten Zeitpunkt zu suchen. Das folgende Beispiel zeigt sowohl den <xref:System.Windows.Media.Animation.ClockController.Seek%2A> und <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> Methoden eine <xref:System.Windows.Media.Animation.ClockController>.  
  
 Dieses Beispiel zeigt, wie die Suche eine <xref:System.Windows.Media.Animation.Clock>; ein Beispiel für das Durchsuchen eines Storyboards finden Sie unter [Synchrones Suchen in einem Storyboard](how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
