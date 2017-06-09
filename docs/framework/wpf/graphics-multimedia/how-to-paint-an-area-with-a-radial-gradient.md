---
title: "Gewusst wie: Zeichnen eines Bereichs mit einem radialen Farbverlauf | Microsoft Docs"
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
  - "Pinsel, Zeichnen mit einem radialen Farbverlauf"
  - "Zeichnen, Mit radialen Farbverläufen"
  - "Radiale Farbverläufe, Zeichnen mit"
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Zeichnen eines Bereichs mit einem radialen Farbverlauf
Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Media.RadialGradientBrush>\-Klasse verwenden, um einen Bereich mit einem radialen Farbverlauf zu zeichnen.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.RadialGradientBrush> verwendet, um ein Rechteck mit einem radialen Farbverlauf zu zeichnen, in dem die Farbe von Gelb in Rot in Blau und in Gelbgrün übergeht.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 Die folgende Abbildung zeigt den Farbverlauf des vorangegangenen Beispiels.  Die Farbverlaufsunterbrechungspunkte wurden hervorgehoben.  
  
 ![Farbverlaufstopps in einem radialen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk\_graphicsmm\_4gradientstops\_rg")  
  
> [!NOTE]
>  In den Beispielen in diesem Thema wird zum Festlegen der Kontrollpunkte das Standardkoordinatensystem verwendet.  Das Standardkoordinatensystem ist relativ zu einem umgebenden Rechteck: 0 gibt 0 Prozent des umgebenden Rechtecks an, und 1 gibt 100 Prozent des umgebenden Rechtecks an.  Sie können dieses Koordinatensystem ändern, indem Sie den Wert der <xref:System.Windows.Media.GradientBrush.MappingMode%2A>\-Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode> festlegen.  Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Rechteck.  Werte werden direkt im lokalen Raum interpretiert.  
  
 Weitere <xref:System.Windows.Media.RadialGradientBrush>\-Beispiele finden Sie unter [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).  Weitere Informationen zu Farbverläufen und anderen Typen von Pinseln finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).