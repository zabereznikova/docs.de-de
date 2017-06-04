---
title: "Gewusst wie: Treffertest mithilfe eines Win32-Hostcontainers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Treffertests, Verwenden von Win32-Hostcontainern"
  - "Visuelle Objekte, Treffertests für"
  - "Win32-Hostcontainer, Treffertests mit"
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Treffertest mithilfe eines Win32-Hostcontainers
Sie können visuelle Objekte in einem [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-Fenster erstellen, indem Sie für die visuellen Objekte einen Hostcontainer in Fensterform bereitstellen.  Um für die visuellen Objekte im Container die Ereignisbehandlung bereitzustellen, verarbeiten Sie die Meldungen, die an die Meldungsfilterschleife des Hostcontainers übergeben werden.  Weitere Informationen dazu, wie Sie visuelle Objekte in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster hosten, finden Sie unter [Lernprogramm: Hosten von visuellen Objekten in einer Win32\-Anwendung](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md).  
  
## Beispiel  
 Der folgende Code zeigt, wie Sie Mausereignishandler für ein [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster einrichten, das als Hostcontainer für visuelle Objekte verwendet wird.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 Das folgende Beispiel zeigt, wie Sie einen [Treffertest](GTMT) als Reaktion auf abgefangene Mausereignisse einrichten.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Das <xref:System.Windows.Interop.HwndSource>\-Objekt stellt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Inhalt in einem [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-Fenster dar. Der Wert der <xref:System.Windows.Interop.HwndSource.RootVisual%2A>\-Eigenschaft des <xref:System.Windows.Interop.HwndSource>\-Objekts stellt den obersten Knoten in der Hierarchie der [visuellen Struktur](GTMT) dar.  
  
 Das vollständige Beispiel zum Durchführen von Treffertests für Objekte mithilfe eines Win32\-Hostcontainers finden Sie unter [Beispiel für Treffertests mit Win32\-Interoperabilität](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
## Siehe auch  
 <xref:System.Windows.Interop.HwndSource>   
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Lernprogramm: Hosten von visuellen Objekten in einer Win32\-Anwendung](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)