---
title: 'Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186700"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start

Dieses Beispiel zeigt, <xref:System.Windows.Media.Animation.Storyboard> wie sie nach dem Start eines steuert. Um eine <xref:System.Windows.Media.Animation.Storyboard> mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]zu <xref:System.Windows.Media.Animation.BeginStoryboard>starten, verwenden Sie , die die Animationen an die Objekte und Eigenschaften verteilt, die sie animieren, und starten Sie dann das Storyboard. Wenn Sie <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen angeben, indem Sie dessen <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> Eigenschaft angeben, machen Sie ihn zu einem kontrollierbaren Storyboard. Sie können dann das Storyboard interaktiv steuern, nachdem es gestartet wurde.

Verwenden Sie die folgenden <xref:System.Windows.EventTrigger> Storyboard-Aktionen zusammen mit Objekten, um ein Storyboard zu steuern.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard an.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Setzt ein angehaltenes Storyboard fort.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Storyboard-Geschwindigkeit.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Verschiebt ein Storyboard bis zum Ende seiner Füllperiode, wenn es eins hat.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Stoppt das Storyboard.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard und gibt Ressourcen frei.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden steuerbare Storyboardaktionen verwendet, um ein Storyboard interaktiv zu steuern.

> [!NOTE]
> Ein Beispiel für die Steuerung eines Storyboards mithilfe von Code finden Sie unter [Steuern eines Storyboards, nachdem es mit seinen interaktiven Methoden beginnt.](how-to-control-a-storyboard-after-it-starts.md)

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

Weitere Beispiele finden Sie in der [Animationsbeispielgalerie](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Interaktives Steuern eines Storyboards, nachdem es gestartet wurde](how-to-control-a-storyboard-after-it-starts.md)
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
