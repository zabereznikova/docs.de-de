---
title: 'Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: c8baefbf01467a65626a77f300f34a145d5c7281
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962876"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie jedoch eine beträchtliche Investition in [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] den Code haben, kann es effektiver sein, der Anwendung Funktionalität hinzuzufügen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , anstatt den Code neu zu schreiben. Um Unterstützung für [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] - [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und-Grafik Subsysteme bereitzustellen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gleichzeitig in einer Anwendung verwendet werden, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] stellt einen Mechanismus zum Hosting von Objekten in einem-Fenster  
  
 In diesem Tutorial wird beschrieben, wie Sie eine Beispielanwendung, ein [Treffer Test mit Win32-Interoperation-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159995), erstellen [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , das visuelle Objekte in einem Fenster hostet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  

<a name="requirements"></a>   
## <a name="requirements"></a>Anforderungen  
 In diesem Lernprogramm wird vorausgesetzt, dass Sie mit den Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierung und der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Programmierung vertraut sind. Eine grundlegende Einführung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Programmierung finden [Sie unter Exemplarische Vorgehensweise: Meine erste WPF-Desktop](../getting-started/walkthrough-my-first-wpf-desktop-application.md)Anwendung. Eine Einführung in die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Programmierung finden Sie in den zahlreichen Büchern zu diesem Thema, insbesondere in den *Programmier Fenstern* von Charles Petzold.  
  
> [!NOTE]
> Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Den gesamten Beispielcode finden Sie unter [Beispiel für Treffer Tests mit Win32-Interoperation](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Erstellen des Host-Win32-Fensters  
 Der Schlüssel für das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Hosting von Objekten [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] in einem- <xref:System.Windows.Interop.HwndSource> Fenster ist die-Klasse. Diese Klasse umschließt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die-Objekte [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] in einem-Fenster, sodass Sie als unter [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] geordnetes Fenster in Ihre eingebunden werden können.  
  
 Das folgende Beispiel zeigt den Code zum Erstellen des <xref:System.Windows.Interop.HwndSource> -Objekts [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] als Containerfenster für die visuellen Objekte. Verwenden Sie das <xref:System.Windows.Interop.HwndSourceParameters> -Objekt, um den Fenster Stil, die Position [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und andere Parameter für das Fenster festzulegen.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> Der Wert <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> der Eigenschaft kann nicht auf WS_EX_TRANSPARENT festgelegt werden. Dies bedeutet, dass das [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Host Fenster nicht transparent sein darf. Aus diesem Grund wird die Hintergrundfarbe des Host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fensters auf dieselbe Hintergrundfarbe wie das übergeordnete Fenster festgelegt.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Hinzufügen von visuellen Objekten zum Host-Win32-Fenster  
 Nachdem Sie ein Host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Containerfenster für die visuellen Objekte erstellt haben, können Sie visuelle Objekte hinzufügen. Sie müssen sicherstellen, dass alle Transformationen der visuellen Objekte (z. b. Animationen) nicht über die Grenzen des umgebenden Rechtecks des Host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fensters hinausgehen.  
  
 Das folgende Beispiel zeigt den Code zum Erstellen des <xref:System.Windows.Interop.HwndSource> -Objekts und zum Hinzufügen von visuellen Objekten.  
  
> [!NOTE]
> Die <xref:System.Windows.Interop.HwndSource.RootVisual%2A> -Eigenschaft <xref:System.Windows.Interop.HwndSource> des-Objekts wird auf das erste visuelle Objekt festgelegt, das [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dem Host Fenster hinzugefügt wird. Das visuelle Stammobjekt definiert den obersten Knoten der Struktur des visuellen Objekts. Alle nachfolgenden visuellen Objekte, die dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Host Fenster hinzugefügt werden, werden als untergeordnete Objekte hinzugefügt.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Implementieren des Win32-Nachrichtenfilters  
 Das Host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster für die visuellen Objekte erfordert eine Fenster Meldungs Filter Prozedur, um Meldungen zu verarbeiten, die aus der Anwendungs Warteschlange an das Fenster gesendet werden. Die Fenster Prozedur empfängt Nachrichten vom [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] System. Dabei kann es sich um Eingabe- oder Fensterverwaltungsmeldungen handeln. Sie können wahlweise eine Meldung in der Fensterprozedur verarbeiten oder die Meldung zwecks Standardverarbeitung an das System übergeben.  
  
 Das <xref:System.Windows.Interop.HwndSource> Objekt, das Sie als übergeordnetes Element für die visuellen Objekte definiert haben, muss auf die von Ihnen bereitgestellte Fenster Nachrichtenfilter-Prozedur verweisen. Wenn Sie das <xref:System.Windows.Interop.HwndSource> Objekt erstellen, legen Sie <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> die-Eigenschaft so fest, dass Sie auf die Fenster Prozedur verweist.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 Das folgende Beispiel zeigt den Code für die Verarbeitung der Meldungen der linken und rechten Maustaste. Der Koordinaten Wert der Maus Treffer Position ist im Wert des `lParam` -Parameters enthalten.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Verarbeiten der Win32-Meldungen  
 Der Code im folgenden Beispiel zeigt, wie ein Treffer Test für die Hierarchie von visuellen Objekten durchgeführt wird, die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] im Host Fenster enthalten sind. Sie können ermitteln, ob sich ein Punkt innerhalb der Geometrie eines visuellen Objekts befindet, indem Sie <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> die-Methode verwenden, um das visuelle Stamm Objekt und den Koordinaten Wert anzugeben, für den der Treffer Test durch gefunden werden soll. In diesem Fall ist das visuelle Stamm Objekt der Wert der <xref:System.Windows.Interop.HwndSource.RootVisual%2A> -Eigenschaft <xref:System.Windows.Interop.HwndSource> des-Objekts.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Weitere Informationen zu Treffer Tests für visuelle Objekte finden Sie unter [Treffer Tests in der visuellen Ebene](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndSource>
- [Beispiel für einen Treffer Test mit Win32-Interoperation](https://go.microsoft.com/fwlink/?LinkID=159995)
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
