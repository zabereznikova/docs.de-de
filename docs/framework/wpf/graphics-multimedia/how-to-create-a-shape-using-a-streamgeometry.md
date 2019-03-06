---
title: 'Vorgehensweise: Erstellen eines Shapes mit einer StreamGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: 3273b6f45c367afeb8e572d0f68e6774075890c9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361017"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="adbc7-102">Vorgehensweise: Erstellen eines Shapes mit einer StreamGeometry</span><span class="sxs-lookup"><span data-stu-id="adbc7-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="adbc7-103"><xref:System.Windows.Media.StreamGeometry> stellt einfache Alternative zu <xref:System.Windows.Media.PathGeometry> zum Erstellen geometrischer Formen.</span><span class="sxs-lookup"><span data-stu-id="adbc7-103"><xref:System.Windows.Media.StreamGeometry> is light-weight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="adbc7-104">Verwenden einer <xref:System.Windows.Media.StreamGeometry> Wenn Sie eine komplexe Geometrie beschreiben müssen jedoch nicht den Mehraufwand für die Unterstützung von Datenbindung, Animation oder Änderung möchten.</span><span class="sxs-lookup"><span data-stu-id="adbc7-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="adbc7-105">Beispielsweise aufgrund ihrer Effizienz der <xref:System.Windows.Media.StreamGeometry> Klasse ist eine gute Wahl zum Beschreiben von Adornern.</span><span class="sxs-lookup"><span data-stu-id="adbc7-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adbc7-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="adbc7-106">Example</span></span>  
 <span data-ttu-id="adbc7-107">Im folgenden Beispiel wird eine Attributsyntax eine dreieckige erstellen <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adbc7-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="adbc7-108">Weitere Informationen zu <xref:System.Windows.Media.StreamGeometry> Attributsyntax, finden Sie unter den [Pfadmarkupsyntax](path-markup-syntax.md) Seite.</span><span class="sxs-lookup"><span data-stu-id="adbc7-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adbc7-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="adbc7-109">Example</span></span>  
 <span data-ttu-id="adbc7-110">Im nächsten Beispiel wird eine <xref:System.Windows.Media.StreamGeometry> ein Dreieck im Code definiert.</span><span class="sxs-lookup"><span data-stu-id="adbc7-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="adbc7-111">Zunächst das Beispiel erstellt eine <xref:System.Windows.Media.StreamGeometry>, erhält dann eine <xref:System.Windows.Media.StreamGeometryContext> und wird verwendet, um das Dreieck zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="adbc7-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="adbc7-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="adbc7-112">Example</span></span>  
 <span data-ttu-id="adbc7-113">Im nächste Beispiel erstellt eine Methode, verwendet eine <xref:System.Windows.Media.StreamGeometry> und <xref:System.Windows.Media.StreamGeometryContext> eine geometrische Form, die basierend auf den angegebenen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="adbc7-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="adbc7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adbc7-114">See also</span></span>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [<span data-ttu-id="adbc7-115">Erstellen einer Form mithilfe von PathGeometry</span><span class="sxs-lookup"><span data-stu-id="adbc7-115">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
- [<span data-ttu-id="adbc7-116">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="adbc7-116">Geometry Overview</span></span>](geometry-overview.md)
