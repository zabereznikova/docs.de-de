---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem linearen Farbverlauf'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dcc37651d6f1f304f15d3244c2504517a2a9fb76
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Gewusst wie: Zeichnen eines Bereichs mit einem linearen Farbverlauf
Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.LinearGradientBrush> Klasse, um einen Bereich mit einem linearen Farbverlauf zu zeichnen. Im folgenden Beispiel die <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle> mit einer diagonalen linearen Farbverlauf, der von Gelb zu Rot Blau Gelbgrün übergeht gezeichnet wird.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.  
  
 ![Diagonaler, linearer Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "Graphicsmm_DiagonalLGB")  
  
 Um einen horizontalen linearen Farbverlauf erstellen, Ändern der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> von der <xref:System.Windows.Media.LinearGradientBrush> in (0,0.5) und (1,0.5 ändern). Im folgenden Beispiel eine <xref:System.Windows.Shapes.Rectangle> mit einem horizontalen linearen Farbverlauf gezeichnet wird.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.  
  
 ![Einen horizontalen linearen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "Graphicsmm_HorizontalLGB")  
  
 Um ein vertikaler, linearer Farbverlauf zu erstellen, Ändern der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> von der <xref:System.Windows.Media.LinearGradientBrush> in (0.5,0) und (0.5,1 ändern). Im folgenden Beispiel eine <xref:System.Windows.Shapes.Rectangle> mit vertikaler, linearer Farbverlauf gezeichnet wird.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.  
  
 ![Vertikaler, linearer Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "Graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  In den Beispielen in diesem Thema werden die Standard-Koordinatensystem zum Festlegen von Anfangs- und Endpunkte verwenden. Der Standard-Koordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds und 1 gibt 100 Prozent des umgebenden Felds an. Sie können dieses Koordinatensystems ändern, durch Festlegen der <xref:System.Windows.Media.GradientBrush.MappingMode%2A> -Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>. Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld. Werte werden direkt im lokalen Raum interpretiert.  
  
 Weitere Beispiele finden Sie unter [Pinsel Beispiel](http://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen zu Farbverläufen und anderen Typen von Pinseln finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).
