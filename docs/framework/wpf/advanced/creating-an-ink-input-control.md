---
title: "Erstellen eines Freihandeingabesteuerelements | Microsoft Docs"
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
  - "Erfassen von Freihandeingabestrichen"
  - "DynamicRenderer-Objekte"
  - "Freihandeingabesteuerelement"
  - "Freihandeingabestriche, Erfassen"
  - "Freihandeingabestriche, Verwalten"
  - "Freihandeingaben, Rendering"
  - "Mauseingabe, Annehmen"
  - "Vewalten von Freihandeingabestrichen"
  - "Mauseingabe, Annehmen"
  - "Rendern von Freihandeingaben"
  - "StylusPlugIn-Objekte"
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Erstellen eines Freihandeingabesteuerelements
Sie können ein benutzerdefiniertes Steuerelement erstellen, das Freihandeingaben dynamisch und statisch rendert.  Das bedeutet, dass die Eingabe gerendert wird, während der Benutzer einen Strich zieht, sodass der Stift den Strich scheinbar zeichnet. Außerdem wird die Eingabe angezeigt, nachdem sie dem Steuerelement per Tablettstift, durch Einfügen aus der Zwischenablage oder durch Laden aus einer Datei hinzugefügt wurde.  Das Steuerelement muss <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> verwenden, um Freihandeingaben dynamisch zu rendern.  Zum statischen Rendern von Freihandeingaben müssen die Tablettstiftereignismethoden \(<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A> und <xref:System.Windows.UIElement.OnStylusUp%2A>\) überschrieben werden, um <xref:System.Windows.Input.StylusPoint>\-Daten zu erfassen, Striche zu erstellen und sie dem <xref:System.Windows.Controls.InkPresenter> \(zum Rendern der Freihandeingabe auf dem Steuerelement\) hinzuzufügen.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   [Gewusst wie: Erfassen von Tablettstift-Punktdaten und Erstellen von Freihandstrichen](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [Gewusst wie: Aktivieren der Mauseingabe für das Steuerelement](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [Die Komponenten im Zusammenhang](#PuttingItTogether)  
  
-   [Verwenden von zusätzlichen Plug-Ins und DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [Schlussfolgerung](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## Gewusst wie: Erfassen von Tablettstift\-Punktdaten und Erstellen von Freihandstrichen  
 So erstellen Sie ein Steuerelement, das Freihandstriche erfasst und verwaltet  
  
1.  Leiten Sie eine Klasse von <xref:System.Windows.Controls.Control> oder einer der Klassen ab, die von <xref:System.Windows.Controls.Control>, z. B. <xref:System.Windows.Controls.Label>, abgeleitet werden.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  Fügen Sie der Klasse <xref:System.Windows.Controls.InkPresenter> hinzu, und legen Sie die <xref:System.Windows.Controls.ContentControl.Content%2A>\-Eigenschaft auf den neuen <xref:System.Windows.Controls.InkPresenter> fest.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  Fügen Sie <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> von <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> dem <xref:System.Windows.Controls.InkPresenter> hinzu, indem Sie die <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A>\-Methode aufrufen und <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> der <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Sammlung hinzufügen.  Dies ermöglicht <xref:System.Windows.Controls.InkPresenter> das Anzeigen der Freihandeingaben, während die Tablettstift\-Punktdaten vom Steuerelement erfasst werden.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusDown%2A>\-Methode.  Erfassen Sie in dieser Methode den Tablettstift durch einen Aufruf von <xref:System.Windows.Input.Stylus.Capture%2A>.  Durch das Erfassen des Tablettstifts empfängt das Steuerelement auch dann <xref:System.Windows.UIElement.StylusMove>\- und <xref:System.Windows.UIElement.StylusUp>\-Ereignisse, wenn der Tablettstift außerhalb der Begrenzung des Steuerelements verwendet wird.  Dies ist zwar nicht notwendig, wird jedoch im Hinblick auf die Benutzerfreundlichkeit empfohlen.  Erstellen Sie eine neue <xref:System.Windows.Input.StylusPointCollection>, um <xref:System.Windows.Input.StylusPoint>\-Daten zu erfassen.  Fügen Sie schließlich den Anfangssatz der <xref:System.Windows.Input.StylusPoint>\-Daten der <xref:System.Windows.Input.StylusPointCollection> hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusMove%2A>\-Methode, und fügen Sie die <xref:System.Windows.Input.StylusPoint>\-Daten dem bereits erstellten <xref:System.Windows.Input.StylusPointCollection>\-Objekt hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  Überschreiben Sie die <xref:System.Windows.UIElement.OnStylusUp%2A>\-Methode, und erstellen Sie einen neuen <xref:System.Windows.Ink.Stroke> mithilfe der <xref:System.Windows.Input.StylusPointCollection>\-Daten.  Fügen Sie den neu erstellten <xref:System.Windows.Ink.Stroke> der <xref:System.Windows.Controls.InkPresenter.Strokes%2A>\-Auflistung von <xref:System.Windows.Controls.InkPresenter> hinzu, und heben Sie die Erfassung des Tablettstifts auf.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## Gewusst wie: Aktivieren der Mauseingabe für das Steuerelement  
 Wenn Sie der Anwendung das vorherige Steuerelement hinzufügen, diese ausführen und die Maus als Eingabegerät verwenden, werden die Striche nicht beibehalten.  So behalten Sie die mit einer Maus eingegebenen Striche bei  
  
1.  Überschreiben Sie <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A>, und erstellen Sie eine neue <xref:System.Windows.Input.StylusPointCollection>. Rufen Sie die Mausposition zum Zeitpunkt des Auftretens des Ereignisses ab, und erstellen Sie mithilfe der Punktdaten einen <xref:System.Windows.Input.StylusPoint>. Fügen Sie dann den <xref:System.Windows.Input.StylusPoint>zur <xref:System.Windows.Input.StylusPointCollection> hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A>\-Methode.  Rufen Sie die Mausposition zu dem Zeitpunkt ab, als das Ereignis aufgetreten ist, und erstellen Sie mithilfe der Punktdaten einen <xref:System.Windows.Input.StylusPoint>.  Fügen Sie den <xref:System.Windows.Input.StylusPoint> dem bereits erstellten <xref:System.Windows.Input.StylusPointCollection>\-Objekt  hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  Überschreiben Sie die <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>\-Methode.  Erstellen Sie einen neuen <xref:System.Windows.Ink.Stroke> mithilfe der <xref:System.Windows.Input.StylusPointCollection>\-Daten. Fügen Sie den neu erstellten <xref:System.Windows.Ink.Stroke> der <xref:System.Windows.Controls.InkPresenter.Strokes%2A>\-Auflistung des <xref:System.Windows.Controls.InkPresenter> hinzu.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## Die Komponenten im Zusammenhang  
 Das folgende Beispiel enthält ein benutzerdefiniertes Steuerelement, das Freihandeingaben erfasst, die Benutzer mit der Maus oder dem Tablettstift eingeben.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## Verwenden von zusätzlichen Plug\-Ins und DynamicRenderers  
 Wie InkCanvas kann das benutzerdefinierte Steuerelement über benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und zusätzliche <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>\-Objekte verfügen.  Fügen Sie diese der <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Auflistung hinzu.  Die Reihenfolge der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>\-Objekte in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> wirkt sich auf die Anzeige der gerenderten Feihandeingaben aus.  Angenommen, Sie verfügen über einen <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> mit dem Namen `dynamicRenderer` und über ein benutzerdefiniertes <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> mit dem Namen `translatePlugin`, das den Offset der Freihandeingabe vom Tablettstift berechnet.  Wenn `translatePlugin` das erste <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> in der <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> ist und `dynamicRenderer` an zweiter Stelle steht, wird der Offset der Freihandeingabe berechnet, während der Benutzer den Stift bewegt.  Wenn `dynamicRenderer` in der Reihenfolge an erster Stelle und `translatePlugin` an zweiter Stelle steht, wird der Offset der Freihandeingabe erst berechnet, wenn der Benutzer den Stift anhebt.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## Schlussfolgerung  
 Sie können ein Steuerelement, das Freihandeingaben erfasst und rendert, durch Überschreiben der Tablettstiftereignis\-Methoden erstellen.  Wenn Sie ein benutzerdefiniertes Steuerelement erstellen, eigene <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>\-Klassen ableiten und in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> einfügen, können Sie praktisch jedes Verhalten bezüglich Freihandeingaben implementieren.  Sie können auf die <xref:System.Windows.Input.StylusPoint>\-Daten zugreifen, während sie erstellt werden. So können Sie <xref:System.Windows.Input.Stylus>\-Eingaben anpassen und Ihrer Anwendung entsprechend auf dem Bildschirm rendern.  Durch diesen Low\-Level\-Zugriff auf die <xref:System.Windows.Input.StylusPoint>\-Daten können Sie das Erfassen und Rendern von Freihandeingaben mit optimaler Leistung für Ihre Anwendung implementieren.  
  
## Siehe auch  
 [Erweiterte Behandlung von Freihandeingaben](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)   
 [Zugriff auf Stifteingaben und Bearbeiten von Stifteingaben](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)