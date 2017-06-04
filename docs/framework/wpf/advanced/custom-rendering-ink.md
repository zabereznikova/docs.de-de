---
title: "Benutzerdefiniertes Rendern von Freihandeingaben | Microsoft Docs"
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
  - "Klassen, DynamicRenderer"
  - "Klassen, InkCanvas"
  - "Klassen, Strich"
  - "Freihandeingaben durch benutzerdefiniertes Rendern"
  - "DynamicRenderer-Klasse"
  - "Freihandeingaben, Benutzerdefiniertes Rendering"
  - "InkCanvas-Klasse"
  - "Stroke-Klasse"
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Benutzerdefiniertes Rendern von Freihandeingaben
Die <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>\-Eigenschaft eines Strichs gestattet Ihnen, die Darstellung des Strichs anzugeben, z. B. die Größe, Farbe und Form. Es gibt jedoch möglicherweise Situationen, in denen Sie die Darstellung über die Möglichkeiten von <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> hinausgehend anpassen möchten.  Möglicherweise möchten Sie die Darstellung der Freihandzeichnung so anpassen, dass sie wie ein Airbrush\- oder Ölfarbebild aussieht oder mit einem von vielen anderen Effekten gerendert wird.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] ermöglicht Ihnen, Freihandzeichnungen benutzerdefiniert zu rendern, indem Sie ein benutzerdefiniertes <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>\-Objekt und <xref:System.Windows.Ink.Stroke>\-Objekt implementieren.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   [Architektur](#Architecture)  
  
-   [Implementieren eines dynamischen Renderers](#ImplementingADynamicRenderer)  
  
-   [Implementing a Custom Stroke](#ImplementingACustomStroke)  
  
-   [Implementieren eines benutzerdefinierten InkCanvas](#ImplementingACustomInkCanvas)  
  
-   [Schlussfolgerung](#Conclusion)  
  
<a name="Architecture"></a>   
## Architektur  
 Freihandrendering erfolgt zweimal: einmal, wenn ein Benutzer auf einer Freihandoberfläche schreibt, und ein zweites Mal, nachdem der Strich der freihandfähigen Oberfläche hinzugefügt wurde.  Der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> rendert die Freihandeingabe, wenn der Benutzer den Tablettstift auf dem Digitizer verschiebt, und der <xref:System.Windows.Ink.Stroke> rendert sich selbst, sobald er einem Element hinzugefügt wird.  
  
 Beim dynamischen Rendern von Freihandeingaben sind drei Klassen zu implementieren.  
  
1.  **DynamicRenderer**: Implementieren Sie eine Klasse, die sich von <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> ableitet.  Diese Klasse ist ein spezielles <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, das den Strich beim Zeichnen rendert.  Der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> führt das Rendern in einem separaten Thread aus, sodass die Freihandoberfläche scheinbar Eingaben entgegennimmt, auch wenn der Thread der Anwendungsbenutzeroberfläche blockiert ist.  Weitere Informationen zum Threadmodell finden Sie unter [Das Threadmodell für Freihandeingaben](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  Um das dynamische Rendern eines Strichs anzupassen, überschreiben Sie die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>\-Methode.  
  
2.  **Stroke**: Implementieren Sie eine Klasse, die sich von <xref:System.Windows.Ink.Stroke> ableitet.  Diese Klasse ist für das statische Rendern der <xref:System.Windows.Input.StylusPoint>\-Daten verantwortlich, nachdem sie in ein <xref:System.Windows.Ink.Stroke>\-Objekt konvertiert wurden.  Überschreiben Sie die <xref:System.Windows.Ink.Stroke.DrawCore%2A>\-Methode, um sicherzustellen, dass das statische Rendern des Strichs und das dynamische Rendern konsistent sind.  
  
3.  **InkCanvas:** Implementieren Sie eine Klasse, die sich von <xref:System.Windows.Controls.InkCanvas> ableitet.  Weisen Sie den benutzerdefinierten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> der <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>\-Eigenschaft zu.  Überschreiben Sie die <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>\-Methode, und fügen Sie der <xref:System.Windows.Controls.InkCanvas.Strokes%2A>\-Eigenschaft einen benutzerdefinierten Strich hinzu.  Dadurch wird sichergestellt, dass die Darstellung der Freihandeingaben konsistent ist.  
  
<a name="ImplementingADynamicRenderer"></a>   
## Implementieren eines dynamischen Renderers  
 Zwar gehört die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>\-Klasse zum Standardumfang von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], um spezialisierteres Rendern auszuführen, müssen Sie jedoch einen benutzerdefinierten dynamischen Renderer erstellen, der vom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> abgeleitet ist, und die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>\-Methode überschreiben.  
  
 Im folgenden Beispiel wird ein angepasster <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> veranschaulicht, der Freihandeingaben mit einem Pinsel mit linearem Farbverlaufeffekt zeichnet.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## Implementieren von benutzerdefinierten Strichen  
 Implementieren Sie eine Klasse, die von <xref:System.Windows.Ink.Stroke> abgeleitet ist.  Diese Klasse ist für das Rendern von <xref:System.Windows.Input.StylusPoint>\-Daten verantwortlich, nachdem sie in ein <xref:System.Windows.Ink.Stroke>\-Objekt konvertiert wurden.  Überschreiben Sie die <xref:System.Windows.Ink.Stroke.DrawCore%2A>\-Klasse, um den eigentlichen Zeichnungsvorgang auszuführen.  
  
 Die Stroke\-Klasse kann mithilfe der <xref:System.Windows.Ink.Stroke.AddPropertyData%2A>\-Methode auch benutzerdefinierte Daten speichern.  Diese Daten werden beim dauerhaften Speichern zusammen mit den Strichdaten gespeichert.  
  
 Die <xref:System.Windows.Ink.Stroke>\-Klasse kann auch Trefferüberprüfungen ausführen.  Sie können auch eigene Trefferüberprüfungsalgorithmen implementieren, indem Sie die <xref:System.Windows.Ink.Stroke.HitTest%2A>\-Methode in der aktuellen Klasse überschreiben.  
  
 Im folgenden C\#\-Code wird eine benutzerdefinierte <xref:System.Windows.Ink.Stroke>\-Klasse veranschaulicht, die <xref:System.Windows.Input.StylusPoint>\-Daten als 3D\-Strich rendert.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## Implementieren eines benutzerdefinierten InkCanvas  
 Die einfachste Art, einen benutzerdefinierten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> und Strich zu verwenden, besteht im Implementieren einer Klasse, die von <xref:System.Windows.Controls.InkCanvas> abgeleitetet ist und diese Klassen verwendet.  <xref:System.Windows.Controls.InkCanvas> verfügt über eine <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>\-Eigenschaft, die angibt, wie der Strich beim Zeichnen durch den Benutzer gerendert wird.  
  
 Gehen Sie wie folgt vor, um das Rendern von Strichen auf einem <xref:System.Windows.Controls.InkCanvas> anzupassen:  
  
-   Erstellen Sie eine von der <xref:System.Windows.Controls.InkCanvas>\-Klasse abgeleitete Klasse.  
  
-   Weisen Sie den benutzerdefinierten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> der <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=fullName>\-Eigenschaft zu.  
  
-   Überschreiben Sie die <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>\-Methode.  Entfernen Sie in dieser Methode den ursprünglichen Strich, der dem InkCanvas hinzugefügt wurde.  Erstellen Sie dann einen benutzerdefinierten Strich, fügen Sie ihn der <xref:System.Windows.Controls.InkCanvas.Strokes%2A>\-Eigenschaft hinzu, und rufen Sie die Basisklasse mit einer neuen <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs>\-Klasse auf, die den benutzerdefinierten Strich enthält.  
  
 Im folgenden C\#\-Code wird eine benutzerdefinierte <xref:System.Windows.Controls.InkCanvas>\-Klasse veranschaulicht, die einen angepassten <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> verwendet und benutzerdefinierte Striche erfasst.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Ein <xref:System.Windows.Controls.InkCanvas> kann über mehrere <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> verfügen.  Sie können mehrere <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>\-Objekte dem <xref:System.Windows.Controls.InkCanvas> hinzufügen, indem Sie sie der <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Eigenschaft hinzufügen.  
  
<a name="Conclusion"></a>   
## Schlussfolgerung  
 Sie können die Darstellung von Freihandeingaben anpassen, indem Sie eigene <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>\-, <xref:System.Windows.Ink.Stroke>\- und <xref:System.Windows.Controls.InkCanvas>\-Klassen ableiten.  Zusammen stellen diese Klassen sicher, dass die Darstellung des Strichs beim Zeichnen durch den Benutzer und nach dem Erfassen konsistent ist.  
  
## Siehe auch  
 [Erweiterte Behandlung von Freihandeingaben](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)