---
title: "Verwenden von DrawingVisual-Objekten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DrawingVisual-Objekte auf visueller Ebene"
  - "Visuelle Ebene, DrawingVisual-Objekte"
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Verwenden von DrawingVisual-Objekten
Dieses Thema bietet einen Überblick über die Verwendung von <xref:System.Windows.Media.DrawingVisual>\-Objekten in der visuellen Ebene von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Dieses Thema enthält folgende Abschnitte.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [DrawingVisual\-Objekt](#drawing_visual_object)  
  
-   [DrawingVisual\-Hostcontainer](#drawingvisual_host_container)  
  
-   [Erstellen von DrawingVisual\-Objekten](#creating_drawingvisual_objects)  
  
-   [Erstellen von Überschreibungen für FrameworkElement\-Member](#creating_overrides)  
  
-   [Bereitstellen von Unterstützung für Treffertests](#providing_hit_testing_support)  
  
-   [Verwandte Themen](#seeAlsoToggle)  
  
<a name="drawingvisual_object"></a>   
## DrawingVisual\-Objekt  
 <xref:System.Windows.Media.DrawingVisual> ist eine einfache Zeichnungsklasse, die verwendet wird, um Formen, Bilder oder Text zu rendern.  Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert.  Aus diesem Grund sind Zeichnungen ideal für Hintergründe und ClipArt.  
  
<a name="drawingvisual_host_container"></a>   
## DrawingVisual\-Hostcontainer  
 Um <xref:System.Windows.Media.DrawingVisual>\-Objekte verwenden zu können, müssen Sie einen Hostcontainer für die Objekte erstellen.  Das Hostcontainerobjekt muss von der <xref:System.Windows.FrameworkElement>\-Klasse abgeleitet werden, die die in der <xref:System.Windows.Media.DrawingVisual>\-Klasse nicht verfügbare Layout\- und Ereignisbehandlungsunterstützung bereitstellt.  Das Hostcontainerobjekt zeigt keine sichtbaren Eigenschaften, da sein Hauptzweck im Aufnehmen untergeordneter Objekte besteht.  Die <xref:System.Windows.UIElement.Visibility%2A>\-Eigenschaft des Hostcontainers muss jedoch auf <xref:System.Windows.Visibility> festgelegt werden. Andernfalls würden die untergeordneten Objekte nicht angezeigt.  
  
 Wenn Sie ein Hostcontainerobjekt für visuelle Objekte erstellen, müssen Sie die Verweise für die visuellen Objekte in einer <xref:System.Windows.Media.VisualCollection> speichern.  Verwenden Sie die <xref:System.Windows.Media.VisualCollection.Add%2A>\-Methode, um dem Hostcontainer ein visuelles Objekt hinzuzufügen.  In dem folgenden Beispiel wird ein Hostcontainerobjekt erstellt, und es werden drei visuelle Objekte zu dessen <xref:System.Windows.Media.VisualCollection> hinzugefügt.  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  Das vollständige Codebeispiel, aus dem das vorangehende Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit "DrawingVisuals"](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## Erstellen von DrawingVisual\-Objekten  
 Wenn Sie ein <xref:System.Windows.Media.DrawingVisual>\-Objekt erstellen, besitzt dieses keinen Zeichnungsinhalt.  Sie können Text\-, Grafik\- oder Bildinhalt hinzufügen, indem Sie den <xref:System.Windows.Media.DrawingContext> des Objekts und die Zeichnung abrufen.  Ein <xref:System.Windows.Media.DrawingContext> wird zurückgegeben, wenn Sie die <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>\-Methode eines <xref:System.Windows.Media.DrawingVisual>\-Objekts aufrufen.  
  
 Um ein Rechteck in den <xref:System.Windows.Media.DrawingContext> zu zeichnen, verwenden Sie die <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A>\-Methode des <xref:System.Windows.Media.DrawingContext>\-Objekts.  Ähnliche Methoden sind auch zum Zeichnen anderer Inhaltstypen verfügbar.  Wenn Sie den Inhalt in den <xref:System.Windows.Media.DrawingContext> gezeichnet haben, rufen Sie die <xref:System.Windows.Media.DrawingContext.Close%2A>\-Methode auf, um den <xref:System.Windows.Media.DrawingContext> zu schließen und den Inhalt beizubehalten.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.DrawingVisual>\-Objekt erstellt, und es wird ein Rechteck in seinen <xref:System.Windows.Media.DrawingContext> gezeichnet.  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## Erstellen von Überschreibungen für FrameworkElement\-Member  
 Das Hostcontainerobjekt verwaltet die zugehörige Auflistung visueller Objekte.  Hierzu muss der Hostcontainer Memberüberschreibungen für die abgeleitete <xref:System.Windows.FrameworkElement>\-Klasse implementieren.  
  
 Die folgende Liste beschreibt die zwei Member, die Sie überschreiben müssen:  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Gibt ein untergeordnetes Element am angegebenen Index aus der Auflistung der untergeordneten Elemente zurück.  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Ruft die Anzahl visueller untergeordneter Elemente innerhalb dieses Elements ab.  
  
 Im folgenden Beispiel werden Überschreibungen für die zwei <xref:System.Windows.FrameworkElement>\-Member implementiert.  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## Bereitstellen von Unterstützung für Treffertests  
 Das Hostcontainerobjekt ermöglicht eine Ereignisbehandlung, auch wenn keine sichtbaren Eigenschaften angezeigt werden. Hierzu muss jedoch die <xref:System.Windows.UIElement.Visibility%2A>\-Eigenschaft auf <xref:System.Windows.Visibility> festgelegt sein.  Sie können so eine Ereignisbehandlungsroutine für den Hostcontainer erstellen, durch die Mausereignisse erfasst werden, z. B. das Loslassen der linken Maustaste.  Die Ereignisbehandlungsroutine kann dann Treffertests implementieren, indem sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>\-Methode aufruft.  Der <xref:System.Windows.Media.HitTestResultCallback>\-Parameter der Methode bezieht sich auf eine benutzerdefinierte Prozedur, mit der Sie die resultierende Aktion für einen Treffertest bestimmen können.  
  
 Im folgenden Beispiel wird die Unterstützung für Treffertests für das Hostcontainerobjekt und die untergeordneten Elemente implementiert.  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## Siehe auch  
 <xref:System.Windows.Media.DrawingVisual>   
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>   
 [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)