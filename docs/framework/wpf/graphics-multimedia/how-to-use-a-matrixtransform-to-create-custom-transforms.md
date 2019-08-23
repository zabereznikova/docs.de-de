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
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="53d58-102">Vorgehensweise: Verwenden eines MatrixTransform-Objekts zum Erstellen benutzerdefinierter Transformationen</span><span class="sxs-lookup"><span data-stu-id="53d58-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="53d58-103">Dieses Beispiel zeigt, wie Sie mit <xref:System.Windows.Media.MatrixTransform> einem die Position, die Streckung und die Schiefe <xref:System.Windows.Controls.Button>eines übersetzen (verschieben).</span><span class="sxs-lookup"><span data-stu-id="53d58-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53d58-104">Verwenden Sie <xref:System.Windows.Media.MatrixTransform> die-Klasse, um benutzerdefinierte Transformationen zu erstellen, <xref:System.Windows.Media.RotateTransform>die nicht <xref:System.Windows.Media.ScaleTransform>von den <xref:System.Windows.Media.TranslateTransform> Klassen, <xref:System.Windows.Media.SkewTransform>, oder bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="53d58-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d58-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53d58-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="53d58-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53d58-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="53d58-107">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="53d58-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="53d58-108">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="53d58-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="53d58-109">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="53d58-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
