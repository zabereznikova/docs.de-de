---
title: 'Gewusst wie: Erstellen einer Reflektion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 8a5ed345c0aa25312bd74799264e1f66ab4554e0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452057"
---
# <a name="how-to-create-a-reflection"></a>Gewusst wie: Erstellen einer Reflektion
In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.VisualBrush> zum Erstellen einer Reflektion verwendet werden kann. Da eine <xref:System.Windows.Media.VisualBrush> ein vorhandenes visuelles Element anzeigen kann, können Sie diese Funktion verwenden, um interessante visuelle Effekte, wie z. b. Reflektionen und Vergrößerung, zu erzeugen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.VisualBrush> verwendet, um eine Reflektion einer <xref:System.Windows.Controls.Border> zu erstellen, die mehrere-Elemente enthält. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Ein reflektiertes Visual-Objekt](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Ein reflektiertes Visual-Objekt  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Das vollständige Beispiel, das Beispiele enthält, die veranschaulichen, wie Teile des Bildschirms vergrößert werden und wie Sie Reflektionen erstellen, finden Sie unter [VisualBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.VisualBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
