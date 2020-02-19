---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem radialen Farbverlauf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452752"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Gewusst wie: Zeichnen eines Bereichs mit einem radialen Farbverlauf
Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Media.RadialGradientBrush>-Klasse verwenden, um einen Bereich mit einem radialen Farbverlauf zu zeichnen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Rechteck mit einem <xref:System.Windows.Media.RadialGradientBrush> verwendet, um ein Rechteck mit einem radialen Farbverlauf zu zeichnen, der von gelb zu rot zu blau in Kalk grün übergeht.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 Die folgende Abbildung zeigt den Farbverlauf aus dem vorherigen Beispiel. Die Verlaufs Stopps wurden hervorgehoben.  
  
 ![Farbverlaufs Stopps in einem radialen Farbverlauf](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
> In den Beispielen in diesem Thema wird das Standard Koordinatensystem zum Festlegen von Steuerungs Punkten verwendet. Das Standard Koordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds an, und 1 gibt 100 Prozent des umgebenden Felds an. Sie können dieses Koordinatensystem ändern, indem Sie die <xref:System.Windows.Media.GradientBrush.MappingMode%2A>-Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute>festlegen. Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld. Werte werden direkt im lokalen Raum interpretiert.  
  
 Weitere <xref:System.Windows.Media.RadialGradientBrush> Beispiele finden Sie im [Beispiel Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Weitere Informationen zu Farbverläufen und anderen Pinseltypen finden Sie unter Übersicht über das Zeichnen [mit voll Tonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).
