---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einem linearen Farbverlauf'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 92c9ccd846dbbce043d13e6ba82b9fa8e72fa8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916163"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Vorgehensweise: Zeichnen eines Bereichs mit einem linearen Farbverlauf
In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Media.LinearGradientBrush> die-Klasse verwendet wird, um einen Bereich mit einem linearen Farbverlauf zu zeichnen. Im folgenden Beispiel <xref:System.Windows.Shapes.Rectangle> wird der eines <xref:System.Windows.Shapes.Shape.Fill%2A> mit einem diagonalen linearen Farbverlauf gezeichnet, der von gelb zu rot zu blau in Kalk grün übergeht.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Die folgende Abbildung zeigt den im vorherigen Beispiel erstellten Farbverlauf.  
  
 ![Diagonal linearer Farbverlauf](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 Um einen horizontalen linearen Farbverlauf zu erstellen, <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> ändern <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> <xref:System.Windows.Media.LinearGradientBrush> Sie und von in (0,0) und (1, 0,5). Im folgenden Beispiel wird ein <xref:System.Windows.Shapes.Rectangle> mit einem horizontalen linearen Farbverlauf gezeichnet.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 Die folgende Abbildung zeigt den im vorherigen Beispiel erstellten Farbverlauf.  
  
 ![Ein horizontaler linearer Farbverlauf](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 Um einen vertikalen linearen Farbverlauf zu erstellen, <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> ändern <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> <xref:System.Windows.Media.LinearGradientBrush> Sie und von in (0,5, 0) und (0,5, 1). Im folgenden Beispiel wird ein <xref:System.Windows.Shapes.Rectangle> mit einem vertikalen linearen Farbverlauf gezeichnet.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 Die folgende Abbildung zeigt den im vorherigen Beispiel erstellten Farbverlauf.  
  
 ![Vertikaler linearer Verlauf](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
> In den Beispielen in diesem Thema wird das Standard Koordinatensystem zum Festlegen von Startpunkten und Endpunkten verwendet. Das Standard Koordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent, und 1 gibt 100 Prozent des umgebenden Feldes an. Sie können dieses Koordinatensystem ändern, indem Sie <xref:System.Windows.Media.GradientBrush.MappingMode%2A> die-Eigenschaft auf <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>den Wert festlegen. Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld. Werte werden direkt im lokalen Raum interpretiert.  
  
 Weitere Beispiele finden Sie unter [Beispiel für Pinsel](https://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen zu Farbverläufen und anderen Pinseltypen finden Sie unter Übersicht über das Zeichnen [mit voll Tonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).
