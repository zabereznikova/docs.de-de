---
title: 'Gewusst wie: Anwenden mehrerer Transformationen auf ein Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 3ef11104b2a4fc775d29d2a388c9a70a69a3f10f
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112114"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>Gewusst wie: Anwenden mehrerer Transformationen auf ein Objekt
In diesem Beispiel wird <xref:System.Windows.Media.TransformGroup> gezeigt, wie <xref:System.Windows.Media.Transform> sie zum <xref:System.Windows.Media.Transform>Gruppieren von zwei oder mehr Objekten in einem einzelnen Verbund verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.TransformGroup> wird <xref:System.Windows.Media.ScaleTransform> ein <xref:System.Windows.Media.RotateTransform> zum <xref:System.Windows.Controls.Button>Anwenden von a und a auf eine verwendet.  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [Übersicht über Transformationen](transforms-overview.md)
- [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
