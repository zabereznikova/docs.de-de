---
title: "Gewusst wie: Beibehalten des Seitenverh&#228;ltnisses bei einem als Hintergrund verwendeten Bild | Microsoft Docs"
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
  - "Seitenverhältnis von Hintergrundbildern, Beibehalten"
  - "Hintergrundbilder, Beibehalten des Seitenverhältnisses"
  - "Pinsel, Beibehalten der Seitenverhältnisse von Hintergrundbildern"
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Beibehalten des Seitenverh&#228;ltnisses bei einem als Hintergrund verwendeten Bild
In diesem Beispiel wird gezeigt, wie mithilfe der <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft eines <xref:System.Windows.Media.ImageBrush>\-Objekts das [Seitenverhältnis](GTMT) eines Bildes beibehalten wird.  
  
 Wenn Sie mit einem <xref:System.Windows.Media.ImageBrush> einen Bereich zeichnen, wird dessen Inhalt standardmäßig so gestreckt, dass er den Ausgabebereich vollständig ausfüllt.  Wenn der Ausgabebereich und das Bild unterschiedliche [Seitenverhältnisse](GTMT) aufweisen, wird das Bild durch dieses Strecken verzerrt.  
  
 Damit ein <xref:System.Windows.Media.ImageBrush> das Seitenverhältnis beibehält, müssen Sie für die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft <xref:System.Windows.Media.Stretch> oder <xref:System.Windows.Media.Stretch> festlegen.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Media.ImageBrush>\-Objekte verwendet, um zwei Rechtecke zu zeichnen.  Jedes Rechteck ist 300 x 150 [Pixel](GTMT) groß und enthält jeweils ein 300 x 300 Pixel großes Bild.  Für die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft des ersten Pinsels wird <xref:System.Windows.Media.Stretch> und für die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft des zweiten Pinsels <xref:System.Windows.Media.Stretch> festgelegt.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Die folgende Abbildung zeigt die Ausgabe des ersten Pinsels, bei dem für <xref:System.Windows.Media.TileBrush.Stretch%2A> der Wert <xref:System.Windows.Media.Stretch> festgelegt ist.  
  
 ![ImageBrush mit Uniform&#45;Dehnung](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.png "graphicsmm\_ImageBrushUniformStretch")  
  
 Die nächste Abbildung zeigt die Ausgabe des zweiten Pinsels, bei dem für <xref:System.Windows.Media.TileBrush.Stretch%2A> der Wert <xref:System.Windows.Media.Stretch> festgelegt ist.  
  
 ![ImageBrush mit UniformToFill&#45;Dehnung](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.png "graphicsmm\_ImageBrushUniformToFillStretch")  
  
 Beachten Sie, dass sich die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft bei den anderen <xref:System.Windows.Media.TileBrush>\-Objekten \(d.h. <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>\) genauso verhält.  Weitere Informationen über <xref:System.Windows.Media.ImageBrush> und die anderen <xref:System.Windows.Media.TileBrush>\-Objekte finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Beachten Sie auch, dass die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft zwar anzugeben scheint, wie der <xref:System.Windows.Media.TileBrush>\-Inhalt gestreckt wird, damit er in den Ausgabebereich passt, dass sie tatsächlich aber angibt, wie der <xref:System.Windows.Media.TileBrush>\-Inhalt gestreckt wird, damit er die Basisfläche ausfüllt.  Weitere Informationen finden Sie unter <xref:System.Windows.Media.TileBrush>.  
  
 Dieses Codebeispiel ist Teil eines umfangreicheren Beispiels für die <xref:System.Windows.Media.ImageBrush>\-Klasse.  Das vollständige Beispiel finden Sie unter [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## Siehe auch  
 <xref:System.Windows.Media.TileBrush>   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)