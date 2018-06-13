---
title: 'Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: c864668026c4f8bb58a4d6c4c36f96fb07445a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561293"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start
In diesem Beispiel wird gezeigt, wie zur Steuerung einer <xref:System.Windows.Media.Animation.Storyboard> nach dem Start. Starten einer <xref:System.Windows.Media.Animation.Storyboard> mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden <xref:System.Windows.Media.Animation.BeginStoryboard>, die verteilt der Animationen an die Objekte und Eigenschaften, die sie dem animiert werden soll, und startet dann das Storyboard. Wenn verfügt <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen durch Angabe seiner <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> -Eigenschaft, ist er ein Storyboard steuerbares. Sie können dann das Storyboard interaktiv steuern nach dem Start.  
  
 Verwenden Sie die folgenden Storyboardaktionen zusammen mit <xref:System.Windows.EventTrigger> Objekte zum Steuern eines Storyboards.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Nimmt eine angehaltene Storyboards.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Geschwindigkeit des Storyboards.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Setzt ein Storyboard bis zum Ende des Füllzeitraums, falls vorhanden.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Das Storyboard beendet.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard und Verfügbarmachen von Ressourcen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird steuerbare Storyboard-Aktionen, um ein Storyboard interaktiv zu steuern.  
  
 **Hinweis:** ein Beispiel zum Steuern eines Storyboards mithilfe von Code finden Sie unter [ein Storyboard nach er startet mithilfe seiner interaktiven Methoden steuern](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Weitere Beispiele finden Sie unter der [Beispielsammlung](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [Interaktives Steuern eines Storyboards, nachdem es gestartet wurde](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
