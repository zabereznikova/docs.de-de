---
title: 'Gewusst wie: Steuern eines Storyboards nach dem Start'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b28cdf3b653925a5856c0bc9def5aebb9fdc6c14
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Gewusst wie: Steuern eines Storyboards nach dem Start
Dieses Beispiel zeigt, wie Code, um zu steuern verwendet eine <xref:System.Windows.Media.Animation.Storyboard> nachdem dieser gestartet wurde. Zum Steuern eines Storyboards in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie <xref:System.Windows.Trigger> und <xref:System.Windows.TriggerAction> Objekte ist ein Beispiel finden Sie unter [Ereignistriggern verwenden, um ein Storyboard nach Beginn steuern](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Um ein Storyboard zu starten, verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> -Methode, die das Storyboard-Animationen, um die Eigenschaften animierenden verteilt werden und das Storyboard gestartet wird.  
  
 Um ein Storyboard steuerbar festzulegen, verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, und geben Sie **"true"** als zweiten Parameter. Anschließend können Sie das Storyboard interaktiv Methoden anhalten, fortsetzen, seek, beenden, beschleunigen oder verlangsamen Sie das Storyboard oder auf den Füllzeitraum zu gelangen. Im folgenden finden eine Liste der interaktiven das Storyboard-Methoden:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Hält das Storyboard.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Nimmt eine angehaltene Storyboards.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Legt fest, interaktive Geschwindigkeit des Storyboards.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Sucht die Storyboards am angegebenen Speicherort.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Sucht die Storyboards am angegebenen Speicherort. Im Gegensatz zu den <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> -Methode, diesen Vorgang vor dem nächsten Teilstrich verarbeitet wird.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Setzt das Storyboard mit den Füllzeitraum, falls vorhanden.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Das Storyboard beendet.  
  
 Im folgenden Beispiel werden verschiedene Storyboard-Methoden verwendet, um ein Storyboard interaktiv zu steuern.  
  
 **Hinweis:** sehen Sie ein Beispiel zum Steuern eines Storyboards mithilfe von Triggern mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], finden Sie unter [Ereignistriggern verwenden, um ein Storyboard nach dem Start zu steuern](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
