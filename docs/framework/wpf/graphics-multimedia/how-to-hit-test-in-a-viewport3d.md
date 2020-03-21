---
title: 'Gewusst wie: Treffertest in Viewport3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D visuals [WPF], hit-testing for
- hit tests [WPF], for 3D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 34bc86349332293e40aca5743cbabb2a48634da6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112088"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>Gewusst wie: Treffertest in Viewport3D

Dieses Beispiel zeigt, wie Sie den Test <xref:System.Windows.Controls.Viewport3D>für 3D-Visuals in einem treffen.

Da <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2D- und 3D-Informationen zurückgegeben werden, ist es möglich, die Testergebnisse zu durchlaufen, um nur 3D-Ergebnisse zu lesen.

[!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
[!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]

Der <xref:System.Windows.Media.HitTestResultBehavior> im folgenden Code beschriebene Art und Weise, wie die Treffertestergebnisse verarbeitet werden. `UpdateResultInfo`und `UpdateMaterial` sind lokal definierte Methoden.

[!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
[!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]
