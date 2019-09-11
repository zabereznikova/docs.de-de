---
title: 'Vorgehensweise: Steuern eines Storyboards nach dem Start'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: de30cfdb49df721cb4d6845dc67464e8a5b61f93
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855862"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Vorgehensweise: Steuern eines Storyboards nach dem Start

Dieses Beispiel zeigt, wie Sie mithilfe von Code eine <xref:System.Windows.Media.Animation.Storyboard> steuern können, nachdem Sie gestartet wurde. Um ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Storyboard in zu steuern, verwenden <xref:System.Windows.TriggerAction> <xref:System.Windows.Trigger> Sie die-und-Objekte. ein Beispiel finden Sie unter Verwenden von [Ereignis Triggern zum Steuern eines Storyboards nach dessen Start](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).

Zum Starten eines Storyboards verwenden <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Sie die zugehörige-Methode, die die Animationen des Storyboards an die Eigenschaften verteilt, die Sie animieren, und das Storyboard startet.

Wenn Sie ein Storyboard steuerbar machen möchten, <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> verwenden Sie die-Methode, und geben Sie **true** als zweiten Parameter an. Anschließend können Sie die interaktiven Methoden des Storyboards verwenden, um das Storyboard anzuhalten, fortzusetzen, zu suchen, zu stoppen, zu beschleunigen oder zu verlangsamen, oder um das Storyboard in seine Füllzeit zu verschieben. Im folgenden finden Sie eine Liste der interaktiven Methoden des Storyboards:

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Hält das Storyboard an.

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Setzt ein angehaltene Storyboard fort.

- <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Legt die interaktive Geschwindigkeit des Storyboards fest.

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Sucht das Storyboard an der angegebenen Position.

- <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Sucht das Storyboard an der angegebenen Position. Anders als <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> bei der-Methode wird dieser Vorgang vor dem nächsten Tick verarbeitet.

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Verschiebt das Storyboard in seine Füllzeit, wenn es eine hat.

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Beendet das Storyboard.

Im folgenden Beispiel werden mehrere Storyboard-Methoden verwendet, um ein Storyboard interaktiv zu steuern.

> [!NOTE]
> Ein Beispiel für die Steuerung eines Storyboards mithilfe von Triggern [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]mit finden [Sie unter Verwenden von Ereignis Triggern zum Steuern eines Storyboards, nachdem es gestartet](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)wurde.

## <a name="example"></a>Beispiel

[!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
[!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]

## <a name="see-also"></a>Siehe auch

- [Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
