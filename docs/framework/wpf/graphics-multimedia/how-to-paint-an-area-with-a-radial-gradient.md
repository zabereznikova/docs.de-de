---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einem radialen Farbverlauf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 5762ef1a1526ba6f004917c8a947e35ce731c86d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916103"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Vorgehensweise: Zeichnen eines Bereichs mit einem radialen Farbverlauf
Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Media.RadialGradientBrush> -Klasse verwenden, um einen Bereich mit einem radialen Farbverlauf zu zeichnen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird verwendet <xref:System.Windows.Media.RadialGradientBrush> , um ein Rechteck mit einem radialen Farbverlauf zu zeichnen, der von gelb zu rot zu blau in Kalk grün übergeht.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 Die folgende Abbildung zeigt den Farbverlauf aus dem vorherigen Beispiel. Die Verlaufs Stopps wurden hervorgehoben.  
  
 ![Farbverlaufstopps in einem radialen Farbverlauf](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "Wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
> In den Beispielen in diesem Thema wird das Standard Koordinatensystem zum Festlegen von Steuerungs Punkten verwendet. Das Standard Koordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent, und 1 gibt 100 Prozent des umgebenden Feldes an. Sie können dieses Koordinatensystem ändern, indem Sie <xref:System.Windows.Media.GradientBrush.MappingMode%2A> die-Eigenschaft auf <xref:System.Windows.Media.BrushMappingMode.Absolute>den Wert festlegen. Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld. Werte werden direkt im lokalen Raum interpretiert.  
  
 Weitere <xref:System.Windows.Media.RadialGradientBrush> Beispiele finden Sie im [Beispiel Pinsel](https://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen zu Farbverläufen und anderen Pinseltypen finden Sie unter Übersicht über das Zeichnen [mit voll Tonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).
