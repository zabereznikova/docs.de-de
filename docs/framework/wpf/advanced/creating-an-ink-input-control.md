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
ms.openlocfilehash: 394318488b0afb8e043389e0abc3f51dce8604c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186283"
---
# <a name="creating-an-ink-input-control"></a>Erstellen eines Freihandeingabesteuerelements
Sie können ein benutzerdefiniertes Steuerelement erstellen, das Tinte dynamisch und statisch rendert. Das heißt, Rendern Sie Tinte, wenn ein Benutzer einen Strich zeichnet, wodurch die Tinte aus dem Tablettstift "fließt" und Die Tinte angezeigt wird, nachdem sie dem Steuerelement hinzugefügt wurde, entweder über den Tablettstift, eingefügt aus der Zwischenablage oder aus einer Datei geladen. Um Tinte dynamisch zu rendern, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>muss das Steuerelement eine verwenden. Um Tinte statisch zu rendern, müssen Sie die<xref:System.Windows.UIElement.OnStylusDown%2A> <xref:System.Windows.UIElement.OnStylusMove%2A>Eingabestiftereignismethoden ( , und <xref:System.Windows.UIElement.OnStylusUp%2A>) überschreiben, um Daten zu sammeln, <xref:System.Windows.Input.StylusPoint> Striche zu erstellen und sie einem <xref:System.Windows.Controls.InkPresenter> hinzuzufügen (der die Tinte für das Steuerelement rendert).  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
- [Gewusst wie: Sammeln von Stylus Point-Daten und Erstellen von Tintenstrichen](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [Gewusst wie: Aktivieren Des Steuerelements zum Akzeptieren von Eingaben von der Maus](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [Zusammenführung](#PuttingItTogether)  
  
- [Verwenden zusätzlicher Plug-Ins und DynamicRenderer](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [Schlussfolgerung](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Gewusst wie: Sammeln von Stylus Point-Daten und Erstellen von Tintenstrichen  
 Gehen Sie wie folgt vor, um ein Steuerelement zu erstellen, das Druckstücke sammelt und verwaltet:  
  
1. Leiten Sie eine <xref:System.Windows.Controls.Control> Klasse von oder <xref:System.Windows.Controls.Control>eine der <xref:System.Windows.Controls.Label>von abgeleiteten Klassen ab, z. B. .  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Fügen <xref:System.Windows.Controls.InkPresenter> Sie der Klasse <xref:System.Windows.Controls.ContentControl.Content%2A> eine hinzu, <xref:System.Windows.Controls.InkPresenter>und legen Sie die Eigenschaft auf die neue fest.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. Fügen <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Sie <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> die <xref:System.Windows.Controls.InkPresenter> an die <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> an, indem <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Sie <xref:System.Windows.UIElement.StylusPlugIns%2A> die Methode aufrufen, und fügen Sie die der Auflistung hinzu. Dadurch kann <xref:System.Windows.Controls.InkPresenter> die Tinte angezeigt werden, wenn die Stiftpunktdaten von Ihrem Steuerelement erfasst werden.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusDown%2A> -Methode.  Erfassen Sie bei dieser Methode den <xref:System.Windows.Input.Stylus.Capture%2A>Stift mit einem Aufruf von . Durch das Erfassen des Stifts wird <xref:System.Windows.UIElement.StylusMove> das <xref:System.Windows.UIElement.StylusUp> Steuerelement weiterhin empfangen und Ereignisse empfangen, auch wenn der Stift die Grenzen des Steuerelements verlässt. Dies ist nicht unbedingt obligatorisch, aber fast immer für eine gute Benutzererfahrung gewünscht. Erstellen Sie <xref:System.Windows.Input.StylusPointCollection> eine <xref:System.Windows.Input.StylusPoint> neue, um Daten zu sammeln. Fügen Sie schließlich den <xref:System.Windows.Input.StylusPoint> ersten <xref:System.Windows.Input.StylusPointCollection>Datensatz zum hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Überschreiben <xref:System.Windows.UIElement.OnStylusMove%2A> Sie die <xref:System.Windows.Input.StylusPoint> Methode, <xref:System.Windows.Input.StylusPointCollection> und fügen Sie die Daten dem zuvor erstellten Objekt hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Überschreiben <xref:System.Windows.UIElement.OnStylusUp%2A> Sie die Methode, und erstellen Sie eine neue <xref:System.Windows.Ink.Stroke> methode mit den <xref:System.Windows.Input.StylusPointCollection> Daten. Fügen Sie <xref:System.Windows.Ink.Stroke> die neue, die Sie erstellt haben, zur <xref:System.Windows.Controls.InkPresenter.Strokes%2A> Sammlung der <xref:System.Windows.Controls.InkPresenter> und Release-Stylus-Capture hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Gewusst wie: Aktivieren Des Steuerelements zum Akzeptieren von Eingaben von der Maus  
 Wenn Sie das vorherige Steuerelement zu Ihrer Anwendung hinzufügen, es ausführen und die Maus als Eingabegerät verwenden, werden Sie feststellen, dass die Striche nicht beibehalten werden. Um die Striche beizubehalten, wenn die Maus als Eingabegerät verwendet wird, gehen Sie wie folgt vor:  
  
1. Überschreiben <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> Sie die, <xref:System.Windows.Input.StylusPointCollection> und erstellen Sie eine neue Position <xref:System.Windows.Input.StylusPoint> der Maus abrufen, <xref:System.Windows.Input.StylusPoint> wenn <xref:System.Windows.Input.StylusPointCollection>das Ereignis aufgetreten ist, und erstellen Sie eine mit den Punktdaten, und fügen Sie die zum hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> -Methode. Rufen Sie die Position der Maus ab, als das Ereignis aufgetreten ist, und erstellen Sie eine <xref:System.Windows.Input.StylusPoint> verwendungsmenge der Punktdaten.  Fügen <xref:System.Windows.Input.StylusPoint> Sie <xref:System.Windows.Input.StylusPointCollection> die dem Objekt hinzu, das Sie zuvor erstellt haben.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> -Methode.  Erstellen Sie <xref:System.Windows.Ink.Stroke> eine <xref:System.Windows.Input.StylusPointCollection> neue mit den <xref:System.Windows.Ink.Stroke> Daten, <xref:System.Windows.Controls.InkPresenter.Strokes%2A> und fügen <xref:System.Windows.Controls.InkPresenter>Sie die neue, die Sie der Auflistung der erstellt haben.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>
## <a name="putting-it-together"></a>Zusammenführung  
 Das folgende Beispiel ist ein benutzerdefiniertes Steuerelement, das Tinte sammelt, wenn der Benutzer entweder die Maus oder den Stift verwendet.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Verwenden zusätzlicher Plug-Ins und DynamicRenderer  
 Wie inkCanvas kann auch Ihr <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> benutzerdefiniertes Steuerelement über benutzerdefinierte und zusätzliche <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Objekte verfügen. Fügen Sie <xref:System.Windows.UIElement.StylusPlugIns%2A> diese der Auflistung hinzu. Die Reihenfolge <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> der Objekte <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> im wirkt sich auf die Darstellung der Tinte aus, wenn sie gerendert wird. Angenommen, Sie <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> `dynamicRenderer` haben einen <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> `translatePlugin` aufgerufenen und einen benutzerdefinierten Aufruf, der die Tinte aus dem Tablettstift versetzt. Wenn `translatePlugin` es <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> sich <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>um `dynamicRenderer` die erste in der handelt, und die zweite, wird die Tinte, die "flows" abgibt, versetzt, wenn der Benutzer den Stift verschiebt. Wenn `dynamicRenderer` die erste `translatePlugin` und die zweite ist, wird die Tinte erst versetzt, wenn der Benutzer den Stift anhebt.  
  
<a name="AdvancedInkHandling_Conclusion"></a>
## <a name="conclusion"></a>Zusammenfassung  
 Sie können ein Steuerelement erstellen, das Tinte sammelt und rendert, indem Sie die Eingabestiftereignismethoden überschreiben. Durch das Erstellen eines eigenen Steuerelements, das Ableiten <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>eigener Klassen und das Einfügen der in können Sie praktisch jedes Verhalten implementieren, das mit digitaler Tinte erdenkbar ist. Sie haben Zugriff <xref:System.Windows.Input.StylusPoint> auf die generierten Daten, sodass Sie die Eingabe anpassen <xref:System.Windows.Input.Stylus> und entsprechend ihrer Anwendung auf dem Bildschirm rendern können. Da Sie über einen solchen <xref:System.Windows.Input.StylusPoint> Low-Level-Zugriff auf die Daten verfügen, können Sie die Freihanderfassung implementieren und mit optimaler Leistung für Ihre Anwendung rendern.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweiterte Behandlung von Freihandeingaben](advanced-ink-handling.md)
- [Zugriff auf und Manipulation von Pen-Eingängen](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
