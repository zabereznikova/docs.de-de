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
ms.openlocfilehash: bb175e0f8aeb126b7f7fa85d5af1c4afcf5bea61
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44212385"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="7bf6f-102">Gewusst wie: Treffertest mithilfe eines Win32-Hostcontainers</span><span class="sxs-lookup"><span data-stu-id="7bf6f-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="7bf6f-103">Sie können visuelle Objekte in erstellen eine [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Fenster durch Bereitstellen eines Hosts Hostcontainer für visuelle Objekte.</span><span class="sxs-lookup"><span data-stu-id="7bf6f-103">You can create visual objects within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="7bf6f-104">Verarbeiten Sie die Meldungen, die an die Meldungsfilterschleife des Hostcontainers übergeben werden, um für die visuellen Objekte im Container die Ereignisbehandlung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7bf6f-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="7bf6f-105">Finden Sie unter [Lernprogramm: Hosten von visuellen Objekten in einer Win32-Anwendung](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) für Weitere Informationen zum Hosten von visuellen Objekten in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster.</span><span class="sxs-lookup"><span data-stu-id="7bf6f-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bf6f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7bf6f-106">Example</span></span>  
 <span data-ttu-id="7bf6f-107">Der folgende Code zeigt, wie Sie Mausereignishandler für Einrichten einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster, das als Hostcontainer für visuelle Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7bf6f-107">The following code shows how to set up mouse event handlers for a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="7bf6f-108">Das folgende Beispiel zeigt, wie Sie einen Treffertest als Reaktion auf abgefangene Mausereignisse einrichten.</span><span class="sxs-lookup"><span data-stu-id="7bf6f-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="7bf6f-109">Die <xref:System.Windows.Interop.HwndSource> -Objekt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalt in einem [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Fenster.</span><span class="sxs-lookup"><span data-stu-id="7bf6f-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window.</span></span> <span data-ttu-id="7bf6f-110">Der Wert des der <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft der <xref:System.Windows.Interop.HwndSource> -Objekt stellt den obersten Knoten in der Hierarchie der visuellen Struktur dar.</span><span class="sxs-lookup"><span data-stu-id="7bf6f-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="7bf6f-111">Das vollständige Beispiel für Treffertests Objekte mithilfe eines Win32-Hostcontainers, finden Sie unter [Treffertests mit Win32-Interoperabilität](https://go.microsoft.com/fwlink/?LinkID=159995).</span><span class="sxs-lookup"><span data-stu-id="7bf6f-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf6f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bf6f-112">See Also</span></span>  
 <xref:System.Windows.Interop.HwndSource>  
 [<span data-ttu-id="7bf6f-113">Treffertests in der visuellen Ebene</span><span class="sxs-lookup"><span data-stu-id="7bf6f-113">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [<span data-ttu-id="7bf6f-114">Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung</span><span class="sxs-lookup"><span data-stu-id="7bf6f-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
