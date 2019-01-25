---
title: 'Vorgehensweise: Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 3b5a6fbedd30c859dffadad00c8faab74fc0773b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628798"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Vorgehensweise: Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.MatrixTransform> übersetzt (verschoben) die Position, Strecken und Zerren von einem <xref:System.Windows.Controls.Button>.  
  
> [!NOTE]
>  Verwenden der <xref:System.Windows.Media.MatrixTransform> Klasse benutzerdefinierte Transformationen erstellen, die nicht verfügbar sind die <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, oder <xref:System.Windows.Media.TranslateTransform> Klassen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
