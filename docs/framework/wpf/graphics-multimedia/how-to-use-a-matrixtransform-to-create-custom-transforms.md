---
title: 'Vorgehensweise: Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 179c7986b6a7021f4e1245aef01eb555108ebf4f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358859"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="58b0a-102">Vorgehensweise: Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen</span><span class="sxs-lookup"><span data-stu-id="58b0a-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="58b0a-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.MatrixTransform> übersetzt (verschoben) die Position, Strecken und Zerren von einem <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="58b0a-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58b0a-104">Verwenden der <xref:System.Windows.Media.MatrixTransform> Klasse benutzerdefinierte Transformationen erstellen, die nicht verfügbar sind die <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, oder <xref:System.Windows.Media.TranslateTransform> Klassen.</span><span class="sxs-lookup"><span data-stu-id="58b0a-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58b0a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58b0a-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="58b0a-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58b0a-106">See also</span></span>
- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="58b0a-107">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="58b0a-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="58b0a-108">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="58b0a-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="58b0a-109">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="58b0a-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
