---
title: 'Gewusst wie: Treffertest mithilfe eines Win32-Hostcontainers'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: a86c1c36f75fa232d52731959371268a8b2593d7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452804"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="185d3-102">Gewusst wie: Treffertest mithilfe eines Win32-Hostcontainers</span><span class="sxs-lookup"><span data-stu-id="185d3-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="185d3-103">Sie können visuelle Objekte in einem Win32-Fenster erstellen, indem Sie einen Host Fenster Container für die visuellen Objekte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="185d3-103">You can create visual objects within a Win32 window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="185d3-104">Verarbeiten Sie die Meldungen, die an die Meldungsfilterschleife des Hostcontainers übergeben werden, um für die visuellen Objekte im Container die Ereignisbehandlung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="185d3-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="185d3-105">Weitere Informationen zum Hosten von visuellen Objekten in einem Win32-Fenster finden Sie unter [Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung](tutorial-hosting-visual-objects-in-a-win32-application.md) .</span><span class="sxs-lookup"><span data-stu-id="185d3-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a Win32 window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="185d3-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="185d3-106">Example</span></span>  
 <span data-ttu-id="185d3-107">Der folgende Code zeigt, wie Sie Maus Ereignishandler für ein Win32-Fenster einrichten, das als Host Container für visuelle Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="185d3-107">The following code shows how to set up mouse event handlers for a Win32 window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="185d3-108">Das folgende Beispiel zeigt, wie Sie einen Treffer Test als Reaktion auf das Abfangen bestimmter Mausereignisse einrichten.</span><span class="sxs-lookup"><span data-stu-id="185d3-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="185d3-109">Das <xref:System.Windows.Interop.HwndSource>-Objekt stellt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalt in einem Win32-Fenster dar.</span><span class="sxs-lookup"><span data-stu-id="185d3-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a Win32 window.</span></span> <span data-ttu-id="185d3-110">Der Wert der <xref:System.Windows.Interop.HwndSource.RootVisual%2A>-Eigenschaft des <xref:System.Windows.Interop.HwndSource>-Objekts stellt den obersten Knoten in der visuellen Struktur Hierarchie dar.</span><span class="sxs-lookup"><span data-stu-id="185d3-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="185d3-111">Das komplette Beispiel für Treffer Testobjekte mithilfe eines Win32-Host Containers finden Sie unter [Beispiel für Treffer Tests mit Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)-Interoperabilität.</span><span class="sxs-lookup"><span data-stu-id="185d3-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="185d3-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="185d3-112">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="185d3-113">Treffertests in der visuellen Ebene</span><span class="sxs-lookup"><span data-stu-id="185d3-113">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="185d3-114">Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung</span><span class="sxs-lookup"><span data-stu-id="185d3-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](tutorial-hosting-visual-objects-in-a-win32-application.md)
