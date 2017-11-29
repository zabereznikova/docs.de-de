---
title: 'Gewusst wie: Rendern in Pro-Frame-Intervallen mit CompositionTarget'
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
- CompositionTarget objects [WPF], rendering per frame
- rendering per frame using CompositionTarget objects [WPF]
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7616a418b9f2f6b175b925e4385322c42546e9bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>Gewusst wie: Rendern in Pro-Frame-Intervallen mit CompositionTarget
Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationsmodul stellt zahlreiche Funktionen zum Erstellen framebasierter Animationen bereit. In manchen Anwendungsszenarios müssen Sie das Rendering jedoch pro Frame detaillierter steuern können. Die <xref:System.Windows.Media.CompositionTarget> -Objekt stellt die Fähigkeit zum Erstellen von benutzerdefinierter Animationen basierend auf einer pro-Frame-Rückruf bereit.  
  
 <xref:System.Windows.Media.CompositionTarget>ist eine statische Klasse, die die Anzeigeoberfläche darstellt, auf der Ihre Anwendung gezeichnet wird. Die <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis wird jedes Mal die Anwendung Szene gezeichnet wird. Die Renderingbildfrequenz gibt an, wie häufig die Szene pro Sekunde gezeichnet wird.  
  
> [!NOTE]
>  Für einen vollständigen Code Beispiel mit <xref:System.Windows.Media.CompositionTarget>, finden Sie unter [anhand des Beispiels CompositionTarget](http://go.microsoft.com/fwlink/?LinkID=160045).  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis ausgelöst wird, während die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendern. Das folgende Beispiel zeigt, wie Sie registrieren einen <xref:System.EventHandler> Delegieren der statischen <xref:System.Windows.Media.CompositionTarget.Rendering> Methode <xref:System.Windows.Media.CompositionTarget>.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Mit der Rendering-Ereignishandlermethode können Sie benutzerdefinierten Zeichnungsinhalt erstellen. Diese Ereignishandlermethode wird einmal pro Frame aufgerufen. Immer, wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der visuellen Struktur für die Szenengrafik der Komposition marshallt, wird die Ereignishandlermethode aufgerufen. Zudem wird die Ereignishandlermethode aufgerufen, wenn durch Änderungen an der visuellen Struktur Aktualisierungen der Szenengrafik erzwungen werden. Beachten Sie, dass die Ereignishandlermethode aufgerufen wird, nachdem das Layout berechnet wurde. Sie können das Layout jedoch in der Ereignishandlermethode ändern. In diesem Fall wird das Layout vor dem Rendern erneut berechnet.  
  
 Das folgende Beispiel zeigt, wie Sie bereitstellen können benutzerdefinierte Zeichnung einem <xref:System.Windows.Media.CompositionTarget> Ereignishandlermethode. In diesem Fall wird die Hintergrundfarbe der <xref:System.Windows.Controls.Canvas> mit einem Color-Wert, der auf Grundlage der-Koordinate Position der Maus gezeichnet wird. Wenn Sie die Maus innerhalb Verschieben der <xref:System.Windows.Controls.Canvas>, dessen Farbe Änderungen im Hintergrund. Darüber hinaus wird die durchschnittliche Bildfrequenz auf Basis der verstrichenen Zeit und der Gesamtanzahl gerenderter Frames berechnet.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Möglicherweise stellen Sie fest, dass die benutzerdefinierte Zeichnung auf verschiedenen Computern mit unterschiedlicher Geschwindigkeit ausgeführt wird. Das liegt daran, dass die benutzerdefinierte Zeichnung von der Bildfrequenz abhängt. Abhängig von dem System ausgeführt wird und der arbeitsauslastung des Systems, die <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis können Sie eine andere Anzahl der Versuche pro Sekunde aufgerufen werden. Informationen zur Ermittlung der Grafikleistung eines Geräts, auf dem eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung ausgeführt wird, finden Sie unter [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 Hinzufügen oder Entfernen eines <xref:System.EventHandler> Delegaten während der Auslösung wird erst verzögert werden, nach Abschluss des Ereignisses ausgelöst. Dies ist konsistent mit <xref:System.MulticastDelegate>-Basis-Ereignisse in der Common Language Runtime (CLR) behandelt. Beachten Sie außerdem, dass die Reihenfolge, in der die Renderingereignisse aufgerufen werden, nicht festgelegt werden kann. Wenn mehrere <xref:System.EventHandler> Delegaten, die abhängig von einer bestimmten Reihenfolge, registrieren Sie ein einzelnes <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis, und bündeln Sie die Delegaten in der richtigen selbst Reihenfolge.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.CompositionTarget>  
 [Übersicht über das WPF-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
