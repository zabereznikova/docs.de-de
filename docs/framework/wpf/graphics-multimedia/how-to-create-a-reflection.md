---
title: 'Vorgehensweise: Erstellen einer Reflektion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 61b597cd36fcf0d60f215d9b5403f3b42b21dec4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904220"
---
# <a name="how-to-create-a-reflection"></a>Vorgehensweise: Erstellen einer Reflektion
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.VisualBrush> eine Reflektion erstellt. Da eine <xref:System.Windows.Media.VisualBrush> können vorhandene visuelle anzeigen, Sie können diese Funktion verwenden, um interessante visuelle Effekte, z.B. Reflexionen und vergrößerungen zu erzeugen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.VisualBrush> zum Erstellen einer Spiegelung einer <xref:System.Windows.Controls.Border> , das mehrere Elemente enthält. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Ein wiedergegeben visuellen Objekts](./media/graphicsmm-visualbrush-reflection-small.jpg "Graphicsmm_visualbrush_reflection_small")  
Ein reflektiertes Visual-Objekt  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Das vollständige Beispiel, das Beispiele enthält, die zeigen, wie Sie Teile des Bildschirms zu vergrößern und Reflektionen erstellt werden, finden Sie unter [Beispiel zu VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.VisualBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
