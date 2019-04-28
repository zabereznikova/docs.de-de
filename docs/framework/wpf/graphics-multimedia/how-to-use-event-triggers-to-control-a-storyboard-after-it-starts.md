---
title: 'Vorgehensweise: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d444349f8bc9236e1d15f484f35b1326c77e2425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769290"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Vorgehensweise: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start
Dieses Beispiel zeigt, wie Sie steuern eine <xref:System.Windows.Media.Animation.Storyboard> nachdem es gestartet wurde. Starten einer <xref:System.Windows.Media.Animation.Storyboard> mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie <xref:System.Windows.Media.Animation.BeginStoryboard>, das verteilt der Animationen an die Objekte und Eigenschaften, die sie animieren, und klicken Sie dann das Storyboard gestartet wird. Wenn Sie geben <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen durch Angabe der <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> -Eigenschaft, Sie machen es ein steuerbares Storyboard. Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde.  
  
 Verwenden Sie die folgenden Storyboard Aktionen zusammen mit <xref:System.Windows.EventTrigger> Objekte zum Steuern eines Storyboards.  
  
- <xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard an.  
  
- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Setzt ein angehaltenes Storyboard fort.  
  
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Geschwindigkeit des Storyboards.  
  
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Setzt ein Storyboard an das Ende seines Füllbereichs, sofern vorhanden.  
  
- <xref:System.Windows.Media.Animation.StopStoryboard>: Hält das Storyboard an.  
  
- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard, das Freigeben von Ressourcen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Aktionen des steuerbaren Storyboards zum interaktiven Steuern eines Storyboards.  
  
 **Hinweis**: Ein Beispiel zum Steuern eines Storyboards mithilfe von Code finden Sie unter [steuern Sie ein Storyboard nach es beginnt mithilfe von einem interaktiven Methoden](how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Weitere Beispiele finden Sie unter den [Beispielsammlung](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Interaktives Steuern eines Storyboards, nachdem es gestartet wurde](how-to-control-a-storyboard-after-it-starts.md)
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
