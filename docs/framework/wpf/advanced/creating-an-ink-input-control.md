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
ms.openlocfilehash: b3dc71182b7553a429bb17e1888a4108ceb3e286
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541056"
---
# <a name="creating-an-ink-input-control"></a>Erstellen eines Freihandeingabesteuerelements
Sie können ein benutzerdefiniertes Steuerelement erstellen, die dynamisch und statisch Freihandeingabe gerendert. Freihandeingaben gerendert wird, wenn ein Benutzer ein Strichs zeichnet, verursacht die Freihandeingabe "Datenfluss" aus der Tablettstift, Freihandeingaben nach der er angezeigt wird hinzugefügt und an das Steuerelement entweder über den Tablettstift aus der Zwischenablage eingefügten oder aus einer Datei geladen werden. Um Freihandeingaben dynamisch zu rendern, das Steuerelement verwenden, muss ein <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Um Freihandeingaben statisch zu rendern, müssen Sie den Tablettstiftereignismethoden überschreiben (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, und <xref:System.Windows.UIElement.OnStylusUp%2A>) sammeln <xref:System.Windows.Input.StylusPoint> , Striche zu erstellen und Hinzufügen einer <xref:System.Windows.Controls.InkPresenter> (so wird die Freihandeingabe auf das Steuerelement gerendert wird).  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   [Vorgehensweise: Tablettstift Verwaltungspunkt-Daten zu sammeln und Strichen erstellen](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [Vorgehensweise: Aktivieren Sie das Steuerelement zum Akzeptieren der Mauseingabe](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [Es zusammenstellen](#PuttingItTogether)  
  
-   [Verwenden zusätzliche Plug-ins und DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [Schlussfolgerung](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Vorgehensweise: Tablettstift Verwaltungspunkt-Daten zu sammeln und Strichen erstellen  
 Führen Sie zur Erstellung eines Steuerelements, das erfasst und verwaltet Striche folgende:  
  
1.  Leiten Sie eine Klasse von <xref:System.Windows.Controls.Control> oder eine der Klassen abgeleitet <xref:System.Windows.Controls.Control>, wie z. B. <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  Hinzufügen einer <xref:System.Windows.Controls.InkPresenter> auf die Klasse und den Satz der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft mit dem neuen <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  Anfügen der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> von der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> auf die <xref:System.Windows.Controls.InkPresenter> durch Aufrufen der <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> -Methode, und Hinzufügen der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> auf die <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung. Dies ermöglicht die <xref:System.Windows.Controls.InkPresenter> , um die Freihandeingabe anzuzeigen, wie der Tablettstift-Verwaltungspunkt-Daten vom Steuerelement erfasst werden.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusDown%2A>-Methode.  Erfassen Sie bei dieser Methode den Tablettstift mit einem Aufruf von <xref:System.Windows.Input.Stylus.Capture%2A>. Durch das Erfassen des Tablettstifts an, das Steuerelement wird weiterhin erhalten <xref:System.Windows.UIElement.StylusMove> und <xref:System.Windows.UIElement.StylusUp> Ereignisse, selbst wenn der Tablettstift Grenzen des Steuerelements verlässt. Dies ist nicht zwingend erforderlich, jedoch fast immer für eine gute Benutzeroberfläche gewünschten. Erstellen Sie ein neues <xref:System.Windows.Input.StylusPointCollection> zum Sammeln von <xref:System.Windows.Input.StylusPoint> Daten. Fügen Sie schließlich den anfänglichen Satz von <xref:System.Windows.Input.StylusPoint> Daten an die <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  Überschreiben der <xref:System.Windows.UIElement.OnStylusMove%2A> Methode und Hinzufügen der <xref:System.Windows.Input.StylusPoint> Daten an die <xref:System.Windows.Input.StylusPointCollection> -Objekt, das Sie zuvor erstellt haben.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusUp%2A> Methode und erstellen Sie ein neues <xref:System.Windows.Ink.Stroke> mit der <xref:System.Windows.Input.StylusPointCollection> Daten. Fügen Sie der neuen <xref:System.Windows.Ink.Stroke> Sie erstellt haben, um die <xref:System.Windows.Controls.InkPresenter.Strokes%2A> Auflistung von der <xref:System.Windows.Controls.InkPresenter> und Tablettstift freizugeben.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Vorgehensweise: Aktivieren Sie das Steuerelement zum Akzeptieren der Mauseingabe  
 Wenn Sie das vorherige Steuerelement, um die Anwendung hinzufügen, führen Sie ihn, und verwenden Sie die Maus als Eingabegerät, bemerken Sie, dass die Striche nicht beibehalten werden. Um beizubehalten, gehen die Striche, wenn die Maus als das Eingabegerät, das verwendet wird:  
  
1.  Überschreiben der <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> und erstellen Sie ein neues <xref:System.Windows.Input.StylusPointCollection> rufen Sie die Position der Maus aus, wenn das Ereignis aufgetreten ist, und erstellen Sie eine <xref:System.Windows.Input.StylusPoint> Verwaltungspunkt-Daten und fügen Sie der <xref:System.Windows.Input.StylusPoint> auf der <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A>-Methode. Rufen Sie die Position der Maus aus, wenn das Ereignis aufgetreten ist, und erstellen Sie eine <xref:System.Windows.Input.StylusPoint> die Verwaltungspunkt-Daten verwenden.  Hinzufügen der <xref:System.Windows.Input.StylusPoint> auf die <xref:System.Windows.Input.StylusPointCollection> -Objekt, das Sie zuvor erstellt haben.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>-Methode.  Erstellen Sie ein neues <xref:System.Windows.Ink.Stroke> mit der <xref:System.Windows.Input.StylusPointCollection> Daten, und fügen Sie der neuen <xref:System.Windows.Ink.Stroke> Sie erstellt haben, um die <xref:System.Windows.Controls.InkPresenter.Strokes%2A> Auflistung von der <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>Es zusammenstellen  
 Im folgende Beispiel wird ein benutzerdefiniertes Steuerelement, das Freihandeingaben erfasst, wenn der Benutzer die Maus oder den Stift verwendet.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Verwenden zusätzliche Plug-ins und DynamicRenderers  
 Wie InkCanvas kann das benutzerdefinierte Steuerelement benutzerdefinierte haben <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und zusätzliche <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Objekte. Hinzufügen der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung. Die Reihenfolge der der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Objekte in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> wirkt sich auf die Darstellung der, wenn er gerendert wird. Angenommen, Sie haben eine <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> aufgerufen `dynamicRenderer` und eine benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> aufgerufen `translatePlugin` , die vom Tablettstift Freihandeingaben offsets. Wenn `translatePlugin` ist die erste <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, und `dynamicRenderer` ist die zweite Freihandeingaben, die "übertragen" wird versetzt werden, wenn der Benutzer den Stift bewegt. Wenn `dynamicRenderer` erster und `translatePlugin` ist die zweite Freihandeingaben werden nicht angezeigt, bis der Benutzer den Stift anhebt.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>Schlussbemerkung  
 Sie können ein Steuerelement erstellen, die gesammelt und durch Überschreiben der Tablettstiftereignismethoden Freihandeingabe gerendert. Erstellen Sie ein eigenes Steuerelement ableiten eigene <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klassen und eingefügt werden die in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, können Sie praktisch jeder erdenklichen mit Freihandeingaben Verhalten implementieren. Haben Sie Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten, wie er generiert, mit dem Sie die Möglichkeit zum Anpassen <xref:System.Windows.Input.Stylus> Eingabe- und auf dem Bildschirm nach Bedarf für Ihre Anwendung zu rendern. Schreibberechtigung für diesen Low-Level-Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten, können Sie Freihandeingaben implementieren und mit optimaler Leistung für Ihre Anwendung darstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Behandlung von Freihandeingaben](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [Zugreifen auf und Bearbeiten von Stifteingabe](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
