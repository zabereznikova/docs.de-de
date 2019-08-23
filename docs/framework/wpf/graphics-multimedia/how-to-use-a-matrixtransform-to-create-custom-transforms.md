---
title: 'Vorgehensweise: Verwenden eines MatrixTransform-Objekts zum Erstellen benutzerdefinierter Transformationen'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913914"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Vorgehensweise: Verwenden eines MatrixTransform-Objekts zum Erstellen benutzerdefinierter Transformationen
Dieses Beispiel zeigt, wie Sie mit <xref:System.Windows.Media.MatrixTransform> einem die Position, die Streckung und die Schiefe <xref:System.Windows.Controls.Button>eines übersetzen (verschieben).  
  
> [!NOTE]
> Verwenden Sie <xref:System.Windows.Media.MatrixTransform> die-Klasse, um benutzerdefinierte Transformationen zu erstellen, <xref:System.Windows.Media.RotateTransform>die nicht <xref:System.Windows.Media.ScaleTransform>von den <xref:System.Windows.Media.TranslateTransform> Klassen, <xref:System.Windows.Media.SkewTransform>, oder bereitgestellt werden.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Übersicht über Transformationen](transforms-overview.md)
- [Themen zu Vorgehensweisen](transformations-how-to-topics.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
