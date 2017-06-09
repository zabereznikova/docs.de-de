---
title: "Gewusst wie: Festlegen von horizontaler und vertikaler Ausrichtung bei einem TileBrush | Microsoft Docs"
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
  - "Ausrichten, TileBrushes"
  - "Horizontale Ausrichtung von TileBrushes"
  - "TileBrush, Ausrichtung von"
  - "Vertikale Ausrichtung von TileBrushes"
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Festlegen von horizontaler und vertikaler Ausrichtung bei einem TileBrush
In diesem Beispiel wird gezeigt, wie die horizontale und die vertikale Ausrichtung des Inhalts in einer Fläche gesteuert werden.  Sie können die horizontale und vertikale Ausrichtung eines <xref:System.Windows.Media.TileBrush> mithilfe der Eigenschaft <xref:System.Windows.Media.TileBrush.AlignmentX%2A> bzw. <xref:System.Windows.Media.TileBrush.AlignmentY%2A> steuern.  
  
 Die Eigenschaften <xref:System.Windows.Media.TileBrush.AlignmentX%2A> und <xref:System.Windows.Media.TileBrush.AlignmentY%2A> eines <xref:System.Windows.Media.TileBrush>\-Objekts werden verwendet, wenn eine der folgenden Bedingungen erfüllt ist:  
  
-   Die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft ist <xref:System.Windows.Media.Stretch> oder <xref:System.Windows.Media.Stretch>, und die <xref:System.Windows.Media.TileBrush.Viewbox%2A> und der <xref:System.Windows.Media.TileBrush.Viewport%2A> weisen unterschiedliche [Seitenverhältnisse](GTMT) auf.  
  
-   Die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft ist <xref:System.Windows.Media.Stretch>, und <xref:System.Windows.Media.TileBrush.Viewbox%2A> und <xref:System.Windows.Media.TileBrush.Viewport%2A> sind von unterschiedlicher Größe.  
  
## Beispiel  
 Im folgenden Beispiel wird der Inhalt eines <xref:System.Windows.Media.DrawingBrush> \(ein Typ von <xref:System.Windows.Media.TileBrush>\) an der oberen linken Ecke der zugehörigen Fläche ausgerichtet.  Zum Ausrichten des Inhalts wird in dem Beispiel für die <xref:System.Windows.Media.TileBrush.AlignmentX%2A>\-Eigenschaft des <xref:System.Windows.Media.DrawingBrush> die Einstellung <xref:System.Windows.Media.AlignmentX> und für die <xref:System.Windows.Media.TileBrush.AlignmentY%2A>\-Eigenschaft die Einstellung <xref:System.Windows.Media.AlignmentY> festgelegt.  Folgende Ergebnisse werden zurückgegeben:  
  
 ![Ein TileBrush mit oberer linker Ausrichtung](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm\_TileBrushAlignmentExampleTopLeft")  
  
        TileBrush mit an der linken oberen Ecke ausgerichtetem Inhalt  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## Beispiel  
 Im nächsten Beispiel wird der Inhalt eines <xref:System.Windows.Media.DrawingBrush> an der rechten unteren Ecke der zugehörigen Fläche ausgerichtet, indem für die <xref:System.Windows.Media.TileBrush.AlignmentX%2A>\-Eigenschaft die Einstellung <xref:System.Windows.Media.AlignmentX> und für die <xref:System.Windows.Media.TileBrush.AlignmentY%2A>\-Eigenschaft die Einstellung <xref:System.Windows.Media.AlignmentY> festgelegt wird.  Das Beispiel erzeugt folgende Ausgabe.  
  
 ![Ein TileBrush mit unterer rechter Ausrichtung](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm\_TileBrushAlignmentExampleBottomRight")  
  
        TileBrush mit an der rechten unteren Ecke ausgerichtetem Inhalt  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## Beispiel  
 Im nächsten Beispiel wird der Inhalt eines <xref:System.Windows.Media.DrawingBrush> an der linken oberen Ecke der zugehörigen Fläche ausgerichtet, indem für die <xref:System.Windows.Media.TileBrush.AlignmentX%2A>\-Eigenschaft die Einstellung <xref:System.Windows.Media.AlignmentX> und für die <xref:System.Windows.Media.TileBrush.AlignmentY%2A>\-Eigenschaft die Einstellung <xref:System.Windows.Media.AlignmentY> festgelegt wird.  Außerdem werden <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.TileMode%2A> von <xref:System.Windows.Media.DrawingBrush> festgelegt, um ein Flächenmuster zu erzeugen.  Das Beispiel erzeugt folgende Ausgabe.  
  
 ![Ein gekachelter TileBrush mit oberer linker Ausrichtung](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm\_TileBrushAlignmentExampleTopLeftTiled")  
  
        Flächenmuster mit in der Basisfläche oben links ausgerichtetem Inhalt  
  
 In der Abbildung ist eine Basisfläche hervorgehoben, damit Sie sehen können, wie der Inhalt ausgerichtet ist.  Beachten Sie, dass die <xref:System.Windows.Media.TileBrush.AlignmentX%2A>\-Einstellung keine Wirkung hat, da der Inhalt des <xref:System.Windows.Media.DrawingBrush> die Basisfläche horizontal vollständig ausfüllt.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## Beispiel  
 Im letzten Beispiel wird der Inhalt eines in Flächen unterteilten <xref:System.Windows.Media.DrawingBrush> an der rechten unteren Ecke der zugehörigen Basisfläche ausgerichtet, indem für die <xref:System.Windows.Media.TileBrush.AlignmentX%2A>\-Eigenschaft <xref:System.Windows.Media.AlignmentX> und für die <xref:System.Windows.Media.TileBrush.AlignmentY%2A>\-Eigenschaft <xref:System.Windows.Media.AlignmentY> festgelegt wird.  Das Beispiel erzeugt folgende Ausgabe.  
  
 ![Ein gekachelter TileBrush mit unterer rechter Ausrichtung](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm\_TileBrushAlignmentExampleBottomRightTiled")  
  
        Flächenmuster mit in der Basisfläche oben rechts ausgerichtetem Inhalt  
  
 Auch hier hat die <xref:System.Windows.Media.TileBrush.AlignmentX%2A>\-Einstellung keine Wirkung, da der Inhalt des <xref:System.Windows.Media.DrawingBrush> die Basisfläche horizontal vollständig ausfüllt.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 In den Beispielen wird anhand von <xref:System.Windows.Media.DrawingBrush>\-Objekten gezeigt, wie die Eigenschaften <xref:System.Windows.Media.TileBrush.AlignmentX%2A> und <xref:System.Windows.Media.TileBrush.AlignmentY%2A> verwendet werden.  Diese Eigenschaften verhalten sich bei allen TileBrush\-Objekten identisch: <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush> und <xref:System.Windows.Media.VisualBrush>.  Weitere Informationen über TileBrush\-Objekte finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.DrawingBrush>   
 <xref:System.Windows.Media.ImageBrush>   
 <xref:System.Windows.Media.VisualBrush>   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)