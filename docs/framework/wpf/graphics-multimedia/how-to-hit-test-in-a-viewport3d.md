---
title: 'Vorgehensweise: Treffertest in Viewport3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 0906fc0da363f9b4022eea863ec1140c8eeb2da2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494239"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>Vorgehensweise: Treffertest in Viewport3D
Dieses Beispiel zeigt, wie ein Treffertest für 3D-Elemente in einem <xref:System.Windows.Controls.Viewport3D>.  
  
 Da <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2D- und 3D-Spiele gibt Informationen zurück, es ist möglich, durchlaufen die Testergebnisse nur 3D Ergebnisse zu lesen.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 Die <xref:System.Windows.Media.HitTestResultBehavior> in den folgenden Code bestimmt, wie die Treffertestergebnissen verarbeitet werden.  `UpdateResultInfo` und `UpdateMaterial` lokal definierte Methoden sind.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a>Siehe auch
- [Drücken Sie Beispiel zu Leistungstests in 3D](https://go.microsoft.com/fwlink/?LinkID=159959)
