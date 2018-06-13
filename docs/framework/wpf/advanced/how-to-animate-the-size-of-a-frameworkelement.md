---
title: 'Gewusst wie: Animieren der Größe von FrameworkElement'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: 148e3d592e129984bd2f7ac062340c5169e48d30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543984"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>Gewusst wie: Animieren der Größe von FrameworkElement
Animieren Sie die Größe des eine <xref:System.Windows.FrameworkElement>, können Sie entweder animieren seine <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften, oder verwenden Sie eine animierte <xref:System.Windows.Media.ScaleTransform>.  
  
 Im folgende Beispiel erstellt eine Animation die Größe der zwei Schaltflächen, die mithilfe der folgenden beiden Ansätze. Durch animieren die Größe einer Schaltfläche geändert wird seine <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft und eine andere durch animieren angepasst wird eine <xref:System.Windows.Media.ScaleTransform> angewendet, um seine <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft. Jede Schaltfläche enthält Text. Zu Beginn der Text wird in beiden Schaltflächen, während die Schaltflächen angepasst werden, der Text in die zweite Schaltfläche wird jedoch verzerrt Wert.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 Wenn Sie ein Element transformieren, werden das gesamte Element und dessen Inhalt transformiert. Wenn Sie die Größe eines Elements, wie im Fall der ersten Schaltfläche direkt ändern werden dem Inhalt des Elements nicht geändert werden, es sei denn, ihre Größe und Position von der Größe des jeweils übergeordneten Elements abhängen.  
  
 Animieren der Größe eines Elements durch Anwenden einer animierten Transformation auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft ermöglicht eine bessere Leistung als animiert seine <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> direkt, da die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft wird nicht ausgelöst, eine Layoutdurchlauf.  
  
 Weitere Informationen zum Animieren von Eigenschaften finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Weitere Informationen zu Transformationen finden Sie unter der [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).
