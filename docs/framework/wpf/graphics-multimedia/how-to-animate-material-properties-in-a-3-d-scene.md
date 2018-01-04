---
title: 'Gewusst wie: Animieren von Material-Eigenschaften in einer 3D-Szene'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16d7ba089730a58106448d8a6889b362042532e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a>Gewusst wie: Animieren von Material-Eigenschaften in einer 3D-Szene
In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.Material> angewendet, um eine [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Modell.  
  
 Das folgende Codebeispiel definiert die <xref:System.Windows.Media.LinearGradientBrush> verwendet als die <xref:System.Windows.Media.Media3D.Material> auf das 3D-Objekt angewendet.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 Die <xref:System.Windows.Media.Brush.Opacity%2A> -Eigenschaft dieser <xref:System.Windows.Media.LinearGradientBrush> wird im folgenden Codebeispiel wird mit animiert.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das vollständige Beispiel.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer 3D-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
