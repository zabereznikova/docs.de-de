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
ms.openlocfilehash: 544d0a26f24e5ad4ed7e2e3cfa25f8e15d1be446
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452830"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>Gewusst wie: Anwenden mehrerer Transformationen auf ein Objekt
In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.TransformGroup> verwendet wird, um zwei oder mehr <xref:System.Windows.Media.Transform> Objekte in einem einzelnen zusammengesetzten <xref:System.Windows.Media.Transform>zu gruppieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.TransformGroup> verwendet, um eine <xref:System.Windows.Media.ScaleTransform> und eine <xref:System.Windows.Media.RotateTransform> auf eine <xref:System.Windows.Controls.Button>anzuwenden.  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [Übersicht über Transformationen](transforms-overview.md)
- [Beispiel für 2D-Transformation](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
