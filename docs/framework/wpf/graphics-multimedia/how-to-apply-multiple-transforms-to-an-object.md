---
title: 'Vorgehensweise: Anwenden mehrerer Transformationen auf ein Objekt'
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
ms.openlocfilehash: 26dcd4a64fc7aa2c3cb9cc599ceaef292efb1b6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192757"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>Vorgehensweise: Anwenden mehrerer Transformationen auf ein Objekt
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.TransformGroup> Gruppe zwei oder mehr <xref:System.Windows.Media.Transform> Objekte in einem einzigen zusammengesetzten <xref:System.Windows.Media.Transform>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.TransformGroup> Anwenden einer <xref:System.Windows.Media.ScaleTransform> und ein <xref:System.Windows.Media.RotateTransform> auf eine <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [Übersicht über Transformationen](transforms-overview.md)
- [Beispiel für 2D-Transformationen](https://go.microsoft.com/fwlink/?LinkID=158252)
