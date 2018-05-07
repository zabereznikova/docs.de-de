---
title: 'Lernprogramm: Hosten von visuellen Objekten in einer Win32-Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: cc78dfd22b0ad2726ce8870a4e03f539ec691d85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Lernprogramm: Hosten von visuellen Objekten in einer Win32-Anwendung
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie haben jedoch eine erhebliche Investition [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Code, ist es möglicherweise effektiver hinzufügen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionalität der Anwendung statt den Code umschreiben. Zur Unterstützung von [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Graphics-Subsysteme, die gleichzeitig in einer Anwendung verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet einen Mechanismus zum Hosten von Objekten in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster.  
  
 In diesem Lernprogramm wird beschrieben, wie eine beispielanwendung schreiben [Treffertests mit Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995), die Hosts [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visuelle Objekte einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster.  
  

  
<a name="requirements"></a>   
## <a name="requirements"></a>Anforderungen  
 In diesem Lernprogramm wird vorausgesetzt, dass Sie mit den Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierung und der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Programmierung vertraut sind. Eine grundlegende Einführung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Programmierung, finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md). Eine Einführung in die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Programmierung, finden Sie in der zahlreiche Bücher zu diesem Thema, insbesondere *Windows-Programmierung* von Charles Petzold.  
  
> [!NOTE]
>  Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Den vollständigen Beispielcode finden Sie unter [Treffertests mit Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Erstellen des Host-Win32-Fensters  
 Der Schlüssel zum Hosten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekte in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster ist die <xref:System.Windows.Interop.HwndSource> Klasse. Diese Klasse dient als Wrapper für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekte in einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster, sodass sie integriert werden soll Ihre [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] als untergeordnetes Fenster.  
  
 Das folgende Beispiel zeigt den Code zum Erstellen der <xref:System.Windows.Interop.HwndSource> -Objekts entsprechend der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Containerfenster für visuelle Objekte. Der Fensterstil, Position und andere Parameter für die festzulegende der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster verwenden die <xref:System.Windows.Interop.HwndSourceParameters> Objekt.  
  
 [!code-csharp[VisualsHitTesting#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  Der Wert, der die <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> Eigenschaft kann nicht auf WS_EX_TRANSPARENT festgelegt werden. Dies bedeutet, dass den Host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster nicht transparent sein. Aus diesem Grund die Farbe des Hintergrunds des Hosts [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster auf die gleiche Hintergrundfarbe wie das übergeordnete Fenster festgelegt ist.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Hinzufügen von visuellen Objekten zum Host-Win32-Fenster  
 Nach der Erstellung eines Hosts [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Containerfenster für die visuellen Objekte können Sie visuelle Objekte darauf hinzufügen. Stellen Sie sicher, dass Transformationen der visuellen Objekte, z. B. Animationen, nicht außerhalb des zulässigen Bereichs des Hosts erweitern sollen [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster des umschließenden Rechtecks.  
  
 Das folgende Beispiel zeigt den Code zum Erstellen der <xref:System.Windows.Interop.HwndSource> -Objekt und visuelle Objekte hinzugefügt.  
  
> [!NOTE]
>  Die <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft von der <xref:System.Windows.Interop.HwndSource> Objektsatz zum ersten visual-Objekt an den Host hinzugefügt [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster. Das visuelle Stammobjekt definiert den obersten Knoten der Struktur des visuellen Objekts. Alle weiteren visuellen Objekte, die an den Host hinzugefügt [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster werden als untergeordnete Objekte hinzugefügt.  
  
 [!code-csharp[VisualsHitTesting#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Implementieren des Win32-Nachrichtenfilters  
 Der Host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster für die visuellen Objekte erfordert eine Fensterprozedur für die Filter von Nachrichten zum Verarbeiten von Nachrichten, die aus der Anwendungswarteschlange an das Fenster gesendet werden. Die Fensterprozedur empfängt Nachrichten aus der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] System. Dabei kann es sich um Eingabe- oder Fensterverwaltungsmeldungen handeln. Sie können wahlweise eine Meldung in der Fensterprozedur verarbeiten oder die Meldung zwecks Standardverarbeitung an das System übergeben.  
  
 Die <xref:System.Windows.Interop.HwndSource> -Objekt, das Sie definiert, wie das übergeordnete Element für die visuellen Objekte Fenster Nachrichtenfilterprozedur verweisen müssen Sie angeben. Beim Erstellen der <xref:System.Windows.Interop.HwndSource> Objekt, das Festlegen der <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> Eigenschaft, um die Fensterprozedur verweisen.  
  
 [!code-csharp[VisualsHitTesting#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 Das folgende Beispiel zeigt den Code für die Verarbeitung der Meldungen der linken und rechten Maustaste. Der Koordinatenwert der Maus erreicht Position ist der Wert der Bestandteil der `lParam` Parameter.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Verarbeiten der Win32-Meldungen  
 Der Code im folgenden Beispiel wird gezeigt, wie ein Treffertest ausgeführt wird, für die Hierarchie der visuellen Objekte enthalten sind, auf dem Host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster. Sie können ermitteln, ob sich ein Punkt innerhalb der Geometrie des visuellen Objekts, mit der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode, um das visuelle Stammobjekt und der Koordinatenwert Treffertest für anzugeben. In diesem Fall wird das Stamm-visual-Objekt den Wert des der <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft von der <xref:System.Windows.Interop.HwndSource> Objekt.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Weitere Informationen über Treffertests für visuelle Objekte finden Sie unter [erreicht Testen in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Interop.HwndSource>  
 [Treffertests mit Interoperation Win32-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159995)  
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
