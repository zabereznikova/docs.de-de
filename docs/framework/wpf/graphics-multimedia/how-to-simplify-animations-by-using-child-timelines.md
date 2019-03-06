---
title: 'Vorgehensweise: Vereinfachen von Animationen durch untergeordnete Zeitachsen'
ms.date: 03/30/2017
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
ms.openlocfilehash: 933ba2dff86b99bddd8d8f75bafcd94833b2e066
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370357"
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>Vorgehensweise: Vereinfachen von Animationen durch untergeordnete Zeitachsen
Dieses Beispiel zeigt, wie Sie Animationen durch untergeordnete vereinfachen <xref:System.Windows.Media.Animation.ParallelTimeline> Objekte. Ein <xref:System.Windows.Media.Animation.Storyboard> ist eine Art von <xref:System.Windows.Media.Animation.Timeline> , die Zielinformationen für die Zeitachsen, er enthält, bereitstellt. Verwenden einer <xref:System.Windows.Media.Animation.Storyboard> Zielinformationen, einschließlich Informationen zu Objekt und Eigenschaft bereitstellen.  
  
 Um eine Animation zu starten, verwenden Sie eine oder mehrere <xref:System.Windows.Media.Animation.ParallelTimeline> Objekte als geschachtelte untergeordnete Elemente einer <xref:System.Windows.Media.Animation.Storyboard>. Diese <xref:System.Windows.Media.Animation.ParallelTimeline> Objekte können andere Animationen enthalten und daher die Zeitabfolge in komplexen Animationen besser kapseln. Angenommen, Sie animieren möchten eine <xref:System.Windows.Controls.TextBlock> und mehrere Formen in der gleichen <xref:System.Windows.Media.Animation.Storyboard>, können Sie die Animationen für trennen die <xref:System.Windows.Controls.TextBlock> und für die Formen, indem Sie diese jeweils in eine Separate <xref:System.Windows.Media.Animation.ParallelTimeline>. Da jede <xref:System.Windows.Media.Animation.ParallelTimeline> verfügt über eine eigene <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> und alle untergeordneten Elemente des der <xref:System.Windows.Media.Animation.ParallelTimeline> starten relativ zu diesem <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, zeitsteuerung besser gekapselt.  
  
 Im folgende Beispiel werden zwei Textteile animiert (<xref:System.Windows.Controls.TextBlock> Objekte) von innerhalb des gleichen <xref:System.Windows.Media.Animation.Storyboard>. Ein <xref:System.Windows.Media.Animation.ParallelTimeline> kapselt die Animationen eines der <xref:System.Windows.Controls.TextBlock> Objekte.  
  
 **Leistungshinweis:** Obwohl Sie schachteln können <xref:System.Windows.Media.Animation.Storyboard> ineinander, <xref:System.Windows.Media.Animation.ParallelTimeline>sind besser zum Verschachteln, da sie weniger Aufwand erfordern. (Die <xref:System.Windows.Media.Animation.Storyboard> Klasse erbt von der <xref:System.Windows.Media.Animation.ParallelTimeline> Klasse.)  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Animationen](animation-overview.md)
- [Angeben des Übergabeverhaltens zwischen Storyboard-Animationen](how-to-specify-handoffbehavior-between-storyboard-animations.md)
