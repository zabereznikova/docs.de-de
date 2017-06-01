---
title: "Gewusst wie: Zeichnen eines Bereichs mit einem linearen Farbverlauf | Microsoft Docs"
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
  - "Pinsel, Zeichnen mit einem linearen Farbverlauf"
  - "Lineare Farbverläufe, Zeichnen mit"
  - "Zeichnen, Mit linearen Farbverläufen"
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Zeichnen eines Bereichs mit einem linearen Farbverlauf
In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Windows.Media.LinearGradientBrush>\-Klasse ein Bereich mit einem linearen Farbverlauf gezeichnet wird.  In dem folgenden Beispiel wird die <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle> mit einem diagonalen linearen Farbverlauf gezeichnet, der sich von Gelb über Rot und Blau in Gelbgrün ändert.  
  
## Beispiel  
 [!code-xml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 In der folgenden Abbildung wird der im vorherigen Beispiel erstellte Farbverlauf dargestellt.  
  
 ![Diagonaler, linearer Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.png "graphicsmm\_DiagonalLGB")  
  
 Einen horizontalen linearen Farbverlauf erstellen Sie, indem Sie den <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> für das <xref:System.Windows.Media.LinearGradientBrush>\-Element in \(0,0.5\) und \(1,0.5\) ändern.  In dem folgenden Beispiel wird ein <xref:System.Windows.Shapes.Rectangle>\-Element mit einem horizontalen linearen Farbverlauf gezeichnet.  
  
 [!code-xml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 In der folgenden Abbildung wird der im vorherigen Beispiel erstellte Farbverlauf dargestellt.  
  
 ![Ein horizontaler, linearer Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.png "graphicsmm\_HorizontalLGB")  
  
 Einen vertikalen linearen Farbverlauf erstellen Sie, indem Sie den <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> für das <xref:System.Windows.Media.LinearGradientBrush>\-Element in \(0.5,0\) und \(0.5,1\) ändern.  In dem folgenden Beispiel wird ein <xref:System.Windows.Shapes.Rectangle>\-Element mit einem vertikalen linearen Farbverlauf gezeichnet.  
  
 [!code-xml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 In der folgenden Abbildung wird der im vorherigen Beispiel erstellte Farbverlauf dargestellt.  
  
 ![Vertikaler, linearer Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.png "graphicsmm\_VerticalLGB")  
  
> [!NOTE]
>  Die Beispiele in diesem Thema verwenden das Standardkoordinatensystem zum Festlegen von Startpunkten und Endpunkten.  Das Standardkoordinatensystem ist relativ zu einem umgebenden Rechteck: 0 gibt 0 Prozent des umgebenden Rechtecks an, und 1 gibt 100 Prozent des umgebenden Rechtecks an.  Sie können dieses Koordinatensystem ändern, indem Sie den Wert der <xref:System.Windows.Media.GradientBrush.MappingMode%2A>\-Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode?displayProperty=fullName> festlegen.  Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Rechteck.  Werte werden direkt im lokalen Raum interpretiert.  
  
 Weitere Beispiele finden Sie unter [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).  Weitere Informationen zu Farbverläufen und anderen Typen von Pinseln finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).