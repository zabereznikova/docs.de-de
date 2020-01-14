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
ms.openlocfilehash: 621684e14f9d1b599c4ef60e3731f0f58f31aacd
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740159"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Lernprogramm: Hosten von visuellen Objekten in einer Win32-Anwendung
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie jedoch eine beträchtliche Investition in Win32-Code haben, kann es effektiver sein, der Anwendung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionalität hinzuzufügen, anstatt den Code umzuschreiben. Zur Unterstützung von Win32-und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Grafik Subsystemen, die gleichzeitig in einer Anwendung verwendet werden, stellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einen Mechanismus zum Hosting von Objekten in einem Win32-Fenster bereit.  
  
 In diesem Tutorial wird beschrieben, wie Sie eine Beispielanwendung, ein [Treffer Test mit Win32-Interoperation-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159995), erstellen, das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visuellen Objekte in einem Win32-Fenster hostet.  

<a name="requirements"></a>   
## <a name="requirements"></a>-Anforderungen  
 In diesem Tutorial wird davon ausgegangen, dass es sich um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-und Win32-Programmierung handelt. Eine grundlegende Einführung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierung finden Sie unter Exemplarische Vorgehensweise [: meine erste WPF-Desktop Anwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md). Eine Einführung in die Win32-Programmierung finden Sie in den zahlreichen Büchern zu diesem Thema, insbesondere in den *Programmier Fenstern* von Charles Petzold.  
  
> [!NOTE]
> Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Den gesamten Beispielcode finden Sie unter [Beispiel für Treffer Tests mit Win32-Interoperation](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Erstellen des Host-Win32-Fensters  
 Der Schlüssel zum Hosting von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekten in einem Win32-Fenster ist die <xref:System.Windows.Interop.HwndSource>-Klasse. Diese Klasse umschließt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Objekte in einem Win32-Fenster, sodass Sie als untergeordnetes Fenster in Ihre [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] eingebunden werden können.  
  
 Das folgende Beispiel zeigt den Code zum Erstellen des <xref:System.Windows.Interop.HwndSource> Objekts als Win32-Containerfenster für die visuellen Objekte. Verwenden Sie das <xref:System.Windows.Interop.HwndSourceParameters>-Objekt, um den Fenster Stil, die Position und andere Parameter für das Win32-Fenster festzulegen.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> Der Wert der <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A>-Eigenschaft kann nicht auf WS_EX_TRANSPARENT festgelegt werden. Dies bedeutet, dass das Win32-Host Fenster nicht transparent sein darf. Aus diesem Grund wird die Hintergrundfarbe des Win32-Fensters des Hosts auf die gleiche Hintergrundfarbe wie das übergeordnete Fenster festgelegt.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Hinzufügen von visuellen Objekten zum Host-Win32-Fenster  
 Nachdem Sie ein Win32-Host Containerfenster für die visuellen Objekte erstellt haben, können Sie visuelle Objekte hinzufügen. Sie möchten sicherstellen, dass alle Transformationen der visuellen Objekte (z. b. Animationen) nicht über die Grenzen des umgebenden Rechtecks des Host-Win32-Fensters hinausgehen.  
  
 Das folgende Beispiel zeigt den Code zum Erstellen des <xref:System.Windows.Interop.HwndSource> Objekts und zum Hinzufügen von visuellen Objekten.  
  
> [!NOTE]
> Die <xref:System.Windows.Interop.HwndSource.RootVisual%2A>-Eigenschaft des <xref:System.Windows.Interop.HwndSource>-Objekts wird auf das erste visuelle Objekt festgelegt, das zum Win32-Fenster des Hosts hinzugefügt wurde. Das visuelle Stammobjekt definiert den obersten Knoten der Struktur des visuellen Objekts. Alle nachfolgenden visuellen Objekte, die dem Windows-Host Fenster hinzugefügt werden, werden als untergeordnete Objekte hinzugefügt  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Implementieren des Win32-Nachrichtenfilters  
 Das Win32-Host Fenster für die visuellen Objekte erfordert eine Fenster Meldungs Filter Prozedur zum Verarbeiten von Nachrichten, die aus der Anwendungs Warteschlange an das Fenster gesendet werden. Die Fenster Prozedur empfängt Nachrichten vom Win32-System. Dabei kann es sich um Eingabe- oder Fensterverwaltungsmeldungen handeln. Sie können wahlweise eine Meldung in der Fensterprozedur verarbeiten oder die Meldung zwecks Standardverarbeitung an das System übergeben.  
  
 Das <xref:System.Windows.Interop.HwndSource> Objekt, das Sie als übergeordnetes Element für die visuellen Objekte definiert haben, muss auf die von Ihnen bereitgestellte Fenster Nachrichtenfilter-Prozedur verweisen. Wenn Sie das <xref:System.Windows.Interop.HwndSource> Objekt erstellen, legen Sie die <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A>-Eigenschaft so fest, dass Sie auf die Fenster Prozedur verweist.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 Das folgende Beispiel zeigt den Code für die Verarbeitung der Meldungen der linken und rechten Maustaste. Der Koordinaten Wert der Maus Treffer Position ist im Wert des `lParam`-Parameters enthalten.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Verarbeiten der Win32-Meldungen  
 Der Code im folgenden Beispiel zeigt, wie ein Treffer Test für die Hierarchie von visuellen Objekten durchgeführt wird, die im Win32-Host Fenster enthalten sind. Sie können ermitteln, ob sich ein Punkt innerhalb der Geometrie eines visuellen Objekts befindet, indem Sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>-Methode verwenden, um das visuelle Stamm Objekt und den Koordinaten Wert für den Treffer Test anzugeben. In diesem Fall ist das visuelle Stamm Objekt der Wert der <xref:System.Windows.Interop.HwndSource.RootVisual%2A>-Eigenschaft des <xref:System.Windows.Interop.HwndSource>-Objekts.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Weitere Informationen zu Treffer Tests für visuelle Objekte finden Sie unter [Treffer Tests in der visuellen Ebene](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndSource>
- [Beispiel für einen Treffer Test mit Win32-Interoperation](https://go.microsoft.com/fwlink/?LinkID=159995)
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
