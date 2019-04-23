---
title: 'Vorgehensweise: Verwenden eines MatrixTransform-Objekts zum Erstellen benutzerdefinierter Transformationen'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: aeccb961db539d4cc6dea75fb487fba06e59d6de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182311"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Vorgehensweise: Verwenden eines MatrixTransform-Objekts zum Erstellen benutzerdefinierter Transformationen
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.MatrixTransform> übersetzt (verschoben) die Position, Strecken und Zerren von einem <xref:System.Windows.Controls.Button>.  
  
> [!NOTE]
>  Verwenden der <xref:System.Windows.Media.MatrixTransform> Klasse benutzerdefinierte Transformationen erstellen, die nicht verfügbar sind die <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, oder <xref:System.Windows.Media.TranslateTransform> Klassen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Übersicht über Transformationen](transforms-overview.md)
- [Themen zu Vorgehensweisen](transformations-how-to-topics.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
