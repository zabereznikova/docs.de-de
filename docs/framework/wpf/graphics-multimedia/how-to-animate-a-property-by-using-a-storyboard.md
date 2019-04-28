---
title: 'Vorgehensweise: Animieren einer Eigenschaft unter Verwendung eines Storyboards'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: f6064368b4f5e4fa8324b4039d734d4430cd9174
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761207"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Vorgehensweise: Animieren einer Eigenschaft unter Verwendung eines Storyboards
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.Animation.Storyboard> zum Animieren von Eigenschaften. Zum Animieren einer Eigenschaft mithilfe einer <xref:System.Windows.Media.Animation.Storyboard>, erstellen Sie eine Animation für jede Eigenschaft, die Sie animieren und Sie erstellen möchten eine <xref:System.Windows.Media.Animation.Storyboard> die Animationen enthält.  
  
 Der Typ der Eigenschaft bestimmt den zu verwendenden Animationstyp. Zum Animieren einer Eigenschaft, die akzeptiert beispielsweise <xref:System.Double> Werte, verwenden eine <xref:System.Windows.Media.Animation.DoubleAnimation>. Die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügte Eigenschaften angeben, das Objekt und Eigenschaft, die auf die die Animation angewendet wird.  
  
 Zum Starten eines Storyboards [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], verwenden Sie eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion und ein <xref:System.Windows.EventTrigger>. Die <xref:System.Windows.EventTrigger> beginnt die <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion, wenn das Ereignis, das gemäß der <xref:System.Windows.EventTrigger.RoutedEvent%2A> wird. Die <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion startet den <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Im folgenden Beispiel wird <xref:System.Windows.Media.Animation.Storyboard> Objekte animieren zwei <xref:System.Windows.Controls.Button> Steuerelemente. Um die erste Schaltfläche in der Größe ändern, stellen die <xref:System.Windows.FrameworkElement.Width%2A> animiert ist. Auf der zweiten Schaltfläche ändern Sie Farbe, die <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft der <xref:System.Windows.Media.SolidColorBrush> dient zum Festlegen der <xref:System.Windows.Controls.Control.Background%2A> der Schaltfläche, die animiert wird.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Obwohl Animationen sowohl können eine <xref:System.Windows.FrameworkElement> Objekt, z. B. eine <xref:System.Windows.Controls.Control> oder <xref:System.Windows.Controls.Panel>, und ein <xref:System.Windows.Freezable> Objekt, z. B. eine <xref:System.Windows.Media.Brush> oder <xref:System.Windows.Media.Transform>, verfügen nur FrameworkElement-Objekte eine <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft. Verwenden Sie, wie im vorherigen Beispiel dargestellt, die [x:Name-Direktive](../../xaml-services/x-name-directive.md), um einem Freezable-Objekt einen Namen zuzuweisen, sodass es für eine Animation verwendet werden kann.  
  
 Wenn Sie Code verwenden, müssen Sie erstellen eine <xref:System.Windows.NameScope> für eine <xref:System.Windows.FrameworkElement> und registrieren Sie die Namen der Objekte, die mit dem Animieren <xref:System.Windows.FrameworkElement>. Verwenden Sie zum Starten der Animationen in Code eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion mit einer <xref:System.Windows.EventTrigger>. Optional können Sie einen Ereignishandler verwenden und die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> -Methode der <xref:System.Windows.Media.Animation.Storyboard>. Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode gezeigt.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Weitere Informationen über Animationen und Storyboards finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
 Wenn Sie Code verwenden, sind Sie nicht auf die Verwendung beschränkt <xref:System.Windows.Media.Animation.Storyboard> -Objekte zum Animieren von Eigenschaften. Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md) und [Vorgehensweise: Animieren einer Eigenschaft mit AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
