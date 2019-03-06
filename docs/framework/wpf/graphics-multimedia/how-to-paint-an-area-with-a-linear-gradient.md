---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einem linearen Farbverlauf'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: c48ff13811d784ecc7042b73b964a9e6f2d42a34
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367244"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Vorgehensweise: Zeichnen eines Bereichs mit einem linearen Farbverlauf
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.LinearGradientBrush> -Klasse zum Zeichnen eines Bereichs mit einem linearen Farbverlauf. Im folgenden Beispiel die <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle> einen diagonalen linearen Farbverlauf, der von Gelb zu Rot zu Blau Gelbgrün geht gezeichnet wird.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.  
  
 ![Diagonaler, linearer Farbverlauf](./media/graphicsmm-diagonallgb.jpg "Graphicsmm_DiagonalLGB")  
  
 Um einen horizontalen linearen Farbverlauf zu erstellen, Ändern der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> von der <xref:System.Windows.Media.LinearGradientBrush> in (0,0.5) und (1,0.5 ändern). Im folgenden Beispiel eine <xref:System.Windows.Shapes.Rectangle> einen horizontalen linearen Farbverlauf gezeichnet wird.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.  
  
 ![Einen horizontalen linearen Farbverlauf](./media/graphicsmm-horizontallgb.jpg "Graphicsmm_HorizontalLGB")  
  
 Um ein vertikaler, linearer Farbverlauf zu erstellen, Ändern der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> von der <xref:System.Windows.Media.LinearGradientBrush> in (0.5,0) und (0.5,1 ändern). Im folgenden Beispiel eine <xref:System.Windows.Shapes.Rectangle> vertikaler, linearer Farbverlauf gezeichnet wird.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.  
  
 ![Vertikaler, linearer Farbverlauf](./media/graphicsmm-verticallgb.jpg "Graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  In die Beispielen in diesem Thema verwenden das Standardkoordinatensystem zum Festlegen der Start- und Endpunkte. Das Standardkoordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds, und 1 gibt 100 Prozent des umgebenden Felds. Sie können dieses Koordinatensystem ändern, durch Festlegen der <xref:System.Windows.Media.GradientBrush.MappingMode%2A> -Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>. Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld. Werte werden direkt im lokalen Raum interpretiert.  
  
 Weitere Beispiele finden Sie unter [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen über Farbverläufe und andere Typen von Pinseln, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).
