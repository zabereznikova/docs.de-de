---
title: "Gewusst wie: Animieren eines Popups | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Animation, Popup-Steuerelemente"
  - "Popup-Steuerelement, Animation"
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Animieren eines Popups
In diesem Beispiel werden zwei Möglichkeiten veranschaulicht, ein <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement zu animieren.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.Primitives.PopupAnimation>\-Eigenschaft auf einen Wert von <xref:System.Windows.Controls.Primitives.PopupAnimation> festgelegt, sodass das <xref:System.Windows.Controls.Primitives.Popup> in die Ansicht "gleitet".  
  
 Um das <xref:System.Windows.Controls.Primitives.Popup> zu drehen, wird in diesem Beispiel <xref:System.Windows.Media.RotateTransform> der <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft auf dem <xref:System.Windows.Controls.Canvas>\-Element zugewiesen, das ein untergeordnetes Element von <xref:System.Windows.Controls.Primitives.Popup> ist.  
  
 Damit die Transformation ordnungsgemäß funktioniert, muss die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>\-Eigenschaft im Beispiel auf `true` festgelegt werden.  Außerdem muss der <xref:System.Windows.FrameworkElement.Margin%2A> auf dem <xref:System.Windows.Controls.Canvas>\-Inhalt genug Platz für das <xref:System.Windows.Controls.Primitives.Popup> angeben, damit es gedreht werden kann.  
  
 [!code-xml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis, dass beim Klicken auf ein <xref:System.Windows.Controls.Button>\-Element eintritt, das <xref:System.Windows.Media.Animation.Storyboard> auslöst, das die Animation startet.  
  
 [!code-xml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## Siehe auch  
 <xref:System.Windows.UIElement.RenderTransform%2A>   
 <xref:System.Windows.Controls.Primitives.BulletDecorator>   
 <xref:System.Windows.Media.RotateTransform>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 <xref:System.Windows.Controls.Primitives.Popup>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)   
 [Übersicht über Popups](../../../../docs/framework/wpf/controls/popup-overview.md)