---
title: 'Gewusst wie: Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4995c5d712807e91b27c7afacd6f5b7015cb5898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Gewusst wie: Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.MatrixTransform> übersetzt (verschoben) der Position Strecken und Zerren von einem <xref:System.Windows.Controls.Button>.  
  
> [!NOTE]
>  Verwenden der <xref:System.Windows.Media.MatrixTransform> Klasse, um benutzerdefinierte Transformationen erstellen, die nicht enthalten sind die <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, oder <xref:System.Windows.Media.TranslateTransform> Klassen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.MatrixTransform>  
 <xref:System.Windows.Media.Transform>  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
