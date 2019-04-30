---
title: Das Threadmodell für Freihandeingaben
ms.date: 03/30/2017
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
ms.openlocfilehash: 80e7ef202c46a23069766512cf4e67bb21a49564
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007387"
---
# <a name="the-ink-threading-model"></a>Das Threadmodell für Freihandeingaben
Einer der Vorteile von Freihandeingaben auf einem Tablet PC ist, dass es viel wie beim Schreiben mit einem regulären Stift und Papier fühlt sich.  Um dies zu erreichen, erfasst der Tablettstift Eingabedaten sehr viel schneller als eine Maus und Freihandeingaben während des Schreibvorgangs rendert.  Thread (Benutzeroberflächenthread) der Anwendung ist nicht für das Sammeln von Daten und zum Rendern von Freihandeingaben, ausreichend, da er blockiert werden kann.  Um dies zu lösen eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung verwendet zwei zusätzliche Threads aus, wenn der Freihandeingabe.  
  
 Die folgende Liste beschreibt die Threads, die dadurch beim Sammeln und Rendern von Freihandeingaben schleifenspezifischen:  
  
- Stiftthread - Threads, der Eingabe des Tablettstifts verwendet wird.  (Klicken Sie in der Praxis sieht ein Threadpool, aber dieses Thema bezieht sich darauf, wie einem Stiftthread.)  
  
- Anwendungsbenutzeroberflächenthread - Threads, der die Benutzeroberfläche der Anwendung steuert.  
  
- Thread für dynamisches Rendering - zeichnet der Thread, der rendert Freihandeingaben während der Benutzer einen Strich. Der Thread für dynamisches Rendering unterscheidet sich der Thread, der andere Benutzeroberflächenelemente für die Anwendung, gerendert werden, wie in Windows Presentation Foundation [Threading-Modell](threading-model.md).  
  
 Das bereitgestelltem Modell ist identisch, ob die Anwendung verwendet die <xref:System.Windows.Controls.InkCanvas> oder ein benutzerdefiniertes Steuerelement im ähnelt [erstellen ein Steuerelement für Freihandeingaben](creating-an-ink-input-control.md).  Obwohl in diesem Thema wird das Threading behandeln, in Form von der <xref:System.Windows.Controls.InkCanvas>, die gleichen Konzepte gelten, wenn Sie ein benutzerdefiniertes Steuerelement erstellen.  
  
## <a name="threading-overview"></a>Übersicht über Threading  
 Das folgende Diagramm veranschaulicht das Threadingmodell auf, wenn ein Benutzer einen Strich zeichnet:  
  
 ![Threading-Modell beim Zeichnen eines Strichs. ](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")  
  
1. Aktionen, die auftreten, während des Zeichnens durch des Benutzers  
  
    1. Wenn der Benutzer einen Strich zeichnet, gibt die Tablettstiftpunkte im Stiftthread.  Stift-Plug-ins, einschließlich der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, akzeptieren Sie die Tablettstiftpunkte im Stiftthread und haben die Möglichkeit, die sie vor dem Ändern der <xref:System.Windows.Controls.InkCanvas> Empfangs.  
  
    2. Die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> die Tablettstiftpunkte, die auf den Thread für dynamisches Rendering gerendert. Dies geschieht zur gleichen Zeit wie im vorherigen Schritt.  
  
    3. Die <xref:System.Windows.Controls.InkCanvas> empfängt die Tablettstiftpunkte, die im UI-Thread.  
  
2. Aktionen, die auftreten, nachdem der Benutzer der Strich beendet.  
  
    1. Strich gezeichnet hat, nach Abschluss der Benutzer die <xref:System.Windows.Controls.InkCanvas> erstellt eine <xref:System.Windows.Ink.Stroke> -Objekt und fügt es der <xref:System.Windows.Controls.InkPresenter>, die statisch gerendert wird.  
  
    2. Die UI-Thread-Warnungen der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> , der der Strich gerendert wird statisch, sodass die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> entfernt dessen visuelle Darstellung des Strichs.  
  
## <a name="ink-collection-and-stylus-plug-ins"></a>Erfassen von Freihandeingaben Sie und Stift-Plug-ins  
 Jede <xref:System.Windows.UIElement> verfügt über eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Objekte in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> erhalten, und die Tablettstiftpunkte im Stiftthread ändern können. Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Objekte empfangen, die Tablettstiftpunkte entsprechend ihrer Reihenfolge in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  
  
 Das folgende Diagramm veranschaulicht die hypothetische Situation, in dem die <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung von eine <xref:System.Windows.UIElement> enthält `stylusPlugin1`, eine <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, und `stylusPlugin2`in dieser Reihenfolge.  
  
 ![Reihenfolge der Tablettstift-Plugins beeinflusst Ausgabe. ](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")  
  
 In der vorherigen Abbildung findet folgendes statt:  
  
1. `StylusPlugin1` Ändert die Werte für x und y.  
  
2. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> die geänderte Tablettstiftpunkte empfangen, und klicken Sie auf der Thread für dynamisches Rendering gerendert.  
  
3. `StylusPlugin2` die geänderte Tablettstiftpunkte empfangen und weitere ändert die Werte für x und y.  
  
4. Die Anwendung die Tablettstiftpunkte erfasst, und wenn der Benutzer den Strich, beendet der Strich statisch gerendert.  
  
 Nehmen wir an, die `stylusPlugin1` schränkt die Tablettstiftpunkte, die ein Rechteck und `stylusPlugin2` übersetzt die Tablettstiftpunkte, die auf der rechten Seite.  Im vorherigen Szenario das <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> empfängt die eingeschränkten Tablettstiftpunkte, jedoch nicht die übersetzten Tablettstiftpunkte.  Wenn der Benutzer einen Strich zeichnet, innerhalb der Grenzen des Rechtecks der Strich gerendert wird, aber der Strich nicht übersetzt werden, bis der Benutzer den Stift wird angezeigt.  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a>Ausführen von Vorgängen mit einem Stift-Plug-in im UI-thread  
 Da genauer Treffertest für den Stiftthread ausgeführt werden kann, möglicherweise einige Elemente gelegentlich nastala chyba vstupu für andere Elemente vorgesehen sind. Wenn Sie sicherstellen, dass die Eingabe ordnungsgemäß weitergeleitet wurde, bevor Sie einen Vorgang ausführen möchten, abonnieren und führen Sie den Vorgang in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, oder <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> Methode. Diese Methoden werden vom Thread Anwendung aufgerufen, nachdem die genauer Treffertest ausgeführt wurde. Rufen Sie zum Abonnieren dieser Methoden die <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> -Methode in der die Methode, die auf den Stiftthread auftritt.  
  
 Das folgende Diagramm veranschaulicht die Beziehung zwischen der Stiftthread und UI-Thread in Bezug auf den Stift-Ereignissen von einem <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.  
  
 ![Freihandeingaben Threadingmodelle &#40;UI und Stift&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")  
  
## <a name="rendering-ink"></a>Rendern von Freihandeingaben  
 Wenn der Benutzer einen Strich zeichnet <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> rendert Freihandeingaben auf einem separaten Thread aus, sodass die Freihandeingaben angezeigt wird, um "des Stifts flow" selbst, wenn der UI-Thread ausgelastet ist.  Die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> der Thread für dynamisches Rendering eine visuelle Struktur basiert, wie sie die Tablettstiftpunkte erfasst.  Wenn der Benutzer der Strich beendet die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> fordert benachrichtigt werden, wenn die Anwendung mit den nächsten Renderingdurchlauf ist.  Nachdem die Anwendung mit den nächsten Renderingdurchlauf abgeschlossen wurde die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> der visuellen Struktur bereinigt.  Das folgende Diagramm veranschaulicht diesen Prozess.  
  
 ![Freihandeingaben threading Diagramm](./media/inkthreading-visualtree.png "InkThreading_VisualTree")  
  
1. Der Benutzer mit den Strich beginnt.  
  
    1. Die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> erstellt die visuelle Struktur.  
  
2. Der Benutzer ist den Strich gezeichnet werden.  
  
    1. Die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> erstellt die visuelle Struktur.  
  
3. Der Benutzer beendet den Strich.  
  
    1. Die <xref:System.Windows.Controls.InkPresenter> der visuellen Struktur den Strich hinzugefügt.  
  
    2. Der Media-Integration-Ebene (MIL) rendert statisch die Striche.  
  
    3. Die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> bereinigt die visuellen Elemente.
