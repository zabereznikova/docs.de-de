---
title: 'Vorgehensweise: Horizontales oder vertikales Kippen eines UIElement'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215520"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a>Vorgehensweise: Horizontales oder vertikales Kippen eines UIElement
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.ScaleTransform> So kippen Sie ein <xref:System.Windows.UIElement> horizontal oder vertikal. In diesem Beispiel eine <xref:System.Windows.Controls.Button> Steuerelement (eine Art von <xref:System.Windows.UIElement>) gekippt wird, durch Anwenden einer <xref:System.Windows.Media.ScaleTransform> zu seine <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Die folgende Abbildung zeigt die Schaltfläche, um kippen.  
  
 ![Eine Schaltfläche ohne Transformierung](./media/graphicsmm-buttonflipbeforeflip.gif "Graphicsmm_buttonflipbeforeflip")  
Das zu kippende UIElement  
  
 Das folgende Beispiel zeigt den Code, der die Schaltfläche erstellt.  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a>Beispiel  
 Um die Schaltfläche horizontal zu kippen, erstellen eine <xref:System.Windows.Media.ScaleTransform> und legen Sie dessen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Eigenschaft auf-1 fest. Anwenden der <xref:System.Windows.Media.ScaleTransform> auf der Schaltfläche " <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![Eine gekippte Schaltfläche horizontal &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "Graphicsmm_buttonfliphorizontalflip_displaced")  
Die Schaltfläche nach Anwendung von ScaleTransform  
  
## <a name="example"></a>Beispiel  
 Wie Sie aus der obigen Abbildung sehen können, wurde die Schaltfläche gekippt, aber gleichzeitig verschoben. Das ist da die Schaltfläche mit der von der oberen linken Ecke gedreht wurde. Um die Schaltfläche direktes kippen, die Sie anwenden möchten die <xref:System.Windows.Media.ScaleTransform> um seinen Mittelpunkt, die nicht in der Ecke. Eine einfache Möglichkeit zum Anwenden der <xref:System.Windows.Media.ScaleTransform> auf Schaltflächen Center besteht darin, der der Schaltfläche <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft auf 0,5, 0,5.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![Eine Schaltfläche horizontal ihren Mittelpunkt gekippte](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "Graphicsmm_buttonfliphorizontalflip_inplace")  
Die Schaltfläche mit einem RenderTransformOrigin von 0,5, 0,5  
  
## <a name="example"></a>Beispiel  
 Um die Schaltfläche vertikal zu kippen, legen die <xref:System.Windows.Media.ScaleTransform> des Objekts <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> -Eigenschaft anstelle der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Eigenschaft.  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![Eine Schaltfläche vertikal ihren Mittelpunkt gekippte](./media/graphicsmm-buttonflipverticalflip-inplace.gif "Graphicsmm_buttonflipverticalflip_inplace")  
Die Schaltfläche "vertikal gekippt."  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Transformationen](../graphics-multimedia/transforms-overview.md)
