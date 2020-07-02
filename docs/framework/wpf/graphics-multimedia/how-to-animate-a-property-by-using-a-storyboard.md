---
title: 'Gewusst wie: Animieren einer Eigenschaft unter Verwendung eines Storyboards'
description: Umgestalten Sie Ihre Benutzeroberfläche mit Animationen und Storyboards für Eigenschaften in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: f21b606751b845905a7bde6d3a7658b214369cc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853746"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Gewusst wie: Animieren einer Eigenschaft unter Verwendung eines Storyboards
In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.Animation.Storyboard> zum Animieren von Eigenschaften verwendet wird. Um eine Eigenschaft mit einem zu animieren <xref:System.Windows.Media.Animation.Storyboard> , erstellen Sie eine Animation für jede Eigenschaft, die Sie animieren möchten, und erstellen Sie auch eine <xref:System.Windows.Media.Animation.Storyboard> , die die Animationen enthalten soll.  
  
 Der Typ der Eigenschaft bestimmt den zu verwendenden Animationstyp. Um z. b. eine Eigenschaft zu animieren, die- <xref:System.Double> Werte annimmt, verwenden Sie eine <xref:System.Windows.Media.Animation.DoubleAnimation> . Die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaften und geben das Objekt und die Eigenschaft an, auf die die Animation angewendet wird.  
  
 Verwenden Sie zum Starten eines Storyboards in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] eine <xref:System.Windows.Media.Animation.BeginStoryboard> -Aktion und eine-Aktion <xref:System.Windows.EventTrigger> . <xref:System.Windows.EventTrigger>Startet die <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion, wenn das Ereignis, das durch die-Eigenschaft angegeben wird, <xref:System.Windows.EventTrigger.RoutedEvent%2A> auftritt. Mit dieser <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion wird das gestartet <xref:System.Windows.Media.Animation.Storyboard> .  
  
 Im folgenden Beispiel werden- <xref:System.Windows.Media.Animation.Storyboard> Objekte zum Animieren von zwei-Steuer <xref:System.Windows.Controls.Button> Elementen verwendet. Um die Größe der ersten Schaltfläche zu ändern, wird die-Klasse <xref:System.Windows.FrameworkElement.Width%2A> animiert. Um die Farbe der zweiten Schaltfläche zu ändern, wird die- <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft des-Objekts <xref:System.Windows.Media.SolidColorBrush> verwendet, um die <xref:System.Windows.Controls.Control.Background%2A> der animierten Schaltfläche festzulegen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Obwohl Animationen sowohl <xref:System.Windows.FrameworkElement> für ein-Objekt als auch für ein <xref:System.Windows.Controls.Control> -Objekt (z. b. <xref:System.Windows.Controls.Panel> ein-oder-Objekt) und für ein- <xref:System.Windows.Freezable> Objekt (z <xref:System.Windows.Media.Brush> <xref:System.Windows.Media.Transform> <xref:System.Windows.FrameworkElement.Name%2A> . b Verwenden Sie, wie im vorherigen Beispiel dargestellt, die [x:Name-Direktive](../../../desktop-wpf/xaml-services/xname-directive.md), um einem Freezable-Objekt einen Namen zuzuweisen, sodass es für eine Animation verwendet werden kann.  
  
 Wenn Sie Code verwenden, müssen Sie einen <xref:System.Windows.NameScope> für einen erstellen <xref:System.Windows.FrameworkElement> und die Namen der Objekte registrieren, die mit diesem animiert werden sollen <xref:System.Windows.FrameworkElement> . Um die Animationen im Code zu starten, verwenden Sie eine- <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion mit einem <xref:System.Windows.EventTrigger> . Optional können Sie einen Ereignishandler und die- <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode von verwenden <xref:System.Windows.Media.Animation.Storyboard> . Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode gezeigt.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Weitere Informationen über Animationen und Storyboards finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
 Wenn Sie Code verwenden, sind Sie nicht auf die Verwendung von-Objekten beschränkt, um <xref:System.Windows.Media.Animation.Storyboard> Eigenschaften zu animieren. Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md) und [Vorgehensweise: Animieren einer Eigenschaft mit AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
