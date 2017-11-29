---
title: Benutzerdefiniertes Rendern von Freihandeingaben
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
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90d2ab68f76bef8d8f437a7dd6096011889303fa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="custom-rendering-ink"></a>Benutzerdefiniertes Rendern von Freihandeingaben
Die <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> Eigenschaft eines Strichs ermöglicht Ihnen das Festlegen der Darstellung des Strichs, z. B. seine Größe, Farbe und Form ", aber möglicherweise gibt es Zeiten, die zum Anpassen der Darstellung hinausgehen sollen <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> zulassen. Sie können beispielsweise die Darstellung von Freihandeingaben so anpassen, dass sie wie ein Airbrush- oder Ölgemälde aussieht oder mit vielen weiteren Effekten gerendert wird. Die [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] ermöglicht es Ihnen, benutzerdefinierte Ink durch Implementierung eines benutzerdefinierten Rendern <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und <xref:System.Windows.Ink.Stroke> Objekt.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   [Architektur](#Architecture)  
  
-   [Implementieren eines dynamischen Renderers](#ImplementingADynamicRenderer)  
  
-   [Implementieren von benutzerdefinierten Strichen](#ImplementingCustomStrokes)  
  
-   [Implementieren eines benutzerdefinierten InkCanvas](#ImplementingACustomInkCanvas)  
  
-   [Schlussfolgerung](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architektur  
 Freihandeingaben werden zweimal gerendert: einmal beim Schreiben auf einer Freihandoberfläche und noch einmal, nachdem der Strich der freihandeingabefähigen Oberfläche hinzugefügt wurde. Die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Freihandeingaben rendert, wenn der Benutzer den Tablettstift auf dem Digitizer bewegt und die <xref:System.Windows.Ink.Stroke> rendert selbst, sobald er auf ein Element hinzugefügt wird.  
  
 Beim dynamischen Rendern von Freihandeingaben gibt es drei Klassen zur Implementierung.  
  
1.  **DynamicRenderer**: Implementieren einer Klasse, die abgeleitet <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Diese Klasse ist ein spezieller <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> , rendert die Kontur, wie es gezeichnet wird. Die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> ist das Rendering in einem separaten Thread Kanton Freihand Oberfläche zum Erfassen von Freihandeingaben, selbst wenn der Thread (Benutzeroberflächenthread) blockiert wird. Weitere Informationen zum Threadmodell finden Sie unter [Das Threadmodell für Freihandeingaben](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md). Um dynamisch Rendern eines Strichs anzupassen, überschreiben die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> Methode.  
  
2.  **Strich**: Implementieren einer Klasse, die abgeleitet <xref:System.Windows.Ink.Stroke>. Diese Klasse ist verantwortlich für die Darstellung von statischen der <xref:System.Windows.Input.StylusPoint> Daten nach der Konvertierung in einen <xref:System.Windows.Ink.Stroke> Objekt. Überschreiben Sie die <xref:System.Windows.Ink.Stroke.DrawCore%2A> Methode, um sicherzustellen, statische Darstellung des Strichs mit dynamischen Rendering konsistent ist.  
  
3.  **InkCanvas:** implementieren Sie eine Klasse, die abgeleitet <xref:System.Windows.Controls.InkCanvas>. Weisen Sie den angepassten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> auf die <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> Eigenschaft. Überschreiben der <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> Methode und fügen Sie einen benutzerdefinierten Strich auf die <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaft. Dadurch wird sichergestellt, dass die Darstellung der Freihandeingaben konsistent ist.  
  
<a name="ImplementingADynamicRenderer"></a>   
## <a name="implementing-a-dynamic-renderer"></a>Implementieren eines dynamischen Renderers  
 Obwohl die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Klasse ist eine Standardaufgabe bei der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], auszuführenden mehr spezialisiert rendern, müssen Sie einen benutzerdefinierten dynamischen Renderer, die abgeleitet Erstellen der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und überschreiben die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> Methode.  
  
 Das folgende Beispiel zeigt eine angepasste <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> , zeichnet Freihandeingaben mit einem linearen Farbverlaufspinsel Effekt.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## <a name="implementing-custom-strokes"></a>Implementieren von benutzerdefinierten Strichen  
 Implementieren Sie eine Klasse, die von <xref:System.Windows.Ink.Stroke> abgeleitet ist. Diese Klasse ist verantwortlich für das Rendering <xref:System.Windows.Input.StylusPoint> Daten nach der Konvertierung in einen <xref:System.Windows.Ink.Stroke> Objekt. Überschreiben Sie die <xref:System.Windows.Ink.Stroke.DrawCore%2A> Klasse mit dem tatsächlichen gezeichnet.  
  
 Die Stroke-Klasse kann auch benutzerdefinierte Daten speichern, mithilfe der <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> Methode. Diese Daten werden mit den Strichdaten gespeichert, wenn sie beibehalten werden.  
  
 Die <xref:System.Windows.Ink.Stroke> Klasse auch Treffertests ausführen kann. Sie können auch implementieren Ihre eigenen Algorithmus-Treffertests durch Überschreiben der <xref:System.Windows.Ink.Stroke.HitTest%2A> Methode in der aktuellen Klasse.  
  
 Der folgende C#-Code zeigt ein benutzerdefiniertes <xref:System.Windows.Ink.Stroke> -Klasse, die rendert <xref:System.Windows.Input.StylusPoint> Daten als 3D Strich.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## <a name="implementing-a-custom-inkcanvas"></a>Implementieren eines benutzerdefinierten InkCanvas  
 Die einfachste Möglichkeit zum Verwenden Ihrer benutzerdefinierten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und Strich implementieren eine Klasse, die abgeleitet ist <xref:System.Windows.Controls.InkCanvas> und diese Klassen verwendet. Die <xref:System.Windows.Controls.InkCanvas> verfügt über eine <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> Eigenschaft, die angibt, wie der Strich gerendert wird, wenn der Benutzer es gezeichnet wird.  
  
 Um das Rendern Striche auf eine <xref:System.Windows.Controls.InkCanvas> gehen Sie folgendermaßen vor:  
  
-   Erstellen Sie eine Klasse, die von abgeleitet ist die <xref:System.Windows.Controls.InkCanvas>.  
  
-   Weisen Sie den benutzerdefinierten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> auf die <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> Eigenschaft.  
  
-   Überschreiben Sie die <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>-Methode. Entfernen Sie in dieser Methode den Originalstrich, der InkCanvas hinzugefügt wurde. Erstellen Sie einen benutzerdefinierten Strich, fügen Sie diese der <xref:System.Windows.Controls.InkCanvas.Strokes%2A> -Eigenschaft, und rufen die Basisklasse mit einer neuen <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> , die den benutzerdefinierten Strich enthält.  
  
 Der folgende C#-Code zeigt ein benutzerdefiniertes <xref:System.Windows.Controls.InkCanvas> Klasse, die eine benutzerdefinierte verwendet <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und benutzerdefinierte Striche erfasst.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Ein <xref:System.Windows.Controls.InkCanvas> kann mehr als einen haben <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Sie können mehrere hinzufügen <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> -Objekte und die <xref:System.Windows.Controls.InkCanvas> durch Hinzufügen der <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft.  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Schlussfolgerung  
 Sie können die Darstellung anpassen, indem Sie eine eigene abgeleitete <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, und <xref:System.Windows.Controls.InkCanvas> Klassen. Zusammen stellen diese Klassen sicher, dass die Darstellung des Strichs während des Zeichnens durch den Benutzer mit der Darstellung nach seiner Erfassung konsistent ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Behandlung von Freihandeingaben](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)
