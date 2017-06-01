---
title: "Gewusst wie: Rendern in Pro-Frame-Intervallen mit CompositionTarget | Microsoft Docs"
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
  - "CompositionTarget-Objekte, Rendern per Frame"
  - "Rendern per Frame mit CompositionTarget-Objekten"
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Rendern in Pro-Frame-Intervallen mit CompositionTarget
Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationsmodul stellt zahlreiche Features zum Erstellen framebasierter Animationen bereit.  In manchen Anwendungsszenarios müssen Sie das Rendering jedoch auf Pro\-Frame\-Basis steuern können.  Das <xref:System.Windows.Media.CompositionTarget>\-Objekt bietet die Möglichkeit, benutzerdefinierte Animationen auf der Grundlage von Pro\-Frame\-Rückrufen zu erstellen.  
  
 <xref:System.Windows.Media.CompositionTarget> ist eine statische Klasse, die die Anzeigeoberfläche darstellt, auf der die Anwendung gezeichnet wird.  Das <xref:System.Windows.Media.CompositionTarget.Rendering>\-Ereignis wird jedes Mal ausgelöst, wenn die Szene der Anwendung gezeichnet wird.  Die Rendering\-Framerate gibt an, wie häufig die Szene pro Sekunde gezeichnet wird.  
  
> [!NOTE]
>  Ein vollständiges Codebeispiel für <xref:System.Windows.Media.CompositionTarget> finden Sie unter [Beispiel für die Verwendung von CompositionTarget](http://go.microsoft.com/fwlink/?LinkID=160045).  
  
## Beispiel  
 Das <xref:System.Windows.Media.CompositionTarget.Rendering>\-Ereignis wird während des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Renderingprozesses ausgelöst.  Im folgenden Beispiel wird gezeigt, wie Sie einen <xref:System.EventHandler>\-Delegaten bei der statischen <xref:System.Windows.Media.CompositionTarget.Rendering>\-Methode für <xref:System.Windows.Media.CompositionTarget> registrieren.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Mit der Rendering\-Ereignishandlermethode können Sie benutzerdefinierten Zeichnungsinhalt erstellen.  Diese Ereignishandlermethode wird einmal pro Frame aufgerufen.  Immer wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der [visuellen Struktur](GTMT) für die Szenengrafik der Komposition marshallt, wird die Ereignishandlermethode aufgerufen.  Zudem wird die Ereignishandlermethode aufgerufen, wenn durch Änderungen an der [visuellen Struktur](GTMT) Aktualisierungen der Szenengrafik erzwungen werden.  Beachten Sie, dass die Ereignishandlermethode aufgerufen wird, nachdem das Layout berechnet wurde.  Sie können das Layout jedoch in der Ereignishandlermethode ändern. In diesem Fall wird das Layout vor dem Rendern nochmals berechnet.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie in einer <xref:System.Windows.Media.CompositionTarget>\-Ereignishandlermethode benutzerdefinierte Zeichnungen bereitstellen können.  In diesem Fall wird die Hintergrundfarbe von <xref:System.Windows.Controls.Canvas> mit einem Farbwert erstellt, der auf der Koordinatenposition der Maus basiert.  Wenn Sie die Maus innerhalb von <xref:System.Windows.Controls.Canvas>, bewegen, ändert sich die Hintergrundfarbe.  Darüber hinaus wird die durchschnittliche Framerate auf Basis der verstrichenen Zeit und der Gesamtanzahl gerenderter Frames berechnet.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Möglicherweise stellen Sie fest, dass die benutzerdefinierte Zeichnung auf verschiedenen Computern mit unterschiedlicher Geschwindigkeit ausgeführt wird.  Das liegt daran, dass die benutzerdefinierte Zeichnung von der Framerate abhängt.  Je nach Betriebssystem und Arbeitslast wird das <xref:System.Windows.Media.CompositionTarget.Rendering>\-Ereignis pro Sekunde unterschiedlich oft aufgerufen.  Informationen zur Ermittlung der Grafikleistung eines Geräts, auf dem eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung ausgeführt wird, finden Sie unter [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 Das Hinzufügen bzw. Entfernen eines <xref:System.EventHandler>\-Delegaten wird während der Auslösung des Ereignisses ausgesetzt.  Dies entspricht der Behandlung von <xref:System.MulticastDelegate>\-basierten Ereignissen in der Common Language Runtime \(CLR\).  Beachten Sie außerdem, dass die Reihenfolge, in der die Rendering\-Ereignisse aufgerufen werden, nicht festgelegt werden kann.  Wenn Sie über mehrere <xref:System.EventHandler>\-Delegaten verfügen, die auf einer bestimmten Reihenfolge basieren, registrieren Sie ein einzelnes <xref:System.Windows.Media.CompositionTarget.Rendering>\-Ereignis, und bündeln Sie die Delegaten selbst in der richtigen Reihenfolge.  
  
## Siehe auch  
 <xref:System.Windows.Media.CompositionTarget>   
 [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)