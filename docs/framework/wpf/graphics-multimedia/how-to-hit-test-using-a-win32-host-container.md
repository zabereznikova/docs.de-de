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
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Gewusst wie: Treffertest mithilfe eines Win32-Hostcontainers
Sie können visuelle Objekte in einem Win32-Fenster erstellen, indem Sie einen Host Fenster Container für die visuellen Objekte bereitstellen. Verarbeiten Sie die Meldungen, die an die Meldungsfilterschleife des Hostcontainers übergeben werden, um für die visuellen Objekte im Container die Ereignisbehandlung bereitzustellen. Weitere Informationen zum Hosten von visuellen Objekten in einem Win32-Fenster finden Sie unter [Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung](tutorial-hosting-visual-objects-in-a-win32-application.md) .  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie Maus Ereignishandler für ein Win32-Fenster einrichten, das als Host Container für visuelle Objekte verwendet wird.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 Das folgende Beispiel zeigt, wie Sie einen Treffer Test als Reaktion auf das Abfangen bestimmter Mausereignisse einrichten.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Das <xref:System.Windows.Interop.HwndSource>-Objekt stellt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalt in einem Win32-Fenster dar. Der Wert der <xref:System.Windows.Interop.HwndSource.RootVisual%2A>-Eigenschaft des <xref:System.Windows.Interop.HwndSource>-Objekts stellt den obersten Knoten in der visuellen Struktur Hierarchie dar.  
  
 Das komplette Beispiel für Treffer Testobjekte mithilfe eines Win32-Host Containers finden Sie unter [Beispiel für Treffer Tests mit Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)-Interoperabilität.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndSource>
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
- [Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung](tutorial-hosting-visual-objects-in-a-win32-application.md)
