---
title: "Gewusst wie: Animieren einer Eigenschaft unter Verwendung eines Storyboards | Microsoft Docs"
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
  - "Animation, Storyboards"
  - "Storyboards, Animation"
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Animieren einer Eigenschaft unter Verwendung eines Storyboards
In diesem Beispiel wird die Verwendung von <xref:System.Windows.Media.Animation.Storyboard> zum Animieren von Eigenschaften dargestellt.  Erstellen Sie zum Animieren einer Eigenschaft mithilfe eines <xref:System.Windows.Media.Animation.Storyboard> eine Animation für jede Eigenschaft, die animiert werden soll, und erstellen Sie zusätzlich ein <xref:System.Windows.Media.Animation.Storyboard>, das die Animationen enthält.  
  
 Der Typ der Eigenschaft bestimmt den zu verwendenden Animationstyp.  Verwenden Sie zum Beispiel zum Animieren einer Eigenschaft, die <xref:System.Double>\-Werte entgegennimmt, eine <xref:System.Windows.Media.Animation.DoubleAnimation>\-Klasse.  Die [angefügten Eigenschaften](GTMT) <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> geben das Objekt und die Eigenschaft an, die animiert werden.  
  
 Verwenden Sie zum Starten eines Storyboards in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] eine <xref:System.Windows.Media.Animation.BeginStoryboard>\-Aktion und ein <xref:System.Windows.EventTrigger>\-Objekt.  Das <xref:System.Windows.EventTrigger>\-Objekt startet die <xref:System.Windows.Media.Animation.BeginStoryboard>\-Aktion, wenn das von der <xref:System.Windows.EventTrigger.RoutedEvent%2A>\-Eigenschaft angegebene Ereignis eintritt.  Die <xref:System.Windows.Media.Animation.BeginStoryboard>\-Aktion startet das <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Im folgenden Beispiel werden <xref:System.Windows.Media.Animation.Storyboard>\-Objekte verwendet, um zwei <xref:System.Windows.Controls.Button>\-Steuerelemente zu animieren.  Um die Größe der ersten Schaltfläche zu ändern, wird deren <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft animiert.  Die <xref:System.Windows.Media.SolidColorBrush.Color%2A>\-Eigenschaft von <xref:System.Windows.Media.SolidColorBrush> wird verwendet, um die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft der animierten Schaltfläche festzulegen und so die Farbe der zweiten Schaltfläche zu ändern.  
  
## Beispiel  
 [!code-xml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Obwohl Animationen sowohl für ein <xref:System.Windows.FrameworkElement>\-Objekt, z. B. <xref:System.Windows.Controls.Control> oder <xref:System.Windows.Controls.Panel>, als auch für ein <xref:System.Windows.Freezable>\-Objekt, z. B. <xref:System.Windows.Media.Brush> oder <xref:System.Windows.Media.Transform> möglich sind, verfügen nur FrameworkElement\-Objekte über eine <xref:System.Windows.FrameworkElement.Name%2A>\-Eigenschaft.  Verwenden Sie, wie im vorherigen Beispiel dargestellt, das [x:Name\-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md), um einem Freezable\-Objekt einen Namen zuzuweisen, sodass es für eine Animation verwendet werden kann.  
  
 Wenn Sie Code verwenden, müssen Sie einen <xref:System.Windows.NameScope> für ein <xref:System.Windows.FrameworkElement>\-Objekt erstellen und die Namen der zu animierenden Objekte mit diesem <xref:System.Windows.FrameworkElement>\-Objekt registrieren.  Verwenden Sie eine <xref:System.Windows.Media.Animation.BeginStoryboard>\-Aktion mit einem <xref:System.Windows.EventTrigger>, um die Animation zu starten.  Optional können Sie einen Ereignishandler und die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode von <xref:System.Windows.Media.Animation.Storyboard> verwenden.  Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode gezeigt.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Weitere Informationen über Animationen und Storyboards finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Wenn Sie Code verwenden, sind Sie nicht auf <xref:System.Windows.Media.Animation.Storyboard>\-Objekte zum Animieren von Eigenschaften beschränkt.  Weitere Informationen und Beispiele finden Sie unter [Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) und [Animieren einer Eigenschaft mit AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).