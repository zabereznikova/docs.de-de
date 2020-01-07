---
title: 'Gewusst wie: Animieren einer Eigenschaft unter Verwendung eines Storyboards'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: 6cfce9a5b070a23ed9ac03473888bf572b61393b
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559637"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Gewusst wie: Animieren einer Eigenschaft unter Verwendung eines Storyboards
In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.Animation.Storyboard> zum Animieren von Eigenschaften verwendet wird. Um eine Eigenschaft mithilfe einer <xref:System.Windows.Media.Animation.Storyboard>zu animieren, erstellen Sie eine Animation für jede Eigenschaft, die Sie animieren möchten, und erstellen Sie auch eine <xref:System.Windows.Media.Animation.Storyboard>, die die Animationen enthalten soll.  
  
 Der Typ der Eigenschaft bestimmt den zu verwendenden Animationstyp. Verwenden Sie z. b. eine-<xref:System.Windows.Media.Animation.DoubleAnimation>, um eine Eigenschaft zu animieren, die <xref:System.Double> Werte annimmt. Die Eigenschaften <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angehängter geben das Objekt und die Eigenschaft an, auf die die Animation angewendet wird.  
  
 Verwenden Sie zum Starten eines Storyboards in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion und eine <xref:System.Windows.EventTrigger>. Der <xref:System.Windows.EventTrigger> startet die <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion, wenn das Ereignis, das durch seine <xref:System.Windows.EventTrigger.RoutedEvent%2A>-Eigenschaft angegeben wird, auftritt. Die <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion startet die <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Im folgenden Beispiel werden <xref:System.Windows.Media.Animation.Storyboard>-Objekte verwendet, um zwei <xref:System.Windows.Controls.Button>-Steuerelemente zu animieren. Um die Größe der ersten Schaltfläche zu ändern, wird der <xref:System.Windows.FrameworkElement.Width%2A> animiert. Um die Farbe der zweiten Schaltfläche zu ändern, wird die <xref:System.Windows.Media.SolidColorBrush.Color%2A>-Eigenschaft des <xref:System.Windows.Media.SolidColorBrush> verwendet, um die <xref:System.Windows.Controls.Control.Background%2A> der animierten Schaltfläche festzulegen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Obwohl Animationen sowohl als Ziel für ein <xref:System.Windows.FrameworkElement> Objekt, wie z. b. eine <xref:System.Windows.Controls.Control> oder <xref:System.Windows.Controls.Panel>, als auch ein <xref:System.Windows.Freezable> Objekt (z. b. eine <xref:System.Windows.Media.Brush> oder <xref:System.Windows.Media.Transform>) als Ziel haben, haben nur Frameworkelemente eine <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft Verwenden Sie, wie im vorherigen Beispiel dargestellt, die [x:Name-Direktive](../../../desktop-wpf/xaml-services/xname-directive.md), um einem Freezable-Objekt einen Namen zuzuweisen, sodass es für eine Animation verwendet werden kann.  
  
 Wenn Sie Code verwenden, müssen Sie eine <xref:System.Windows.NameScope> für eine <xref:System.Windows.FrameworkElement> erstellen und die Namen der Objekte registrieren, die mit diesem <xref:System.Windows.FrameworkElement>animiert werden sollen. Um die Animationen im Code zu starten, verwenden Sie eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion mit einem <xref:System.Windows.EventTrigger>. Optional können Sie einen Ereignishandler und die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode von <xref:System.Windows.Media.Animation.Storyboard>verwenden. Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode gezeigt.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Weitere Informationen über Animationen und Storyboards finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
 Wenn Sie Code verwenden, sind Sie nicht auf die Verwendung <xref:System.Windows.Media.Animation.Storyboard>-Objekten beschränkt, um Eigenschaften zu animieren. Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md) und [Vorgehensweise: Animieren einer Eigenschaft mit AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
