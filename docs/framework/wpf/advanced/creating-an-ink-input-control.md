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
ms.openlocfilehash: 329bad9d5e0fa24f66fbd63def4936cb047e62e3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378066"
---
# <a name="creating-an-ink-input-control"></a>Erstellen eines Freihandeingabesteuerelements
Sie können ein benutzerdefiniertes Steuerelement erstellen, die dynamisch und statisch rendert Freihandeingaben. Freihandeingaben gerendert wird, wenn ein Benutzer ein Strichs zeichnet, wodurch die Freihandeingaben angezeigt werden, "flow" aus der Tablettstift und Freihandeingaben dahinter angezeigt wurde an das Steuerelement, entweder über den Tablettstift aus der Zwischenablage eingefügten oder aus einer Datei geladen. Zum Rendern von Freihandeingaben dynamisch das Steuerelement verwenden, muss ein <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Zum Rendern von Freihandeingaben statisch, müssen Sie den Stift-Event-Methoden überschreiben (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, und <xref:System.Windows.UIElement.OnStylusUp%2A>) zum Sammeln von <xref:System.Windows.Input.StylusPoint> , Striche zu erstellen, und fügen sie eine <xref:System.Windows.Controls.InkPresenter> (die rendert Freihandeingaben auf dem Steuerelement).  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   [Vorgehensweise: Stift-Verwaltungspunkt-Daten sammeln und zum Erstellen von Freihandstrichen](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [Vorgehensweise: Aktivieren Sie das Steuerelement Benutzereingaben von der Maus](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [Letzte Schritte](#PuttingItTogether)  
  
-   [Verwenden zusätzliche Plug-ins und DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [Schlussfolgerung](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Vorgehensweise: Stift-Verwaltungspunkt-Daten sammeln und zum Erstellen von Freihandstrichen  
 Führen Sie zum Erstellen eines Steuerelements, das erfasst und verwaltet Striche folgende:  
  
1.  Leiten Sie eine Klasse von <xref:System.Windows.Controls.Control> oder eine der Klassen abgeleitet <xref:System.Windows.Controls.Control>, z. B. <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  Hinzufügen einer <xref:System.Windows.Controls.InkPresenter> auf die Klasse und den Satz der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft mit dem neuen <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  Anfügen der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> von der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> zu der <xref:System.Windows.Controls.InkPresenter> durch Aufrufen der <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> -Methode, und fügen die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> auf der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung. Dadurch wird die <xref:System.Windows.Controls.InkPresenter> um Freihandeingaben anzuzeigen. wenn der Tablettstift-Verwaltungspunkt-Daten vom Steuerelement erfasst werden.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusDown%2A> -Methode.  Erfassen Sie bei dieser Methode den Tablettstift mit einem Aufruf von <xref:System.Windows.Input.Stylus.Capture%2A>. Durch das Erfassen der Stift, wird das Steuerelement weiter empfangen <xref:System.Windows.UIElement.StylusMove> und <xref:System.Windows.UIElement.StylusUp> Ereignisse, selbst wenn der Stift des Steuerelements-Grenzen verlässt. Dies ist nicht unbedingt erforderlich, aber fast immer gewünschten für eine gute benutzererfahrung. Erstellen Sie ein neues <xref:System.Windows.Input.StylusPointCollection> zum Sammeln von <xref:System.Windows.Input.StylusPoint> Daten. Fügen Sie abschließend den anfänglichen Satz von <xref:System.Windows.Input.StylusPoint> Daten an die <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  Überschreiben der <xref:System.Windows.UIElement.OnStylusMove%2A> Methode und Hinzufügen der <xref:System.Windows.Input.StylusPoint> Daten an die <xref:System.Windows.Input.StylusPointCollection> -Objekt, das Sie zuvor erstellt haben.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  Überschreiben der <xref:System.Windows.UIElement.OnStylusUp%2A> Methode, und erstellen Sie ein neues <xref:System.Windows.Ink.Stroke> mit der <xref:System.Windows.Input.StylusPointCollection> Daten. Hinzufügen des neuen <xref:System.Windows.Ink.Stroke> Sie erstellt haben, um die <xref:System.Windows.Controls.InkPresenter.Strokes%2A> Auflistung von der <xref:System.Windows.Controls.InkPresenter> und Freigeben von Tablettstifteingaben erfasst.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Vorgehensweise: Aktivieren Sie das Steuerelement Benutzereingaben von der Maus  
 Wenn Sie das vorherige Steuerelement zu Ihrer Anwendung hinzufügen, führen Sie es, und verwenden Sie die Maus als Eingabegerät, bemerken Sie, dass die Striche nicht beibehalten werden. Um beizubehalten gehen die Striche, wenn der Mauszeiger als das Eingabegerät verwendet wird:  
  
1.  Außer Kraft setzen der <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> und erstellen Sie ein neues <xref:System.Windows.Input.StylusPointCollection> erhalten Sie die Position der Maus aus, wenn das Ereignis aufgetreten ist, und erstellen Sie eine <xref:System.Windows.Input.StylusPoint> mit dem Verwaltungspunkt-Daten, und fügen die <xref:System.Windows.Input.StylusPoint> auf die <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> -Methode. Die Position der Maus zu erhalten, wenn das Ereignis aufgetreten ist, und erstellen Sie eine <xref:System.Windows.Input.StylusPoint> mithilfe der Point-Daten.  Hinzufügen der <xref:System.Windows.Input.StylusPoint> auf die <xref:System.Windows.Input.StylusPointCollection> -Objekt, das Sie zuvor erstellt haben.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> -Methode.  Erstellen Sie ein neues <xref:System.Windows.Ink.Stroke> mit der <xref:System.Windows.Input.StylusPointCollection> Daten, und fügen Sie der neuen <xref:System.Windows.Ink.Stroke> Sie erstellt haben, um die <xref:System.Windows.Controls.InkPresenter.Strokes%2A> Auflistung von der <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>Letzte Schritte  
 Im folgende Beispiel wird ein benutzerdefiniertes Steuerelement, das Freihandeingaben erfasst, wenn der Benutzer entweder der Maus oder der Stift verwendet.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Verwenden zusätzliche Plug-ins und DynamicRenderers  
 Das benutzerdefinierte Steuerelement haben wie InkCanvas benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und zusätzliche <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Objekte. Hinzufügen der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung. Die Reihenfolge der der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Objekte in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> wirkt sich auf die Darstellung der Freihandeingaben, wenn er gerendert wird. Angenommen, Sie haben eine <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> namens `dynamicRenderer` und eine benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> namens `translatePlugin` , die offsets der Freihand auf der Tablettstift. Wenn `translatePlugin` ist der erste <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, und `dynamicRenderer` ist die zweite, wenn der Benutzer den Stift bewegt die Freihandeingabe, die "flows" versetzt werden. Wenn `dynamicRenderer` wird zuerst und `translatePlugin` ist die zweite Freihandeingaben nicht versetzt werden, bis der Benutzer den Stift anhebt.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>Schlussbemerkung  
 Sie können ein Steuerelement erstellen, die erfasst und rendert Freihandeingaben durch Überschreiben der Methoden der Tablettstift-Ereignis. Erstellen eines eigenen Steuerelements, ableiten eigene <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klassen und eingefügt werden die in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, können Sie praktisch jeder erdenklichen mit Freihandeingaben Verhalten implementieren. Sie haben Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten generiert, haben Sie die Möglichkeit zum Anpassen <xref:System.Windows.Input.Stylus> eingeben und auf dem Bildschirm nach Bedarf für Ihre Anwendung zu rendern. Da Sie diese auf niedriger Ebene Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten, können Sie Freihandeingaben implementieren und mit optimaler Leistung für Ihre Anwendung rendern.  
  
## <a name="see-also"></a>Siehe auch
- [Erweiterte Behandlung von Freihandeingaben](advanced-ink-handling.md)
- [Zugreifen auf und Bearbeiten von Stifteingabe](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
