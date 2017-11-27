---
title: 'Gewusst wie: Treffertest in Viewport3D'
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
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: efd8016e0169a258dbe7b6d9a54a81b1cda94ee4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>Gewusst wie: Treffertest in Viewport3D
Dieses Beispiel zeigt, wie ein Treffertest für 3D-Elemente in einem <xref:System.Windows.Controls.Viewport3D>.  
  
 Da <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> gibt 2D- und 3D-Ausrichtung Informationen zurück, es ist möglich, durchlaufen die Testergebnisse nur 3D Ergebnisse zu lesen.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 Die <xref:System.Windows.Media.HitTestResultBehavior> in den folgenden Code bestimmt, wie die Ergebnisse des Treffertests verarbeitet werden.  `UpdateResultInfo`und `UpdateMaterial` sind lokal definierte Methoden.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a>Siehe auch  
 [Bestimmt bei 3D-Elementen erreicht, Beispiel](http://go.microsoft.com/fwlink/?LinkID=159959)
