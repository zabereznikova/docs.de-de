---
title: 'Vorgehensweise: Steuern eines Storyboards, nachdem es gestartet wurde'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 680676921e14ad69d97f3ee1c39e3ec955e66dec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662138"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Vorgehensweise: Steuern eines Storyboards, nachdem es gestartet wurde
Dieses Beispiel zeigt, wie Sie mit Code zum Steuern einer <xref:System.Windows.Media.Animation.Storyboard> nachdem es gestartet wurde. Zum Steuern eines Storyboards in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie <xref:System.Windows.Trigger> und <xref:System.Windows.TriggerAction> Objekte; ein Beispiel finden Sie unter [Verwenden von Ereignistriggern zum Steuern einer Storyboards nach dessen Start](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Um ein Storyboard zu starten, verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> -Methode, die die Storyboard Animationen auf die Eigenschaften animierenden verteilt werden und startet das Storyboard.  
  
 Um ein Storyboard steuerbar ist, verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, und geben Sie **"true"** als zweiten Parameter. Können Sie dann die Storyboard interaktiven Methoden zum Anhalten, fortsetzen, suchen, beenden, beschleunigen, oder das Storyboard verlangsamen oder können es auf seines Füllbereichs. Im folgenden finden eine Liste der Storyboard interaktiven Methoden:  
  
- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Hält das Storyboard an.  
  
- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Setzt ein angehaltenes Storyboard fort.  
  
- <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Legt die Geschwindigkeit des Storyboards interaktive fest.  
  
- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Suchen das Storyboard aus der angegebenen Position ein.  
  
- <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Sucht das Storyboard am angegebenen Speicherort. Im Gegensatz zu den <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> -Methode, diesen Vorgang wird verarbeitet, bevor das nächste Ticken.  
  
- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Setzt das Storyboard, um seines Füllbereichs, sofern vorhanden.  
  
- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Hält das Storyboard an.  
  
 Im folgenden Beispiel werden mehrere Storyboard-Methoden zum interaktiven Steuern eines Storyboards.  
  
 **Hinweis**: Finden Sie ein Beispiel zum Steuern eines Storyboards mithilfe von Triggern mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], finden Sie unter [Verwenden von Ereignistriggern zum Steuern einer Storyboards nach dessen Start](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
