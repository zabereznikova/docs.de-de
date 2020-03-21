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
ms.openlocfilehash: d04357e0770bbf8eebe8f40a86a19ddc9baae3ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187425"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Lernprogramm: Hosten von visuellen Objekten in einer Win32-Anwendung
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie jedoch erheblich in Win32-Code investieren, ist [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es möglicherweise effektiver, Der Anwendung Funktionen hinzuzufügen, anstatt den Code neu zu schreiben. Um Unterstützung für Win32- und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Grafiksubsysteme bereitzustellen, die gleichzeitig in einer Anwendung verwendet werden, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet ein Mechanismus zum Hosten von Objekten in einem Win32-Fenster.  
  
 In diesem Tutorial wird beschrieben, wie Sie eine Beispielanwendung schreiben, [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting), die visuelle Objekte in einem Win32-Fenster hostet. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  

<a name="requirements"></a>
## <a name="requirements"></a>Requirements (Anforderungen)  
 In diesem Tutorial wird eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] grundlegende Vertrautheit mit der Win32-Programmierung vorausgesetzt. Eine grundlegende Einführung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in die Programmierung finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md). Eine Einführung in die Win32-Programmierung finden Sie in einem der zahlreichen Bücher zu diesem Thema, insbesondere *Programming Windows* von Charles Petzold.  
  
> [!NOTE]
> Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Den vollständigen Beispielcode finden Sie unter [Hittest mit Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).  
  
<a name="creating_the_host_win32_window"></a>
## <a name="creating-the-host-win32-window"></a>Erstellen des Host-Win32-Fensters  
 Der Schlüssel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zum Hosten von Objekten <xref:System.Windows.Interop.HwndSource> in einem Win32-Fenster ist die Klasse. Diese Klasse umschließt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekte in einem Win32-Fenster, sodass sie als untergeordnetes Fenster in Sie [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] integriert werden können.  
  
 Das folgende Beispiel zeigt den <xref:System.Windows.Interop.HwndSource> Code zum Erstellen des Objekts als Win32-Containerfenster für die visuellen Objekte. Verwenden Sie das <xref:System.Windows.Interop.HwndSourceParameters> Objekt, um den Fensterstil, die Position und andere Parameter für das Win32-Fenster festzulegen.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> Der Wert <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> der Eigenschaft kann nicht auf WS_EX_TRANSPARENT festgelegt werden. Dies bedeutet, dass das Host-Win32-Fenster nicht transparent sein kann. Aus diesem Grund wird die Hintergrundfarbe des Host-Win32-Fensters auf die gleiche Hintergrundfarbe wie das übergeordnete Fenster festgelegt.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Hinzufügen von visuellen Objekten zum Host-Win32-Fenster  
 Nachdem Sie ein Host-Win32-Containerfenster für die visuellen Objekte erstellt haben, können Sie ihm visuelle Objekte hinzufügen. Sie sollten sicherstellen, dass alle Transformationen der visuellen Objekte, z. B. Animationen, nicht über die Grenzen des umgrenzenden Rechtecks des Host-Win32-Fensters hinausgehen.  
  
 Das folgende Beispiel zeigt den <xref:System.Windows.Interop.HwndSource> Code zum Erstellen des Objekts und Hinzufügen visueller Objekte.  
  
> [!NOTE]
> Die <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft <xref:System.Windows.Interop.HwndSource> des Objekts wird auf das erste visuelle Objekt festgelegt, das dem Win32-Hostfenster hinzugefügt wurde. Das visuelle Stammobjekt definiert den obersten Knoten der Struktur des visuellen Objekts. Alle nachfolgenden visuellen Objekte, die dem Win32-Hostfenster hinzugefügt werden, werden als untergeordnete Objekte hinzugefügt.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>
## <a name="implementing-the-win32-message-filter"></a>Implementieren des Win32-Nachrichtenfilters  
 Das Host-Win32-Fenster für die visuellen Objekte erfordert eine Fensternachrichtenfilterprozedur, um Nachrichten zu verarbeiten, die aus der Anwendungswarteschlange an das Fenster gesendet werden. Die Fensterprozedur empfängt Nachrichten vom Win32-System. Dabei kann es sich um Eingabe- oder Fensterverwaltungsmeldungen handeln. Sie können wahlweise eine Meldung in der Fensterprozedur verarbeiten oder die Meldung zwecks Standardverarbeitung an das System übergeben.  
  
 Das <xref:System.Windows.Interop.HwndSource> Objekt, das Sie als übergeordnetes Objekt für die visuellen Objekte definiert haben, muss auf die von Ihnen vorgesehene Fensternachrichtenfilterprozedur verweisen. Wenn Sie <xref:System.Windows.Interop.HwndSource> das Objekt <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> erstellen, legen Sie die Eigenschaft so fest, dass sie auf die Fensterprozedur verweist.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 Das folgende Beispiel zeigt den Code für die Verarbeitung der Meldungen der linken und rechten Maustaste. Der Koordinatenwert der Maustrefferposition ist im `lParam` Wert des Parameters enthalten.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>
## <a name="processing-the-win32-messages"></a>Verarbeiten der Win32-Meldungen  
 Der Code im folgenden Beispiel zeigt, wie ein Treffertest für die Hierarchie visueller Objekte im Win32-Hostfenster durchgeführt wird. Sie können ermitteln, ob sich ein Punkt innerhalb der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Geometrie eines visuellen Objekts befindet, indem Sie die Methode verwenden, um das visuelle Stammobjekt und den Koordinatenwert anzugeben, für den der Test ausgeführt werden soll. In diesem Fall ist das visuelle Stammobjekt der Wert der <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft des <xref:System.Windows.Interop.HwndSource> Objekts.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Weitere Informationen zu Treffertests für visuelle Objekte finden Sie unter [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Interop.HwndSource>
- [Beispiel für Treffertests mit Win32-Interoperabilität](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
