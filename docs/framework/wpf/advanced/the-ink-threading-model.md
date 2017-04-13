---
title: "Das Threadmodell f&#252;r Freihandeingaben | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungsbenutzeroberflächenthread"
  - "Thread für dynamisches Rendering"
  - "Freihandeingabe-Plug-In"
  - "Threadmodell für Freihandeingaben"
  - "Freihandeingaben, Rendering"
  - "Stiftthread"
  - "Plug-Ins, für Freihandeingaben"
  - "Rendern von Freihandeingaben"
  - "Stift-Plug-In"
  - "Threadingmodell"
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Das Threadmodell f&#252;r Freihandeingaben
Einer der Vorteile von Freihandeingaben auf einem Tablet PC ist, dass der Eindruck entsteht, mit einem echten Stift auf Papier zu schreiben.  Um dies zu bewerkstelligen, werden vom Tablettstift die Eingabedaten mit einer im Vergleich zu einer Maus wesentlich höheren Rate erfasst und die Freihandeingabe während des Schreibvorgangs gerendert.  Der Benutzeroberflächenthread \(UI\-Thread\) der Anwendung ist zum Erfassen der Daten und zum Rendern der Freihandeingabe nicht ausreichend, da er blockiert werden kann.  Um dieses Problem zu lösen, werden von einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung zwei zusätzliche Threads für die Freihandeingabe verwendet.  
  
 In der folgenden Liste werden die Threads erläutert, die am Erfassen und Rendern digitaler Freihandeingaben beteiligt sind:  
  
-   Thread für den Tablettstift \(Stiftthread\) \- In diesem Thread werden die Daten vom Tablettstift erfasst.  \(Eigentlich handelt es sich um einen Threadpool, in diesem Thema wird er jedoch als einzelner Stiftthread dargestellt.\)  
  
-   Thread für die Anwendungsbenutzeroberfläche \(UI\-Thread\) \- Von diesem Thread wird die Benutzeroberfläche der Anwendung gesteuert.  
  
-   Thread für das dynamische Rendering \(Rendering\-Thread\) \- In diesem Thread wird die Freihandeingabe gerendert, während der Benutzer einen Strich zeichnet.  Der Thread für das dynamische Rendering unterscheidet sich von dem Thread, in dem andere Benutzeroberflächenelemente für die Anwendung gerendert werden, wie unter Window Presentation Foundation [Threading\-Modell](../../../../docs/framework/wpf/advanced/threading-model.md) erläutert.  
  
 Das gleiche Freihandeingabemodell wird verwendet, unabhängig davon, ob von der Anwendung das <xref:System.Windows.Controls.InkCanvas>\-Steuerelement oder ein benutzerdefiniertes Steuerelement verwendet wird, vergleichbar mit dem unter [Erstellen eines Freihandeingabesteuerelements](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md) beschriebenen.  In diesem Thema wird Threading in Bezug auf <xref:System.Windows.Controls.InkCanvas> erläutert, die gleiche Konzepte gelten jedoch auch für benutzerdefinierte Steuerelemente.  
  
## Übersicht über Threading  
 Im folgenden Diagramm wird das Threadingmodell beim Zeichnen eines Strichs durch den Benutzer veranschaulicht:  
  
 ![Verkettungsmodell beim Zeichnen eines Strichs.](../../../../docs/framework/wpf/advanced/media/inkthreading-drawingink.png "InkThreading\_DrawingInk")  
  
1.  Auftretende Aktionen während des Zeichnens eines Strichs durch den Benutzer  
  
    1.  Wenn der Benutzer einen Strich zeichnet, werden die Tablettstiftpunkte über den Stiftthread erfasst.  Von Tablettstift\-Plug\-Ins, einschließlich <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, werden die Tablettstiftpunkte im Stiftthread angenommen und ggf. bearbeitet, bevor sie von <xref:System.Windows.Controls.InkCanvas> empfangen werden.  
  
    2.  Vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> werden die Tablettstiftpunkte im dynamischen Rendering\-Thread gerendert.  Dies wird zur gleichen Zeit wie der vorherige Schritt ausgeführt.  
  
    3.  Vom <xref:System.Windows.Controls.InkCanvas> werden die Tablettstiftpunkte im UI\-Thread empfangen.  
  
2.  Auftretende Aktionen nach dem Zeichnen eines Strichs durch den Benutzer  
  
    1.  Nachdem der Benutzer einen Strich gezeichnet hat, wird vom <xref:System.Windows.Controls.InkCanvas> ein <xref:System.Windows.Ink.Stroke>\-Objekt erstellt und dem <xref:System.Windows.Controls.InkPresenter> hinzugefügt, von dem es statisch gerendert wird.  
  
    2.  Der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> wird vom UI\-Thread benachrichtigt, dass der Strich statisch gerendert wird. Die grafische Darstellung des Strichs vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> wird daraufhin von diesem gelöscht.  
  
## Erfassen von Freihandeingaben und Tablettstift\-Plug\-Ins  
 Jedes <xref:System.Windows.UIElement> verfügt über eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  Von den <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>\-Objekten in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> werden die Tablettstiftpunkte im Stiftthread empfangen und ggf. bearbeitet.  Von den <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>\-Objekten werden die Tablettstiftpunkte entsprechend ihrer Reihenfolge in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> empfangen.  
  
 Im folgenden Diagramm wird Situation angenommen, in der die <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Auflistung eines <xref:System.Windows.UIElement> ein `stylusPlugin1`, einen <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und ein `stylusPlugin2` enthält \(in dieser Reihenfolge\).  
  
 ![Reihenfolge der Tablettstift&#45;Plugins beeinflusst Ausgabe.](../../../../docs/framework/wpf/advanced/media/inkthreading-pluginorder.png "InkThreading\_PluginOrder")  
  
 Im oben dargestellten Diagramm findet das folgende Verhalten statt:  
  
1.  Von `StylusPlugin1` werden die Werte für x und y bearbeitet.  
  
2.  Vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> werden die bearbeiteten Tablettstiftpunkte empfangen und im dynamischen Rendering\-Thread gerendert.  
  
3.  Von `StylusPlugin2` werden die bearbeiteten Tablettstiftpunkte empfangen und die Werte für x und y weiter bearbeitet.  
  
4.  Von der Anwendung werden die Tablettstiftpunkte erfasst und der Strich statisch gerendert, nachdem er vom Benutzer gezeichnet wurde.  
  
 Angenommen, von `stylusPlugin1` werden die Tablettstiftpunkte auf ein Rechteck eingeschränkt und von `stylusPlugin2` nach rechts verschoben.  Im oben beschriebenen Szenario werden die eingeschränkten Tablettstiftpunkte vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> empfangen, jedoch nicht die verschobenen Tablettstiftpunkte.  Wenn der Benutzer einen Strich zeichnet, wird der Strich innerhalb des Rechtecks gerendert, jedoch solange nicht verschoben, bis der Tablettstift vom Benutzer angehoben wird.  
  
### Ausführen von Vorgängen mit einem Tablettstift\-Plug\-In im UI\-Thread  
 Da eine genaue Trefferüberprüfung im Stiftthread nicht ausgeführt werden kann, werden von einigen Elementen möglicherweise gelegentlich Tablettstifteingaben empfangen, die für andere Elemente vorgesehen sind.  Wenn Sie sicherstellen müssen, dass die Eingabe vor dem Ausführen eines Vorgangs korrekt weitergeleitet wurde, abonnieren Sie die folgenden Methoden, und führen Sie den Vorgang in diesen aus: <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A> oder <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A>.  Diese Methoden werden vom Anwendungsthread nach der Ausführung einer genauen Trefferüberprüfung aufgerufen.  Rufen Sie zum Abonnieren dieser Methoden die <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A>\-Methode in der im Stiftthread ausgeführten Methode auf.  
  
 Im folgenden Diagramm sind die Beziehungen zwischen dem Stiftthread und dem UI\-Thread hinsichtlich der Tablettstiftereignisse eines <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> dargestellt.  
  
 ![Freihandverkettungsmodelle &#40;UI und Stift&#41;](../../../../docs/framework/wpf/advanced/media/inkthreading-plugincallbacks.png "InkThreading\_PluginCallbacks")  
  
## Rendern von Freihandeingaben  
 Wenn der Benutzer einen Strich zeichnet, wird die Freihandeingabe von <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> in einem separaten Thread gerendert, sodass der Tablettstift auch dann für eine Freihandeingabe verwendet werden kann, wenn der UI\-Thread ausgelastet ist.  Vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> wird beim Erfassen der Tablettstiftpunkte eine visuelle Struktur im dynamischen Rendering\-Thread erstellt.  Nachdem der Benutzer den Strich gezeichnet hat, wird vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> eine Benachrichtigung gefordert, wenn von der Anwendung der nächste Renderingdurchlauf ausgeführt wird.  Nachdem die Anwendung den nächsten Renderingdurchlauf ausgeführt hat, wird die visuelle Struktur vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> gelöscht.  Dieser Prozess wird anhand des folgenden Diagramms veranschaulicht.  
  
 ![Freihandverkettungsdiagramm](../../../../docs/framework/wpf/advanced/media/inkthreading-visualtree.png "InkThreading\_VisualTree")  
  
1.  Der Benutzer beginnt, den Strich zu zeichnen.  
  
    1.  Vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> wird eine visuelle Struktur erstellt.  
  
2.  Der Benutzer zeichnet den Strich.  
  
    1.  Vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> wird die visuelle Struktur erstellt.  
  
3.  Der Benutzer beendet den Strich.  
  
    1.  Der Strich wird von <xref:System.Windows.Controls.InkPresenter> seiner visuellen Struktur hinzugefügt.  
  
    2.  Die Striche werden von Media Integration Layer \(MIL\) statisch gerendert.  
  
    3.  Die visuelle Struktur wird vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> gelöscht.