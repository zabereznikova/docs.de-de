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
ms.openlocfilehash: b71783f2d061c9139de4449d8e0106eb00345894
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740174"
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
  
 Das komplette Beispiel für Treffer Testobjekte mithilfe eines Win32-Host Containers finden Sie unter [Beispiel für Treffer Tests mit Win32](https://go.microsoft.com/fwlink/?LinkID=159995)-Interoperabilität.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndSource>
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
- [Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung](tutorial-hosting-visual-objects-in-a-win32-application.md)
