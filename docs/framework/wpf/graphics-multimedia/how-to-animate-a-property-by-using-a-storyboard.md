---
title: 'Gewusst wie: Animieren einer Eigenschaft unter Verwendung eines Storyboards'
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
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2129ea06e8c92b3912d2abdd3d1a63e651ac59e1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Gewusst wie: Animieren einer Eigenschaft unter Verwendung eines Storyboards
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.Animation.Storyboard> zum Animieren von Eigenschaften. Zum Animieren einer Eigenschaft mithilfe einer <xref:System.Windows.Media.Animation.Storyboard>, erstellen Sie eine Animation für jede Eigenschaft, die Sie verwenden möchten, dem animiert werden soll, und erstellen außerdem eine <xref:System.Windows.Media.Animation.Storyboard> Animationen enthalten.  
  
 Der Typ der Eigenschaft bestimmt den zu verwendenden Animationstyp. Angenommen, eine Eigenschaft animieren, akzeptiert <xref:System.Double> Werte, verwenden eine <xref:System.Windows.Media.Animation.DoubleAnimation>. Die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> angefügte Eigenschaften angeben, dem Objekt und der Eigenschaft, die auf die die Animation angewendet wird.  
  
 So starten Sie ein Storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], verwenden Sie eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion und ein <xref:System.Windows.EventTrigger>. Die <xref:System.Windows.EventTrigger> beginnt die <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion, wenn das Ereignis, das gemäß seiner <xref:System.Windows.EventTrigger.RoutedEvent%2A> -Eigenschaft tritt auf. Die <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion startet den <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Im folgenden Beispiel wird <xref:System.Windows.Media.Animation.Storyboard> Objekte zu animierende zwei <xref:System.Windows.Controls.Button> Steuerelemente. Auf der ersten Schaltfläche in der Größe ändern seiner <xref:System.Windows.FrameworkElement.Width%2A> animiert wird. Auf der zweiten Schaltfläche Farbe ändern die <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft der <xref:System.Windows.Media.SolidColorBrush> dient zum Festlegen der <xref:System.Windows.Controls.Control.Background%2A> neben der Schaltfläche, die animiert wird.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Obwohl Animationen beide können eine <xref:System.Windows.FrameworkElement> Objekt, wie eine <xref:System.Windows.Controls.Control> oder <xref:System.Windows.Controls.Panel>, und ein <xref:System.Windows.Freezable> Objekt, wie eine <xref:System.Windows.Media.Brush> oder <xref:System.Windows.Media.Transform>, nur Frameworkelemente haben eine <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft. Verwenden Sie, wie im vorherigen Beispiel dargestellt, die [x:Name-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md), um einem Freezable-Objekt einen Namen zuzuweisen, sodass es für eine Animation verwendet werden kann.  
  
 Wenn Sie Code möchten verwenden, müssen Sie erstellen eine <xref:System.Windows.NameScope> für eine <xref:System.Windows.FrameworkElement> und registrieren Sie die Namen der Objekte, die mit dem Animieren <xref:System.Windows.FrameworkElement>. Verwenden Sie zum Starten der Animationen in Code eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion mit einer <xref:System.Windows.EventTrigger>. Optional können Sie einen Ereignishandler verwenden und die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode <xref:System.Windows.Media.Animation.Storyboard>. Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode gezeigt.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Weitere Informationen über Animationen und Storyboards finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Wenn Sie Code verwenden, sind Sie nicht auf die Verwendung beschränkt <xref:System.Windows.Media.Animation.Storyboard> Objekte, um Eigenschaften zu animieren. Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) und [Vorgehensweise: Animieren einer Eigenschaft mit AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).
