---
title: 'Vorgehensweise: Animieren der Größe von FrameworkElement'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: d1995deec5ab2c9bf405911af43b4d242d599119
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776908"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>Vorgehensweise: Animieren der Größe von FrameworkElement
Zum Animieren der Größe der ein <xref:System.Windows.FrameworkElement>, animieren Sie entweder die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften oder verwenden Sie einen animierten <xref:System.Windows.Media.ScaleTransform>.  
  
 Im folgende Beispiel führt eine Animation die Größe der zwei Schaltflächen, die mit diesen beiden Ansätzen. Durch das Animieren der Größe einer Schaltfläche geändert wird seine <xref:System.Windows.FrameworkElement.Width%2A> ein durch Animation geändert wird eine <xref:System.Windows.Media.ScaleTransform> angewendet werden, um die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft. Jede Schaltfläche enthält Text. Zunächst wird der Text wird angezeigt, in dem beide Schaltflächen, jedoch wie die Schaltflächen geändert werden, erscheint der Text in die zweite Schaltfläche verzerrt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformanimations_snip#1](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 Wenn Sie ein Element transformieren, werden das gesamte Element und dessen Inhalt transformiert. Wenn Sie direkt die Größe eines Elements, wie im Fall der ersten Schaltfläche ändern, werden dem Inhalt des Elements nicht geändert werden, es sei denn, ihre Größe und Position von der Größe des jeweils übergeordneten Elements abhängen.  
  
 Animieren der Größe eines Elements durch Anwenden einer animierten-Transformation auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft bietet eine bessere Leistung als animiert die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> direkt, da die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft löst keinen Layoutdurchlauf.  
  
 Weitere Informationen zum Animieren von Eigenschaften finden Sie unter den [Übersicht über Animationen](../graphics-multimedia/animation-overview.md). Weitere Informationen zu Transformationen finden Sie unter den [Übersicht über Transformationen](../graphics-multimedia/transforms-overview.md).
