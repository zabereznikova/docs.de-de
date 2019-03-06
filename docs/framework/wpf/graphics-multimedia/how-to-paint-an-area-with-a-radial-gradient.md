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
ms.openlocfilehash: c3bcc11dea4b1f223f629415591ab03588881dde
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379782"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Vorgehensweise: Zeichnen eines Bereichs mit einem radialen Farbverlauf
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.RadialGradientBrush> -Klasse zum Zeichnen eines Bereichs mit einem radialen Farbverlauf.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RadialGradientBrush> um ein Rechteck mit einem radialen Farbverlauf zu zeichnen, die von Gelb zu Rot zu Blau Gelbgrün geht.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 Die folgende Abbildung zeigt den Farbverlauf aus dem vorherigen Beispiel. Die Farbverlaufsunterbrechungspunkte wurden hervorgehoben.  
  
 ![Farbverlaufstopps in einem radialen Farbverlauf](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "Wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
>  In die Beispielen in diesem Thema verwenden das Standardkoordinatensystem zum Festlegen der Control-Punkte. Das Standardkoordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds, und 1 gibt 100 Prozent des umgebenden Felds. Sie können dieses Koordinatensystem ändern, durch Festlegen der <xref:System.Windows.Media.GradientBrush.MappingMode%2A> -Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute>. Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld. Werte werden direkt im lokalen Raum interpretiert.  
  
 Für zusätzliche <xref:System.Windows.Media.RadialGradientBrush> finden Sie unter den [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen über Farbverläufe und andere Typen von Pinseln, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).
