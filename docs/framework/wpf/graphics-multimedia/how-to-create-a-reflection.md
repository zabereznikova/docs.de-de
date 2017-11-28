---
title: 'Gewusst wie: Erstellen einer Reflektion'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3032f46843c6d8efc53c45a927feae7068c3eb5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-reflection"></a>Gewusst wie: Erstellen einer Reflektion
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.VisualBrush> eine Reflektion erstellt. Da eine <xref:System.Windows.Media.VisualBrush> vorhandene visuelle angezeigt werden können, können Sie diese Funktion verwenden, um interessante visuelle Effekte wie Reflektionen und Vergrößerung zu erzeugen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.VisualBrush> zum Erstellen einer Spiegelung einer <xref:System.Windows.Controls.Border> , die mehrere Elemente enthält. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Ein reflektiert visuelles Objekt](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "Graphicsmm_visualbrush_reflection_small")  
Ein reflektiertes Visual-Objekt  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Das vollständige Beispiel, das Beispiele, die zum Teilen des Bildschirms vergrößern und zur Erstellung von Reflektionen anzeigen enthält, finden Sie unter [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.VisualBrush>  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
