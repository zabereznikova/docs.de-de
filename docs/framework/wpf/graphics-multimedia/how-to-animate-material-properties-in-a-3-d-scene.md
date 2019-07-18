---
title: 'Vorgehensweise: Animieren von Materialeigenschaften in einer 3D-Szene'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: 8dfd7f01b87e2becfbcf57544ec4f8340cf8d5cc
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662551"
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a>Vorgehensweise: Animieren von Materialeigenschaften in einer 3D-Szene
Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.Material> auf ein 3D-Modell angewendet.  
  
 Das folgende Codebeispiel definiert die <xref:System.Windows.Media.LinearGradientBrush> verwendet als die <xref:System.Windows.Media.Media3D.Material> auf das 3D-Objekt angewendet.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 Die <xref:System.Windows.Media.Brush.Opacity%2A> -Eigenschaft dieses <xref:System.Windows.Media.LinearGradientBrush> wird im folgenden Codebeispiel wird mithilfe animiert.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
