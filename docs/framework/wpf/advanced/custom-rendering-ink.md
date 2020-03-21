---
title: Benutzerdefiniertes Rendern von Freihandeingaben
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
ms.openlocfilehash: 0ceb831057a9a92aa7319d2004f04d7cf5ac820e
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111828"
---
# <a name="custom-rendering-ink"></a>Benutzerdefiniertes Rendern von Freihandeingaben
Mit <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> der Eigenschaft eines Strichs können Sie die Darstellung eines Strichs angeben, z. B. Größe, Farbe und <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> Form. Sie können beispielsweise die Darstellung von Freihandeingaben so anpassen, dass sie wie ein Airbrush- oder Ölgemälde aussieht oder mit vielen weiteren Effekten gerendert wird. Mit der Windows Presentation Foundation (WPF) können Sie <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> benutzerdefinierten Rendern von Tinte durch Implementieren einer benutzerdefinierten und <xref:System.Windows.Ink.Stroke> eines Objekts.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
- [Architektur](#Architecture)  
  
- [Implementieren eines dynamischen Renderers](#ImplementingADynamicRenderer)  
  
- [Implementieren von benutzerdefinierten Strichen](#ImplementingCustomStrokes)  
  
- [Implementieren eines benutzerdefinierten InkCanvas](#ImplementingACustomInkCanvas)  
  
- [Schlussfolgerung](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Aufbau  
 Freihandeingaben werden zweimal gerendert: einmal beim Schreiben auf einer Freihandoberfläche und noch einmal, nachdem der Strich der freihandeingabefähigen Oberfläche hinzugefügt wurde. Der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> rendert die Tinte, wenn der Benutzer den Tablettstift auf dem Digitizer verschiebt, und der <xref:System.Windows.Ink.Stroke> rendert sich selbst, sobald er einem Element hinzugefügt wird.  
  
 Beim dynamischen Rendern von Freihandeingaben gibt es drei Klassen zur Implementierung.  
  
1. **DynamicRenderer**: Implementieren Sie eine <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>Klasse, die von ableitet. Diese Klasse ist <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> eine Spezialistin, die den Strich beim Zeichnen rendert. Das <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Rendering in einem separaten Thread, sodass die Freihandfläche Freihandeinfäden zu sammeln scheint, auch wenn der Thread der Benutzeroberflächenschnittstelle der Anwendung blockiert ist. Weitere Informationen zum Threadmodell finden Sie unter [Das Threadmodell für Freihandeingaben](the-ink-threading-model.md). Um das dynamische Rendern eines <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> Strichs anzupassen, überschreiben Sie die Methode.  
  
2. **Strich**: Implementieren Sie eine <xref:System.Windows.Ink.Stroke>Klasse, die von ableitet. Diese Klasse ist für das <xref:System.Windows.Input.StylusPoint> statische Rendern der <xref:System.Windows.Ink.Stroke> Daten verantwortlich, nachdem sie in ein Objekt konvertiert wurden. Überschreiben <xref:System.Windows.Ink.Stroke.DrawCore%2A> Sie die Methode, um sicherzustellen, dass das statische Rendering des Strichs mit dem dynamischen Rendern konsistent ist.  
  
3. **InkCanvas:** Implementieren Sie eine Klasse, <xref:System.Windows.Controls.InkCanvas>die von ableitet. Weisen Sie <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> die <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> angepasste Eigenschaft der Eigenschaft zu. Überschreiben <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> Sie die Methode, und <xref:System.Windows.Controls.InkCanvas.Strokes%2A> fügen Sie der Eigenschaft einen benutzerdefinierten Strich hinzu. Dadurch wird sichergestellt, dass die Darstellung der Freihandeingaben konsistent ist.  
  
<a name="ImplementingADynamicRenderer"></a>
## <a name="implementing-a-dynamic-renderer"></a>Implementieren eines dynamischen Renderers  
 Obwohl <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> die Klasse ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Standardteil von ist, um ein spezielleres Rendering durchzuführen, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> müssen Sie <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> einen benutzerdefinierten dynamischen Renderer erstellen, der von der ableitet, und die Methode überschreiben.  
  
 Im folgenden Beispiel <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> wird eine angepasste Datei veranschaulicht, die Tinte mit einem linearen Farbverlaufspinseleffekt zeichnet.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>
## <a name="implementing-custom-strokes"></a>Implementieren von benutzerdefinierten Strichen  
 Implementieren Sie eine Klasse, die von <xref:System.Windows.Ink.Stroke> abgeleitet ist. Diese Klasse ist <xref:System.Windows.Input.StylusPoint> für das Rendern von <xref:System.Windows.Ink.Stroke> Daten verantwortlich, nachdem sie in ein Objekt konvertiert wurden. Überschreiben <xref:System.Windows.Ink.Stroke.DrawCore%2A> Sie die Klasse, um die eigentliche Zeichnung zu übernehmen.  
  
 Ihre Stroke-Klasse kann auch benutzerdefinierte Daten mithilfe der <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> Methode speichern. Diese Daten werden mit den Strichdaten gespeichert, wenn sie beibehalten werden.  
  
 Die <xref:System.Windows.Ink.Stroke> Klasse kann auch Treffertests durchführen. Sie können auch Einen eigenen Treffertestalgorithmus <xref:System.Windows.Ink.Stroke.HitTest%2A> implementieren, indem Sie die Methode in der aktuellen Klasse überschreiben.  
  
 Der folgende C-Code <xref:System.Windows.Ink.Stroke> veranschaulicht eine <xref:System.Windows.Input.StylusPoint> benutzerdefinierte Klasse, die Daten als 3D-Hub rendert.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>
## <a name="implementing-a-custom-inkcanvas"></a>Implementieren eines benutzerdefinierten InkCanvas  
 Die einfachste Möglichkeit, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Ihre angepassten und Strich zu implementieren, ist die Implementierung einer Klasse, die von <xref:System.Windows.Controls.InkCanvas> diesen Klassen ableitet und diese verwendet. Der <xref:System.Windows.Controls.InkCanvas> verfügt <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> über eine Eigenschaft, die angibt, wie der Strich gerendert wird, wenn der Benutzer ihn zeichnet.  
  
 Um benutzerdefinierte Renderstriche auf einem <xref:System.Windows.Controls.InkCanvas> zu verwenden, gehen Sie wie folgt vor:  
  
- Erstellen Sie eine Klasse, <xref:System.Windows.Controls.InkCanvas>die von der ableitet.  
  
- Weisen Sie <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Ihre <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> angepasste Eigenschaft der Eigenschaft zu.  
  
- Überschreiben Sie die <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> -Methode. Entfernen Sie in dieser Methode den Originalstrich, der InkCanvas hinzugefügt wurde. Erstellen Sie dann einen benutzerdefinierten <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Strich, fügen Sie ihn <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> der Eigenschaft hinzu, und rufen Sie die Basisklasse mit einem neuen auf, der den benutzerdefinierten Strich enthält.  
  
 Der folgende C-Code <xref:System.Windows.Controls.InkCanvas> veranschaulicht eine benutzerdefinierte Klasse, die eine benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Klasse verwendet und benutzerdefinierte Striche sammelt.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Ein <xref:System.Windows.Controls.InkCanvas> kann mehr <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>als eine haben. Sie können <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> dem <xref:System.Windows.Controls.InkCanvas> mehrere Objekte hinzufügen, <xref:System.Windows.UIElement.StylusPlugIns%2A> indem Sie sie der Eigenschaft hinzufügen.  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>Zusammenfassung  
 Sie können die Darstellung von Tinte anpassen, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Ink.Stroke>indem <xref:System.Windows.Controls.InkCanvas> Sie eigene , und Klassen ableiten. Zusammen stellen diese Klassen sicher, dass die Darstellung des Strichs während des Zeichnens durch den Benutzer mit der Darstellung nach seiner Erfassung konsistent ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweiterte Behandlung von Freihandeingaben](advanced-ink-handling.md)
