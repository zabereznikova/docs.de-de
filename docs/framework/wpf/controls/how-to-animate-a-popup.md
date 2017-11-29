---
title: 'Gewusst wie: Animieren eines Popups'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 276c1a54cfdddcde84c0702f4e84f1dc6174bbda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-popup"></a>Gewusst wie: Animieren eines Popups
Dieses Beispiel zeigt zwei Möglichkeiten zum Animieren einer <xref:System.Windows.Controls.Primitives.Popup> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.Primitives.PopupAnimation> Eigenschaft auf einen Wert von <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, wodurch die <xref:System.Windows.Controls.Primitives.Popup> "Folie-in" Wenn es angezeigt wird.  
  
 Um Drehen der <xref:System.Windows.Controls.Primitives.Popup>, in diesem Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft auf die <xref:System.Windows.Controls.Canvas>, also das untergeordnete Element des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Für die Transformation ordnungsgemäß funktioniert, muss im Beispiel Festlegen der <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Eigenschaft `true`. Darüber hinaus die <xref:System.Windows.FrameworkElement.Margin%2A> auf die <xref:System.Windows.Controls.Canvas> Inhalt muss genügend Speicherplatz für angeben der <xref:System.Windows.Controls.Primitives.Popup> drehen.  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 Das folgende Beispiel zeigt wie eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis, das auftritt, wenn eine <xref:System.Windows.Controls.Button> geklickt haben, werden Trigger die <xref:System.Windows.Media.Animation.Storyboard> , beginnt die Animation.  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [Übersicht über Popups](../../../../docs/framework/wpf/controls/popup-overview.md)
