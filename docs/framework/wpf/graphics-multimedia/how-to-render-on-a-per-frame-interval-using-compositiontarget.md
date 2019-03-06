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
ms.openlocfilehash: 919e39dbe96a1a72ce517d59dcb239636f5aa692
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353204"
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>Vorgehensweise: Rendern in Pro-Frame-Intervallen mit CompositionTarget
Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animations-Engine stellt zahlreiche Funktionen zum Erstellen framebasierter Animationen bereit. In manchen Anwendungsszenarios müssen Sie das Rendering jedoch pro Frame detaillierter steuern können. Die <xref:System.Windows.Media.CompositionTarget> Objekt bietet die Möglichkeit, benutzerdefinierte Animationen, die basierend auf einer pro-Frame-Rückruf zu erstellen.  
  
 <xref:System.Windows.Media.CompositionTarget> ist eine statische Klasse, die Anzeigeoberfläche darstellt, auf der Ihre Anwendung gezeichnet wird. Die <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis wird ausgelöst, dass jedes Mal die Szene der Anwendung gezeichnet wird. Die Renderingbildfrequenz gibt an, wie häufig die Szene pro Sekunde gezeichnet wird.  
  
> [!NOTE]
>  Für einen vollständigen Code-Beispiel mit <xref:System.Windows.Media.CompositionTarget>, finden Sie unter [Verwendung von CompositionTarget](https://go.microsoft.com/fwlink/?LinkID=160045).  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis wird ausgelöst, während die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendern. Das folgende Beispiel zeigt, wie Sie registrieren einen <xref:System.EventHandler> Delegieren der statischen <xref:System.Windows.Media.CompositionTarget.Rendering> Methode <xref:System.Windows.Media.CompositionTarget>.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Mit der Rendering-Ereignishandlermethode können Sie benutzerdefinierten Zeichnungsinhalt erstellen. Diese Ereignishandlermethode wird einmal pro Frame aufgerufen. Immer, wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der visuellen Struktur für die Szenengrafik der Komposition marshallt, wird die Ereignishandlermethode aufgerufen. Zudem wird die Ereignishandlermethode aufgerufen, wenn durch Änderungen an der visuellen Struktur Aktualisierungen der Szenengrafik erzwungen werden. Beachten Sie, dass die Ereignishandlermethode aufgerufen wird, nachdem das Layout berechnet wurde. Sie können das Layout jedoch in der Ereignishandlermethode ändern. In diesem Fall wird das Layout vor dem Rendern erneut berechnet.  
  
 Das folgende Beispiel zeigt, wie Sie angeben können benutzerdefinierte Zeichnungen in einer <xref:System.Windows.Media.CompositionTarget> Ereignishandlermethode. In diesem Fall ist die Farbe des Hintergrunds der <xref:System.Windows.Controls.Canvas> mit einem Farbwert basierend auf der Koordinatenposition der Maus gezeichnet wird. Wenn Sie die Maus innerhalb von Verschieben der <xref:System.Windows.Controls.Canvas>, dessen Hintergrund ändert. Darüber hinaus wird die durchschnittliche Bildfrequenz auf Basis der verstrichenen Zeit und der Gesamtanzahl gerenderter Frames berechnet.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Möglicherweise stellen Sie fest, dass die benutzerdefinierte Zeichnung auf verschiedenen Computern mit unterschiedlicher Geschwindigkeit ausgeführt wird. Das liegt daran, dass die benutzerdefinierte Zeichnung von der Bildfrequenz abhängt. Abhängig von dem System ausgeführt wird und die arbeitsauslastung des Systems, die <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis kann eine andere Anzahl der Versuche pro Sekunde aufgerufen werden. Informationen zur Ermittlung der Grafikleistung eines Geräts, auf dem eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung ausgeführt wird, finden Sie unter [Renderingebenen für Grafiken](../advanced/graphics-rendering-tiers.md).  
  
 Hinzufügen oder entfernen ein Rendering <xref:System.EventHandler> -Delegaten wird während der Auslösung erst nach Abschluss des Ereignisses verzögert ausgelöst. Dies ist konsistent mit dem <xref:System.MulticastDelegate>-Basis-Ereignisse in der Common Language Runtime (CLR) behandelt. Beachten Sie außerdem, dass die Reihenfolge, in der die Renderingereignisse aufgerufen werden, nicht festgelegt werden kann. Wenn mehrere <xref:System.EventHandler> Delegaten, die abhängig von einer bestimmten Reihenfolge, registrieren Sie ein einzelnes <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis, und bündeln Sie die Delegaten in der richtigen selbst Reihenfolge.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.CompositionTarget>
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
