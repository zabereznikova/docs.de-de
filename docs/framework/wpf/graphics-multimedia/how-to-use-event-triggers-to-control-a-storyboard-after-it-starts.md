---
title: 'Vorgehensweise: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 32591edd065a8122b84ff14102f672ccf6001d67
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855849"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Vorgehensweise: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start

In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Media.Animation.Storyboard> ein nach dem Starten gesteuert wird. Verwenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Media.Animation.Storyboard> Sie,umeinmitzustarten,mithilfevon,wodurchdieAnimationenandievonIhnenanimiertenObjekteundEigenschaftenverteiltwerden,undstartenSiedanndasStoryboard.<xref:System.Windows.Media.Animation.BeginStoryboard> Wenn Sie <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen angeben, indem Sie <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> die zugehörige-Eigenschaft angeben, legen Sie ihn als steuerbares Storyboard fest. Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde.

Verwenden Sie die folgenden storyboardaktionen in <xref:System.Windows.EventTrigger> Verbindung mit-Objekten, um ein Storyboard zu steuern.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard an.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Setzt ein angehaltene Storyboard fort.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die storyboardgeschwindigkeit.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Verschiebt ein Storyboard auf das Ende seines Füllzeitraums, wenn es über eines verfügt.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Beendet das Storyboard.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard und gibt Ressourcen frei.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden steuerbare storyboardaktionen verwendet, um ein Storyboard interaktiv zu steuern.

> [!NOTE]
> Ein Beispiel für die Steuerung eines Storyboards mithilfe von Code finden Sie unter [Steuern eines Storyboards, nachdem es mit seiner interaktiven Methode begonnen](how-to-control-a-storyboard-after-it-starts.md)hat.

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

Weitere Beispiele finden Sie in der [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).

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
