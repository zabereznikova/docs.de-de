---
title: 'Gewusst wie: Vereinfachen von Animationen durch untergeordnete Timeline-Objekte'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: daa4caac0046293e8b86a773bfffd46cf30e835b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>Gewusst wie: Vereinfachen von Animationen durch untergeordnete Timeline-Objekte
Dieses Beispiel zeigt, wie Sie Animationen zu vereinfachen, indem Sie untergeordnete <xref:System.Windows.Media.Animation.ParallelTimeline> Objekte. Ein <xref:System.Windows.Media.Animation.Storyboard> ist eine Art von <xref:System.Windows.Media.Animation.Timeline> Zielinformationen für die Zeitachsen, er enthält, bereitstellt. Verwenden einer <xref:System.Windows.Media.Animation.Storyboard> Zeitachse Adressieren von Informationen, einschließlich Informationen zu Objekt und Eigenschaft bereitstellen.  
  
 Um eine Animation starten, verwenden Sie eine oder mehrere <xref:System.Windows.Media.Animation.ParallelTimeline> Objekte als geschachtelte untergeordnete Elemente von einem <xref:System.Windows.Media.Animation.Storyboard>. Diese <xref:System.Windows.Media.Animation.ParallelTimeline> Objekte können andere Animationen enthalten und daher die zeitliche Steuerung Sequenzen in komplexen Animationen besser kapseln. Angenommen, Sie Animieren einer <xref:System.Windows.Controls.TextBlock> und mehrere Formen in der gleichen <xref:System.Windows.Media.Animation.Storyboard>, können Sie die Animationen für Trennen der <xref:System.Windows.Controls.TextBlock> und Formen, indem Sie diese jeweils in eine Separate <xref:System.Windows.Media.Animation.ParallelTimeline>. Da jede <xref:System.Windows.Media.Animation.ParallelTimeline> verfügt über eine eigene <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> und alle untergeordneten Elemente des der <xref:System.Windows.Media.Animation.ParallelTimeline> beginnen relativ zu dieser <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, ein Timeout besser gekapselt ist.  
  
 Das folgende Beispiel erstellt eine Animation zwei Teile des Texts (<xref:System.Windows.Controls.TextBlock> Objekte) von innerhalb des gleichen <xref:System.Windows.Media.Animation.Storyboard>. Ein <xref:System.Windows.Media.Animation.ParallelTimeline> kapselt die Animationen an eines der <xref:System.Windows.Controls.TextBlock> Objekte.  
  
 **Leistungshinweis:** Sie können jedoch schachteln <xref:System.Windows.Media.Animation.Storyboard> Zeitachsen innerhalb des jeweils anderen <xref:System.Windows.Media.Animation.ParallelTimeline>s sind besser geeignet, für das schachteln, da sie weniger Aufwand erfordern. (Die <xref:System.Windows.Media.Animation.Storyboard> Klasse erbt von der <xref:System.Windows.Media.Animation.ParallelTimeline> Klasse.)  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Angeben des Übergabeverhaltens zwischen Storyboard-Animationen](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
