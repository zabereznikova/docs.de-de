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
ms.openlocfilehash: 9a62a16f4fa16cfe40bbf830de2255bea25f8d3f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611978"
---
# <a name="custom-rendering-ink"></a>Benutzerdefiniertes Rendern von Freihandeingaben
Die <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> -Eigenschaft eines Strichs können Sie die Darstellung eines Strichs, z. B. seine Größe, Farbe und Form angeben, aber unter Umständen, die Sie zum Anpassen der Darstellung überschreiten möchten <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> ermöglichen. Sie können beispielsweise die Darstellung von Freihandeingaben so anpassen, dass sie wie ein Airbrush- oder Ölgemälde aussieht oder mit vielen weiteren Effekten gerendert wird. Die Windows Presentation Foundation (WPF) ermöglicht Ihnen benutzerdefiniertes Rendern von Freihandeingaben durch Implementierung eines benutzerdefinierten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und <xref:System.Windows.Ink.Stroke> Objekt.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
- [Architektur](#Architecture)  
  
- [Implementieren eines dynamischen Renderers](#ImplementingADynamicRenderer)  
  
- [Implementieren von benutzerdefinierten Strichen](#ImplementingCustomStrokes)  
  
- [Implementieren eines benutzerdefinierten InkCanvas](#ImplementingACustomInkCanvas)  
  
- [Schlussfolgerung](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architektur  
 Freihandeingaben werden zweimal gerendert: einmal beim Schreiben auf einer Freihandoberfläche und noch einmal, nachdem der Strich der freihandeingabefähigen Oberfläche hinzugefügt wurde. Die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> rendert Freihandeingaben bei der Benutzer den Tablettstift auf dem Digitizer bewegt und <xref:System.Windows.Ink.Stroke> rendert sich selbst, sobald er auf ein Element hinzugefügt wird.  
  
 Beim dynamischen Rendern von Freihandeingaben gibt es drei Klassen zur Implementierung.  
  
1. **DynamicRenderer**: Implementieren Sie eine Klasse, die von <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> abgeleitet ist. Diese Klasse ist ein spezieller <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> , der den Strich beim Zeichnen rendert. Die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> führt das Rendern auf einem separaten Thread, sodass der Freihandoberfläche scheinbar zum Erfassen von Freihandeingaben, selbst wenn der Benutzeroberfläche (UI) Thread blockiert wird. Weitere Informationen zum Threadmodell finden Sie unter [Das Threadmodell für Freihandeingaben](the-ink-threading-model.md). Um dynamische Rendern eines Strichs anzupassen, überschreiben die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> Methode.  
  
2. **Stroke**: Implementieren Sie eine Klasse, die von <xref:System.Windows.Ink.Stroke> abgeleitet ist. Diese Klasse ist zuständig für das statische Rendern von der <xref:System.Windows.Input.StylusPoint> Daten nach der Konvertierung in einen <xref:System.Windows.Ink.Stroke> Objekt. Überschreiben der <xref:System.Windows.Ink.Stroke.DrawCore%2A> Methode, um sicherzustellen, dass diese statische Rendern des Strichs mit dem dynamischen Rendern konsistent ist.  
  
3. **InkCanvas-Steuerelement:** Implementieren Sie eine Klasse, die von <xref:System.Windows.Controls.InkCanvas> abgeleitet ist. Weisen Sie den benutzerdefinierten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> auf die <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> Eigenschaft. Überschreiben der <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> Methode und fügen Sie einen benutzerdefinierten Strich auf die <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaft. Dadurch wird sichergestellt, dass die Darstellung der Freihandeingaben konsistent ist.  
  
<a name="ImplementingADynamicRenderer"></a>   
## <a name="implementing-a-dynamic-renderer"></a>Implementieren eines dynamischen Renderers  
 Obwohl der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Klasse ist ein Standardbestandteil von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]auszuführenden mehr spezialisierteres rendern, müssen Sie einen benutzerdefinierten dynamischen Renderer, der von abgeleitet ist, Erstellen der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und Überschreiben der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> Methode.  
  
 Das folgende Beispiel veranschaulicht eine benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> , zeichnet Freihandeingaben mit einem Pinsel mit linearem Farbverlauf mit.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## <a name="implementing-custom-strokes"></a>Implementieren von benutzerdefinierten Strichen  
 Implementieren Sie eine Klasse, die von <xref:System.Windows.Ink.Stroke> abgeleitet ist. Diese Klasse ist zuständig für das Rendering <xref:System.Windows.Input.StylusPoint> Daten nach der Konvertierung in einen <xref:System.Windows.Ink.Stroke> Objekt. Überschreiben der <xref:System.Windows.Ink.Stroke.DrawCore%2A> Klasse, um die eigentlichen Zeichenvorgang.  
  
 Die Stroke-Klasse kann auch benutzerdefinierte Daten speichern, mithilfe der <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> Methode. Diese Daten werden mit den Strichdaten gespeichert, wenn sie beibehalten werden.  
  
 Die <xref:System.Windows.Ink.Stroke> Klasse kann auch Treffertests durchzuführen. Sie können auch durch das Überschreiben von Ihren eigenen Treffertestalgorithmus implementieren die <xref:System.Windows.Ink.Stroke.HitTest%2A> -Methode in der aktuellen Klasse.  
  
 Die folgenden C# Code veranschaulicht eine benutzerdefinierte <xref:System.Windows.Ink.Stroke> -Klasse, die rendert <xref:System.Windows.Input.StylusPoint> Daten als 3D-Strich.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## <a name="implementing-a-custom-inkcanvas"></a>Implementieren eines benutzerdefinierten InkCanvas  
 Die einfachste Möglichkeit, Ihre angepassten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und Strich ist das implementieren eine Klasse, die von abgeleitet <xref:System.Windows.Controls.InkCanvas> und diese Klassen verwendet. Die <xref:System.Windows.Controls.InkCanvas> verfügt über eine <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> Eigenschaft, die angibt, wie der Strich gerendert wird, wenn der Benutzer es gezeichnet wird.  
  
 Um das Rendern Striche auf eine <xref:System.Windows.Controls.InkCanvas> gehen Sie folgendermaßen vor:  
  
- Erstellen Sie eine abgeleitete Klasse die <xref:System.Windows.Controls.InkCanvas>.  
  
- Weisen Sie den benutzerdefinierten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> auf die <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> Eigenschaft.  
  
- Überschreiben Sie die <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>-Methode. Entfernen Sie in dieser Methode den Originalstrich, der InkCanvas hinzugefügt wurde. Klicken Sie dann einen benutzerdefinierten Strich zu erstellen, Hinzufügen der <xref:System.Windows.Controls.InkCanvas.Strokes%2A> -Eigenschaft, und rufen Sie die Basisklasse mit einer neuen <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> , das den benutzerdefinierten Strich enthält.  
  
 Die folgenden C# Code veranschaulicht eine benutzerdefinierte <xref:System.Windows.Controls.InkCanvas> Klasse, die eine benutzerdefinierte verwendet <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und benutzerdefinierte Striche erfasst.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Ein <xref:System.Windows.Controls.InkCanvas> haben mehr als eine <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Sie können mehrere hinzufügen <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Objekte die <xref:System.Windows.Controls.InkCanvas> durch Hinzufügen der <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft.  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Schlussbemerkung  
 Sie können die Darstellung von Freihandeingaben anpassen, indem Sie eigene ableiten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, und <xref:System.Windows.Controls.InkCanvas> Klassen. Zusammen stellen diese Klassen sicher, dass die Darstellung des Strichs während des Zeichnens durch den Benutzer mit der Darstellung nach seiner Erfassung konsistent ist.  
  
## <a name="see-also"></a>Siehe auch

- [Erweiterte Behandlung von Freihandeingaben](advanced-ink-handling.md)
