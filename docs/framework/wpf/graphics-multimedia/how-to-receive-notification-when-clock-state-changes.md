---
title: 'Vorgehensweise: Empfangen von Benachrichtigungen bei Statusänderungen der Uhr'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
ms.openlocfilehash: dc3fffb88ce59ceb908d6febd2f078820513b641
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363136"
---
# <a name="how-to-receive-notification-when-a-clocks-state-changes"></a>Vorgehensweise: Empfangen von Benachrichtigungen bei Statusänderungen der Uhr
Der Uhr <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> Ereignis tritt auf, wenn die <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> ungültig, z. B. wenn die Uhr startet oder beendet wird. Registrieren Sie sich, für dieses Ereignis mit der Verwendung von direkt eine <xref:System.Windows.Media.Animation.Clock>, oder registrieren Sie mit einem <xref:System.Windows.Media.Animation.Timeline>.  
  
 Im folgenden Beispiel eine <xref:System.Windows.Media.Animation.Storyboard> und zwei <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte werden verwendet, um die Breite von zwei Rechtecken zu animieren. Die <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> Ereignis wird zum Lauschen auf Änderungen des Ansichtszustands Uhr verwendet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 Die folgende Abbildung zeigt die verschiedenen Zustände, die Animationen geben Sie als die übergeordnete Zeitachse (*Storyboard*) im Verlauf.  
  
 ![Clock-Zustände für ein Drehbuch mit zwei Animationen](./media/graphicsmm-3timelines.png "graphicsmm_3timelines")  
  
 Die folgende Tabelle zeigt die Zeiten, zu dem *Animation1*des <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> -Ereignis ausgelöst wird:  
  
||||||||  
|-|-|-|-|-|-|-|  
|Zeit (Sekunden)|1|10|19|21|30|39|  
|Zustand|Aktiv|Aktiv|Beendet|Aktiv|Aktiv|Beendet|  
  
 Die folgende Tabelle zeigt die Zeiten, zu dem *Animation2*des <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> -Ereignis ausgelöst wird:  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Zeit (Sekunden)|1|9|11|19|21|29|31|39|  
|Zustand|Aktiv|Füllen|Aktiv|Beendet|Aktiv|Füllen|Aktiv|Beendet|  
  
 Beachten Sie, dass *Animation1*des <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> Ereignis bei 10 Sekunden ausgelöst wird, obwohl dessen Zustand bleibt <xref:System.Windows.Media.Animation.ClockState.Active>. Dies liegt daran aus geändert, jedoch seinen Status geändert wird, auf 10 Sekunden <xref:System.Windows.Media.Animation.ClockState.Active> zu <xref:System.Windows.Media.Animation.ClockState.Filling> und dann zurück zur <xref:System.Windows.Media.Animation.ClockState.Active> am selben Teilstrich.
