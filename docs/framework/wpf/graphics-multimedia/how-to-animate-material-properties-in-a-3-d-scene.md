---
title: 'Gewusst wie: Animieren von Materialeigenschaften in einer 3D-Szene'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112192"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a>Gewusst wie: Animieren von Materialeigenschaften in einer 3D-Szene
In diesem Beispiel wird <xref:System.Windows.Media.Brush.Opacity%2A> gezeigt, <xref:System.Windows.Media.Media3D.Material> wie die Eigenschaft des auf ein 3D-Modell angewendeten Zunisanimiert wird.  
  
 Im folgenden Codebeispiel <xref:System.Windows.Media.LinearGradientBrush> wird definiert, welche Verwendung als auf das <xref:System.Windows.Media.Media3D.Material> 3D-Objekt angewendet wird.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 Die <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft <xref:System.Windows.Media.LinearGradientBrush> dieser wird mithilfe des Codebeispiels unten animiert.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
