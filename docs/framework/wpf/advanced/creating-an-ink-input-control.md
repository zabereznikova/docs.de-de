---
title: Erstellen eines Freihandeingabesteuerelements
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: 98b2abf813a232e36b80683254174b12b97659bb
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095215"
---
# <a name="creating-an-ink-input-control"></a>Erstellen eines Freihandeingabesteuerelements
Sie können ein benutzerdefiniertes Steuerelement erstellen, das frei Hand Eingaben dynamisch und statisch rendert. Das heißt, frei Hand Eingaben, wenn ein Benutzer einen Strich zeichnet, der bewirkt, dass die frei Hand Eingaben aus dem Tablettstift "fließen" und frei Hand Eingaben angezeigt werden, nachdem Sie dem Steuerelement hinzugefügt wurden, entweder über den Tablettstift, eingefügt aus der Zwischenablage oder aus einer Datei geladen. Zum dynamischen RenderInk muss das Steuerelement eine <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>verwenden. Zum statischen Rendern von frei Hand Eingaben müssen Sie die Stift-Ereignis Methoden (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>und <xref:System.Windows.UIElement.OnStylusUp%2A>) überschreiben, um <xref:System.Windows.Input.StylusPoint> Daten zu erfassen, Striche zu erstellen und Sie einer <xref:System.Windows.Controls.InkPresenter> hinzuzufügen (wodurch die frei Hand Eingaben auf dem Steuerelement gerendert werden).  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
- [Gewusst wie: Sammeln von Tablettstiftpunkt-Daten und Erstellen von frei Hand Strichen](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [Gewusst wie: Aktivieren des Steuer Elements für die Annahme von Eingaben von der Maus](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [Kombinieren](#PuttingItTogether)  
  
- [Verwenden zusätzlicher Plug-ins und DynamicRenderer](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [Fazit](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Gewusst wie: Sammeln von Tablettstiftpunkt-Daten und Erstellen von frei Hand Strichen  
 Gehen Sie folgendermaßen vor, um ein Steuerelement zu erstellen, das frei Hand Eingaben sammelt und verwaltet  
  
1. Leiten Sie eine Klasse von <xref:System.Windows.Controls.Control> oder einer der Klassen ab, die von <xref:System.Windows.Controls.Control>abgeleitet werden, z. b. <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Fügen Sie der-Klasse einen <xref:System.Windows.Controls.InkPresenter> hinzu, und legen Sie die <xref:System.Windows.Controls.ContentControl.Content%2A>-Eigenschaft auf den neuen <xref:System.Windows.Controls.InkPresenter>fest.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. Fügen Sie die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> an die <xref:System.Windows.Controls.InkPresenter> an, indem Sie die <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A>-Methode aufrufen, und fügen Sie der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Auflistung den <xref:System.Windows.UIElement.StylusPlugIns%2A> hinzu. Dadurch kann der <xref:System.Windows.Controls.InkPresenter> die frei Hand Eingabe anzeigen, wenn die Tablettstiftpunkt-Daten von Ihrem Steuerelement gesammelt werden.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusDown%2A> -Methode.  Erfassen Sie in dieser Methode den Tablettstift mit einem <xref:System.Windows.Input.Stylus.Capture%2A>aufzurufenden. Wenn Sie den Tablettstift erfassen, wird das Steuerelement weiterhin <xref:System.Windows.UIElement.StylusMove> und <xref:System.Windows.UIElement.StylusUp> Ereignisse empfangen, auch wenn der Tablettstift die Grenzen des Steuer Elements verlässt. Dies ist nicht zwingend obligatorisch, aber fast immer für eine gute Benutzer Leistung. Erstellen Sie einen neuen <xref:System.Windows.Input.StylusPointCollection>, um <xref:System.Windows.Input.StylusPoint> Daten zu erfassen. Fügen Sie schließlich dem <xref:System.Windows.Input.StylusPointCollection>den anfänglichen Satz von <xref:System.Windows.Input.StylusPoint> Daten hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusMove%2A>-Methode, und fügen Sie die <xref:System.Windows.Input.StylusPoint> Daten dem zuvor erstellten <xref:System.Windows.Input.StylusPointCollection>-Objekt hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusUp%2A>-Methode, und erstellen Sie eine neue <xref:System.Windows.Ink.Stroke> mit den <xref:System.Windows.Input.StylusPointCollection> Daten. Fügen Sie den neuen <xref:System.Windows.Ink.Stroke>, den Sie erstellt haben, zur <xref:System.Windows.Controls.InkPresenter.Strokes%2A> Auflistung der <xref:System.Windows.Controls.InkPresenter> und Release Stift Capture hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Gewusst wie: Aktivieren des Steuer Elements für die Annahme von Eingaben von der Maus  
 Wenn Sie der Anwendung das vorangehende Steuerelement hinzufügen, es ausführen und die Maus als Eingabegerät verwenden, werden Sie feststellen, dass die Striche nicht persistent gespeichert werden. Gehen Sie folgendermaßen vor, um die Striche beizubehalten, wenn die Maus als Eingabegerät verwendet wird:  
  
1. Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A>, und erstellen Sie eine neue <xref:System.Windows.Input.StylusPointCollection> die die Position der Maus beim Auftreten des Ereignisses erhält, und erstellen Sie mithilfe der Punktdaten eine <xref:System.Windows.Input.StylusPoint>, und fügen Sie die <xref:System.Windows.Input.StylusPoint> dem <xref:System.Windows.Input.StylusPointCollection>hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> -Methode. Rufen Sie die Position der Maus ab, zu der das Ereignis aufgetreten ist, und erstellen Sie mithilfe der Punktdaten einen <xref:System.Windows.Input.StylusPoint>.  Fügen Sie dem <xref:System.Windows.Input.StylusPointCollection> Objekt, das Sie zuvor erstellt haben, die <xref:System.Windows.Input.StylusPoint> hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> -Methode.  Erstellen Sie eine neue <xref:System.Windows.Ink.Stroke> mit den <xref:System.Windows.Input.StylusPointCollection> Daten, und fügen Sie den neuen <xref:System.Windows.Ink.Stroke>, den Sie erstellt haben, der <xref:System.Windows.Controls.InkPresenter.Strokes%2A>-Auflistung des <xref:System.Windows.Controls.InkPresenter>hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>Kombinieren  
 Das folgende Beispiel ist ein benutzerdefiniertes Steuerelement, das frei Hand Eingaben sammelt, wenn der Benutzer entweder die Maus oder den Stift verwendet.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Verwenden zusätzlicher Plug-ins und DynamicRenderer  
 Wie bei InkCanvas kann Ihr benutzerdefiniertes Steuerelement auch über benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und zusätzliche <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Objekte verfügen. Fügen Sie diese der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung hinzu. Die Reihenfolge der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Objekte in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> wirkt sich auf die Darstellung der frei Hand Eingaben aus, wenn Sie gerendert wird. Angenommen, Sie verfügen über eine <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> mit dem Namen `dynamicRenderer` und ein benutzerdefiniertes <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, das als `translatePlugin` bezeichnet wird. Wenn `translatePlugin` der erste <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> im <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>ist und `dynamicRenderer` der zweite Wert ist, wird die frei Hand Eingabe, die "Flows" ist, versetzt, wenn der Benutzer den Stift verschiebt. Wenn `dynamicRenderer` erstmalig ist und `translatePlugin` der zweite Wert ist, wird die frei Hand Eingabe nicht versetzt, bis der Benutzer den Stift hebt.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>Zusammenfassung  
 Sie können ein Steuerelement erstellen, das frei Hand Eingaben sammelt und rendert, indem Sie die Stift Ereignis Methoden überschreiben. Indem Sie ein eigenes Steuerelement erstellen, ihre eigenen <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klassen ableiten und in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>einfügen, können Sie praktisch jedes Verhalten implementieren, das mit Digital Ink vorstellbar ist. Sie haben Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten, wenn Sie generiert werden. dadurch haben Sie die Möglichkeit, <xref:System.Windows.Input.Stylus> Eingaben anzupassen und Sie entsprechend der Anwendung auf dem Bildschirm zu gestalten. Da Sie einen solchen Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten auf niedriger Ebene haben, können Sie die frei Hand Erfassung implementieren und die Leistung für Ihre Anwendung mit einer optimalen Leistung erzielen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweiterte Behandlung von Freihandeingaben](advanced-ink-handling.md)
- [Zugreifen auf und Bearbeiten von Stift Eingaben](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
