---
title: 'Vorgehensweise: Rendern in Pro-Frame-Intervallen mit CompositionTarget'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CompositionTarget objects [WPF], rendering per frame
- rendering per frame using CompositionTarget objects [WPF]
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
ms.openlocfilehash: 8864204ccdd1e860cc910dfe8baa2f25edfb2fcc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956985"
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>Vorgehensweise: Rendern in Pro-Frame-Intervallen mit CompositionTarget
Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animations-Engine stellt zahlreiche Funktionen zum Erstellen framebasierter Animationen bereit. In manchen Anwendungsszenarios müssen Sie das Rendering jedoch pro Frame detaillierter steuern können. Das <xref:System.Windows.Media.CompositionTarget> -Objekt bietet die Möglichkeit, benutzerdefinierte Animationen basierend auf einem pro-Frame-Rückruf zu erstellen.  
  
 <xref:System.Windows.Media.CompositionTarget>ist eine statische Klasse, die die Anzeige Oberfläche darstellt, auf der die Anwendung gezeichnet wird. Das <xref:System.Windows.Media.CompositionTarget.Rendering> -Ereignis wird jedes Mal ausgelöst, wenn die Szene der Anwendung gezeichnet wird. Die Renderingbildfrequenz gibt an, wie häufig die Szene pro Sekunde gezeichnet wird.  
  
> [!NOTE]
> Ein umfassendes Codebeispiel mit finden <xref:System.Windows.Media.CompositionTarget>Sie unter [Verwenden des CompositionTarget](https://go.microsoft.com/fwlink/?LinkID=160045)-Beispiels.  
  
## <a name="example"></a>Beispiel  
 Das <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis wird während des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Renderingprozesses ausgelöst. Im folgenden Beispiel wird gezeigt, wie Sie <xref:System.EventHandler> einen-Delegaten <xref:System.Windows.Media.CompositionTarget.Rendering> bei der <xref:System.Windows.Media.CompositionTarget>statischen Methode für registrieren.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Mit der Rendering-Ereignishandlermethode können Sie benutzerdefinierten Zeichnungsinhalt erstellen. Diese Ereignishandlermethode wird einmal pro Frame aufgerufen. Immer, wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der visuellen Struktur für die Szenengrafik der Komposition marshallt, wird die Ereignishandlermethode aufgerufen. Zudem wird die Ereignishandlermethode aufgerufen, wenn durch Änderungen an der visuellen Struktur Aktualisierungen der Szenengrafik erzwungen werden. Beachten Sie, dass die Ereignishandlermethode aufgerufen wird, nachdem das Layout berechnet wurde. Sie können das Layout jedoch in der Ereignishandlermethode ändern. In diesem Fall wird das Layout vor dem Rendern erneut berechnet.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie eine benutzerdefinierte Zeichnung <xref:System.Windows.Media.CompositionTarget> in einer Ereignishandlermethode bereitstellen können. In diesem Fall <xref:System.Windows.Controls.Canvas> wird die Hintergrundfarbe des mit einem Farbwert gezeichnet, der auf der Koordinaten Position der Maus basiert. Wenn Sie die Maus in den <xref:System.Windows.Controls.Canvas>bewegen, ändert sich die Hintergrundfarbe. Darüber hinaus wird die durchschnittliche Bildfrequenz auf Basis der verstrichenen Zeit und der Gesamtanzahl gerenderter Frames berechnet.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Möglicherweise stellen Sie fest, dass die benutzerdefinierte Zeichnung auf verschiedenen Computern mit unterschiedlicher Geschwindigkeit ausgeführt wird. Das liegt daran, dass die benutzerdefinierte Zeichnung von der Bildfrequenz abhängt. Abhängig vom System, das Sie ausführen, und von der Arbeitsauslastung dieses Systems <xref:System.Windows.Media.CompositionTarget.Rendering> wird das Ereignis möglicherweise unterschiedlich oft pro Sekunde aufgerufen. Informationen zur Ermittlung der Grafikleistung eines Geräts, auf dem eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung ausgeführt wird, finden Sie unter [Renderingebenen für Grafiken](../advanced/graphics-rendering-tiers.md).  
  
 Das Hinzufügen oder entfernen <xref:System.EventHandler> eines renderdelegaten, während das Ereignis ausgelöst wird, wird verzögert, bis das Ereignis abgeschlossen ist. Dies ist konsistent mit der <xref:System.MulticastDelegate>Behandlung von-basierten Ereignissen in der Common Language Runtime (CLR). Beachten Sie außerdem, dass die Reihenfolge, in der die Renderingereignisse aufgerufen werden, nicht festgelegt werden kann. Wenn Sie über mehrere <xref:System.EventHandler> Delegaten verfügen, die auf einer bestimmten Reihenfolge basieren, sollten <xref:System.Windows.Media.CompositionTarget.Rendering> Sie ein einzelnes Ereignis registrieren und die Delegaten selbst in der richtigen Reihenfolge durcharbeiten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.CompositionTarget>
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
