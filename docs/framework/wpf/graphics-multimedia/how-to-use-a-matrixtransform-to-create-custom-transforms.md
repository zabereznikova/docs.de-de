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
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="0c275-102">Vorgehensweise: Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen</span><span class="sxs-lookup"><span data-stu-id="0c275-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="0c275-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.MatrixTransform> übersetzt (verschoben) die Position, Strecken und Zerren von einem <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="0c275-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c275-104">Verwenden der <xref:System.Windows.Media.MatrixTransform> Klasse benutzerdefinierte Transformationen erstellen, die nicht verfügbar sind die <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, oder <xref:System.Windows.Media.TranslateTransform> Klassen.</span><span class="sxs-lookup"><span data-stu-id="0c275-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c275-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c275-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="0c275-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c275-106">See also</span></span>
- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="0c275-107">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="0c275-107">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [<span data-ttu-id="0c275-108">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0c275-108">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
- [<span data-ttu-id="0c275-109">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="0c275-109">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
