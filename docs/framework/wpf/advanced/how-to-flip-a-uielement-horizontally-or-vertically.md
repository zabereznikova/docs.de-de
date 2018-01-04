---
title: 'Gewusst wie: Horizontales oder vertikales Kippen eines UIElement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d34aea4ea99bc03b328fb08582cac3e18a98df66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a>Gewusst wie: Horizontales oder vertikales Kippen eines UIElement
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.ScaleTransform> Blättern eine <xref:System.Windows.UIElement> horizontal oder vertikal. In diesem Beispiel eine <xref:System.Windows.Controls.Button> Steuerelement (eine Art von <xref:System.Windows.UIElement>) wird durch Anwenden von gekippt eine <xref:System.Windows.Media.ScaleTransform> auf seine <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Die folgende Abbildung zeigt die Schaltfläche, um die flip.  
  
 ![Eine Schaltfläche ohne Transformierung](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "Graphicsmm_buttonflipbeforeflip")  
UIElement Blättern  
  
 Im folgenden sehen den Code, der die Schaltfläche "" erstellt.  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a>Beispiel  
 Um die Schaltfläche horizontal kippen, erstellen eine <xref:System.Windows.Media.ScaleTransform> und legen Sie dessen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Eigenschaft auf-1 festgelegt. Anwenden der <xref:System.Windows.Media.ScaleTransform> auf der Schaltfläche <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![Eine horizontal gekippte Schaltfläche &#40; 0,0 &#41; ] (../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "Graphicsmm_buttonfliphorizontalflip_displaced")  
Die Schaltfläche nach Anwendung von ScaleTransform  
  
## <a name="example"></a>Beispiel  
 Wie Sie aus der obigen Abbildung sehen können, wurde die Schaltfläche gekippt, aber es wurde auch verschoben. Ist, dass die Schaltfläche mit der von der linken oberen Ecke umgekehrt wurde. Um die Schaltfläche mit den festliegen Blättern, die Sie anwenden möchten die <xref:System.Windows.Media.ScaleTransform> auf seinen Mittelpunkt, die nicht in der Ecke. Eine einfache Möglichkeit zum Anwenden der <xref:System.Windows.Media.ScaleTransform> zu den Schaltflächen Center besteht darin, der Schaltfläche <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft auf 0,5, 0,5.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![Eine Schaltfläche horizontal ihren Mittelpunkt gekippte](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "Graphicsmm_buttonfliphorizontalflip_inplace")  
Die Schaltfläche mit einem RenderTransformOrigin von 0,5, 0,5  
  
## <a name="example"></a>Beispiel  
 Um die Schaltfläche vertikal kippen, legen Sie die <xref:System.Windows.Media.ScaleTransform> des Objekts <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> -Eigenschaft anstelle von dessen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Eigenschaft.  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![Eine Schaltfläche vertikal ihren Mittelpunkt gekippte](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "Graphicsmm_buttonflipverticalflip_inplace")  
Die vertikal gekippte Schaltfläche  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
