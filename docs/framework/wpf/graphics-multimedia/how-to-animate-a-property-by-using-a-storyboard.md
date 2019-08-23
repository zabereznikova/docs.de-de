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
ms.openlocfilehash: a7a2656d84d37d3e2726df009a07ccf29661df07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963044"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Vorgehensweise: Animieren einer Eigenschaft unter Verwendung eines Storyboards
In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Media.Animation.Storyboard> ein zum Animieren von Eigenschaften verwendet wird. Um eine Eigenschaft mit einem <xref:System.Windows.Media.Animation.Storyboard>zu animieren, erstellen Sie eine Animation für jede Eigenschaft, die Sie animieren möchten, und erstellen Sie auch eine <xref:System.Windows.Media.Animation.Storyboard> , die die Animationen enthalten soll.  
  
 Der Typ der Eigenschaft bestimmt den zu verwendenden Animationstyp. Um z. b. eine Eigenschaft zu animieren <xref:System.Double> , die-Werte <xref:System.Windows.Media.Animation.DoubleAnimation>annimmt, verwenden Sie eine. Die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> angefügten Eigenschaften und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> geben das Objekt und die Eigenschaft an, auf die die Animation angewendet wird.  
  
 Verwenden Sie zum Starten eines Storyboards in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]eine <xref:System.Windows.Media.Animation.BeginStoryboard> -Aktion und eine <xref:System.Windows.EventTrigger>-Aktion. Startet die <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion<xref:System.Windows.EventTrigger.RoutedEvent%2A> , wenn das Ereignis, das durch die-Eigenschaft angegeben wird, auftritt. <xref:System.Windows.EventTrigger> <xref:System.Windows.Media.Animation.Storyboard>Mit dieser <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion wird das gestartet.  
  
 Im folgenden Beispiel werden <xref:System.Windows.Media.Animation.Storyboard> -Objekte zum Animieren <xref:System.Windows.Controls.Button> von zwei-Steuerelementen verwendet. Um die Größe der ersten Schaltfläche zu ändern, <xref:System.Windows.FrameworkElement.Width%2A> wird die-Klasse animiert. Um die Farbe der zweiten Schaltfläche zu ändern <xref:System.Windows.Media.SolidColorBrush.Color%2A> , <xref:System.Windows.Media.SolidColorBrush> wird die-Eigenschaft des-Objekts <xref:System.Windows.Controls.Control.Background%2A> verwendet, um die der animierten Schaltfläche festzulegen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> <xref:System.Windows.FrameworkElement> Obwohl Animationen sowohl <xref:System.Windows.Controls.Control> für ein-Objekt als auch für <xref:System.Windows.Controls.Panel>ein-Objekt (z <xref:System.Windows.Freezable> . b. ein <xref:System.Windows.Media.Brush> -oder <xref:System.Windows.Media.Transform> <xref:System.Windows.FrameworkElement.Name%2A> -Objekt) und für ein-Objekt (z. b Verwenden Sie, wie im vorherigen Beispiel dargestellt, die [x:Name-Direktive](../../xaml-services/x-name-directive.md), um einem Freezable-Objekt einen Namen zuzuweisen, sodass es für eine Animation verwendet werden kann.  
  
 Wenn Sie Code verwenden, müssen Sie einen <xref:System.Windows.NameScope> für einen <xref:System.Windows.FrameworkElement> erstellen und die Namen der Objekte registrieren, die mit diesem <xref:System.Windows.FrameworkElement>animiert werden sollen. Um die Animationen im Code zu starten, verwenden <xref:System.Windows.Media.Animation.BeginStoryboard> Sie eine- <xref:System.Windows.EventTrigger>Aktion mit einem. Optional können Sie einen Ereignishandler und die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> -Methode von <xref:System.Windows.Media.Animation.Storyboard>verwenden. Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode gezeigt.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Weitere Informationen über Animationen und Storyboards finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
 Wenn Sie Code verwenden, sind Sie nicht auf die Verwendung <xref:System.Windows.Media.Animation.Storyboard> von-Objekten beschränkt, um Eigenschaften zu animieren. Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md) und [Vorgehensweise: Animieren einer Eigenschaft mit AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
