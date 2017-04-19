---
title: "Lernprogramm: Hosten von visuellen Objekten in einer Win32-Anwendung | Microsoft Docs"
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
  - "Hosting, Visuelle Objekte in Win32-Code"
  - "Visuelle Objekte in Win32-Code"
  - "Win32-Code, Visuelle Objekte in"
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Lernprogramm: Hosten von visuellen Objekten in einer Win32-Anwendung
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit.  Wenn Sie allerdings bereits erhebliche Arbeit in das Schreiben von [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-Code investiert haben, kann es effektiver sein, eine vorhandene Anwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu erweitern, anstatt sie neu zu schreiben.  Zur Unterstützung von [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\- und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Grafiksubsystemen, die gleichzeitig in einer Anwendung verwendet werden, stellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einen Mechanismus zum Hosten von Objekten in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster bereit.  
  
 In diesem Lernprogramm wird beschrieben, wie eine Beispielanwendung geschrieben wird \([Beispiel für Treffertests mit Win32\-Interoperabilität](http://go.microsoft.com/fwlink/?LinkID=159995)\), die visuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Objekte in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster hostet.  
  
   
  
<a name="requirements"></a>   
## Anforderungen  
 In diesem Lernprogramm wird davon ausgegangen, dass Sie mit den Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Programmierung und [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Programmierung vertraut sind.  Eine Einführung in die Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Programmierung finden Sie unter [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  Eine Einführung in die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Programmierung finden Sie in zahlreichen Büchern zu diesem Thema, insbesondere in *Windows\-Programmierung* von Charles Petzold.  
  
> [!NOTE]
>  Dieses Lernprogramm schließt eine Reihe von Codebeispielen aus dem genannten Beispiel ein.  Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt.  Den vollständige Beispielcode finden Sie unter [Beispiel für Treffertests mit Win32\-Interoperabilität](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## Erstellen des Host\-Win32\-Fensters  
 Der Schlüssel zum Hosten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Objekten in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster ist die <xref:System.Windows.Interop.HwndSource>\-Klasse.  Diese Klasse umschließt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Objekte mit einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster, sodass sie als untergeordnetes Fenster in Ihre [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] eingebunden werden können.  
  
 Das folgende Beispiel zeigt den Code zum Erstellen des <xref:System.Windows.Interop.HwndSource>\-Objekts als [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Containerfenster für die visuellen Objekte.  Verwenden Sie zum Festlegen des Fensterstils, der Position und anderer Parameter für das [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster das <xref:System.Windows.Interop.HwndSourceParameters>\-Objekt.  
  
 [!code-csharp[VisualsHitTesting#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  Der Wert der <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A>\-Eigenschaft kann nicht auf WS\_EX\_TRANSPARENT festgelegt werden.  Dies bedeutet, dass das Host\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster nicht transparent sein kann.  Aus diesem Grund wird als Hintergrundfarbe für das Host\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster die gleiche Hintergrundfarbe wie für das übergeordnete Fenster festgelegt.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## Hinzufügen von visuellen Objekten zum Host\-Win32\-Fenster  
 Nachdem Sie ein Host\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Containerfenster für die visuellen Objekte erstellt haben, können Sie ihm visuelle Objekte hinzufügen.  Sie müssen sicherstellen, dass Transformationen der visuellen Objekte, wie zum Beispiel Animationen, nicht über das Begrenzungsrechteck des Host\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fensters hinausgehen.  
  
 Das folgende Beispiel zeigt den Code zum Erstellen des <xref:System.Windows.Interop.HwndSource>\-Objekts und zum Hinzufügen von visuellen Objekten.  
  
> [!NOTE]
>  Die <xref:System.Windows.Interop.HwndSource.RootVisual%2A>\-Eigenschaft des <xref:System.Windows.Interop.HwndSource>\-Objekts wird auf das erste visuelle Objekt festgelegt, das zum Host\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster hinzugefügt wird.  Das visuelle Stammobjekt definiert den obersten Knoten der visuellen Objektstruktur.  Alle weiteren visuellen Objekte, die dem Host\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster hinzugefügt werden, werden als untergeordnete Objekte hinzugefügt.  
  
 [!code-csharp[VisualsHitTesting#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## Implementieren des Win32\-Nachrichtenfilters  
 Das Host\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster für visuelle Objekte erfordert eine Fenster\-Nachrichtenfilterprozedur, um Nachrichten behandeln zu können, die von einer Anwendungswarteschlange an das Fenster gesendet werden.  Die Fensterprozedur empfängt Nachrichten vom [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-System.  Hierbei kann es sich um Eingabenachrichten oder Nachrichten zur Fensterverwaltung handeln.  Sie können optional eine Nachricht in der Fensterprozedur behandeln oder die Nachricht zur Standardverarbeitung an das System übergeben.  
  
 Das für visuelle Objekte als übergeordnetes Objekt definierte <xref:System.Windows.Interop.HwndSource>\-Objekt muss auf die Fenster\-Nachrichtenfilterprozedur, die Sie bereitstellen, verweisen.  Legen Sie beim Erstellen des <xref:System.Windows.Interop.HwndSource>\-Objekts die <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A>\-Eigenschaft so fest, dass sie auf die Fensterprozedur verweist.  
  
 [!code-csharp[VisualsHitTesting#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 Im folgenden Beispiel wird der Code zum Behandeln der Nachrichten für die linke und rechte Maustaste veranschaulicht.  Der Koordinatenwert der Maustrefferposition ist im Wert des `lParam`\-Parameters enthalten.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## Verarbeiten der Win32\-Nachrichten  
 Der Code im folgenden Beispiel veranschaulicht, wie ein Treffertest für die Hierarchie der visuellen Objekte, die im Host\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster enthalten sind, durchgeführt wird.  Sie können ermitteln, ob sich ein Punkt in der Geometrie eines visuellen Objekts befindet, indem Sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>\-Methode verwenden, um das visuelle Stammobjekt und den Koordinatenwert für den Treffertest anzugeben.  In diesem Fall ist das visuelle Stammobjekt der Wert der <xref:System.Windows.Interop.HwndSource.RootVisual%2A>\-Eigenschaft des <xref:System.Windows.Interop.HwndSource>\-Objekts.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Weitere Informationen über Treffertests für visuelle Objekte finden Sie unter [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
## Siehe auch  
 <xref:System.Windows.Interop.HwndSource>   
 [Beispiel für Treffertests mit Win32\-Interoperabilität](http://go.microsoft.com/fwlink/?LinkID=159995)   
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)