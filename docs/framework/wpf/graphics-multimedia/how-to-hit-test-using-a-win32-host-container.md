---
title: 'Gewusst wie: Treffertest mithilfe eines Win32-Hostcontainers'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a5cb77a53cbb106593b70d618bab67ef816e901
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Gewusst wie: Treffertest mithilfe eines Win32-Hostcontainers
Erstellung visueller Objekte innerhalb einer [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Fenster durch Bereitstellen einer Host-Fenster Container für die visuellen Objekte. Verarbeiten Sie die Meldungen, die an die Meldungsfilterschleife des Hostcontainers übergeben werden, um für die visuellen Objekte im Container die Ereignisbehandlung bereitzustellen. Finden Sie unter [Lernprogramm: visueller Objekte in einer Win32-Anwendung hosten](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) für Weitere Informationen zum Hosten der visuellen Objekte in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie Ereignishandler für Maus Einrichten einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster, das als Hostcontainer für visuelle Objekte verwendet wird.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 Im folgende Beispiel wird gezeigt, wie ein Treffertest als Antwort auf die abgefangene Mausereignisse eingerichtet wird.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Die <xref:System.Windows.Interop.HwndSource> Objekt zeigt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalt in einem [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Fenster. Der Wert des der <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft des der <xref:System.Windows.Interop.HwndSource> Objekt stellt den oberste Knoten in der visuellen Strukturhierarchie dar.  
  
 Das vollständige Beispiel für Treffertests Objekte mit einem Win32-Host-Container, finden Sie unter [Treffertests mit Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Interop.HwndSource>  
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
