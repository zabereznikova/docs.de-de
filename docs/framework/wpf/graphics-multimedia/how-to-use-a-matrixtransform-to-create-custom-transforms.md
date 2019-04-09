---
title: 'Vorgehensweise: Verwenden eines MatrixTransform-Objekts zum Erstellen benutzerdefinierter Transformationen'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: aeccb961db539d4cc6dea75fb487fba06e59d6de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182311"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="273fd-102">Vorgehensweise: Verwenden eines MatrixTransform-Objekts zum Erstellen benutzerdefinierter Transformationen</span><span class="sxs-lookup"><span data-stu-id="273fd-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="273fd-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.MatrixTransform> übersetzt (verschoben) die Position, Strecken und Zerren von einem <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="273fd-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="273fd-104">Verwenden der <xref:System.Windows.Media.MatrixTransform> Klasse benutzerdefinierte Transformationen erstellen, die nicht verfügbar sind die <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, oder <xref:System.Windows.Media.TranslateTransform> Klassen.</span><span class="sxs-lookup"><span data-stu-id="273fd-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="273fd-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="273fd-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="273fd-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="273fd-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="273fd-107">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="273fd-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="273fd-108">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="273fd-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="273fd-109">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="273fd-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
