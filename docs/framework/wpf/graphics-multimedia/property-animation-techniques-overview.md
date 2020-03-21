---
title: Übersicht über die Verfahren zur Animation von Eigenschaften
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
ms.openlocfilehash: 0b4bf6d4963f32ad83f762fce73c805197ff9c9b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181845"
---
# <a name="property-animation-techniques-overview"></a>Übersicht über die Verfahren zur Animation von Eigenschaften
Dieses Thema beschreibt die unterschiedlichen Ansätze zum Animieren von Eigenschaften: Storyboards, lokale Animationen, Uhren und Pro-Frame-Animationen.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Als Voraussetzung für dieses Thema sollten Sie mit den grundlegenden Animationsfunktionen unter [Übersicht über Animationen](animation-overview.md) vertraut sein.  
  
<a name="summary"></a>
## <a name="different-ways-to-animate"></a>Verschiedene Methoden zum Animieren  
 Da viele unterschiedliche Szenarien zum Animieren von Eigenschaften vorhanden sind, bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mehrere Ansätze zum Animieren von Eigenschaften.  
  
 Für jeden der Ansätze gibt die folgende Tabelle an, ob er pro Instanz, in Stilen, in Steuerelementvorlagen oder in Datenvorlagen verwendet werden kann, ob er in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet werden kann und ob er Ihnen ermöglicht, die Animation interaktiv steuern kann.  „Pro Instanz“ bezieht sich auf das Verfahren, eine Animation oder ein Storyboard direkt auf Instanzen eines Objekts und nicht in einem Stil, einer Steuerelementvorlage oder einer Datenvorlage anzuwenden.  
  
|Animationsmethode|Szenarien|Unterstützt XAML|Interaktiv steuerbar|  
|-------------------------|---------------|-------------------|--------------------------------|  
|Storyboard-Animation|Pro Instanz, <xref:System.Windows.Style> <xref:System.Windows.Controls.ControlTemplate>, ,<xref:System.Windows.DataTemplate>|Ja|Ja|  
|Lokale Animation|Pro Instanz|Nein |Nein |  
|Uhranimation|Pro Instanz|Nein |Ja|  
|Pro-Frame-Animation|Pro Instanz|Nein |–|  
  
<a name="storyboard_animations"></a>
## <a name="storyboard-animations"></a>Storyboard-Animationen  
 Verwenden <xref:System.Windows.Media.Animation.Storyboard> Sie eine, wenn Sie Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Animationen in definieren und anwenden möchten, die Animationen nach <xref:System.Windows.Style> <xref:System.Windows.Controls.ControlTemplate> dem <xref:System.Windows.DataTemplate>Start interaktiv steuern, eine komplexe Animationsstruktur erstellen oder in einem oder animieren möchten. Damit ein Objekt von <xref:System.Windows.Media.Animation.Storyboard>einem animiert <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>werden soll, muss es <xref:System.Windows.FrameworkElement> ein <xref:System.Windows.FrameworkContentElement>oder sein, oder es muss zum Festlegen einer oder verwendet werden. Weitere Einzelheiten finden Sie unter [Übersicht über Storyboards](storyboards-overview.md).  
  
 A <xref:System.Windows.Media.Animation.Storyboard> ist ein spezieller Containertyp, <xref:System.Windows.Media.Animation.Timeline> der Zielinformationen für die darin enthaltenen Animationen bereitstellt. Um mit <xref:System.Windows.Media.Animation.Storyboard>einem zu animieren, führen Sie die folgenden drei Schritte aus.  
  
1. Deklarieren Sie eine <xref:System.Windows.Media.Animation.Storyboard> und eine oder mehrere Animationen.  
  
2. Verwenden <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Sie <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> die und angehängten Eigenschaften, um das Zielobjekt und die Eigenschaft jeder Animation anzugeben.  
  
3. (nur Code) Definieren <xref:System.Windows.NameScope> Sie <xref:System.Windows.FrameworkElement> eine <xref:System.Windows.FrameworkContentElement>für a oder . Registrieren Sie die Namen der <xref:System.Windows.FrameworkElement> Objekte, die mit diesem oder <xref:System.Windows.FrameworkContentElement>animiert werden sollen.  
  
4. Beginnen <xref:System.Windows.Media.Animation.Storyboard>Sie die .  
  
 Wenn <xref:System.Windows.Media.Animation.Storyboard> Sie eine beginnen, werden Animationen auf die Eigenschaften angewendet, die sie animieren, und sie gestartet. Es gibt zwei Möglichkeiten, <xref:System.Windows.Media.Animation.Storyboard>eine zu <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> beginnen: <xref:System.Windows.Media.Animation.Storyboard> Sie können die von <xref:System.Windows.Media.Animation.BeginStoryboard> der Klasse bereitgestellte Methode verwenden, oder Sie können eine Aktion verwenden. Die einzige Möglichkeit, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] eine Aktion <xref:System.Windows.Media.Animation.BeginStoryboard> zu verwenden, besteht darin, eine Aktion zu verwenden. Eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion kann in <xref:System.Windows.EventTrigger>einer <xref:System.Windows.Trigger>, <xref:System.Windows.DataTrigger>Eigenschaft oder einer verwendet werden.  
  
 Die folgende Tabelle zeigt die <xref:System.Windows.Media.Animation.Storyboard> verschiedenen Orte, an denen jede Anfangstechnik unterstützt wird: pro Instanz, Stil, Steuerelementvorlage und Datenvorlage.  
  
|Storyboard wird gestartet mit...|Pro Instanz|Style|Steuerelementvorlage|Datenvorlage|Beispiel|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>und ein<xref:System.Windows.EventTrigger>|Ja|Ja|Ja|Ja|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>und eine Immobilie<xref:System.Windows.Trigger>|Nein |Ja|Ja|Ja|[Auslösen einer Animation, wenn sich eine Eigenschaft ändert](how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>und ein<xref:System.Windows.DataTrigger>|Nein |Ja|Ja|Ja|[Vorgehensweise: Auslösen einer Animation bei Änderung eines Eigenschaftswerts](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode|Ja|Nein |Nein |Nein |[Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Weitere Informationen <xref:System.Windows.Media.Animation.Storyboard> zu Objekten finden Sie in der [Storyboards-Übersicht](storyboards-overview.md).  
  
## <a name="local-animations"></a>Lokale Animationen  
 Lokale Animationen bieten eine bequeme Möglichkeit, <xref:System.Windows.Media.Animation.Animatable> eine Abhängigkeitseigenschaft eines beliebigen Objekts zu animieren. Verwenden Sie lokale Animationen, wenn Sie eine einzelne Animation auf eine Eigenschaft anwenden möchten und Sie die Animation nach dem Start nicht interaktiv steuern müssen. Im <xref:System.Windows.Media.Animation.Storyboard> Gegensatz zu einer Animation kann eine lokale Animation ein <xref:System.Windows.FrameworkElement> Objekt <xref:System.Windows.FrameworkContentElement>animieren, das nicht mit einer oder einer verknüpft ist. Sie müssen auch keine <xref:System.Windows.NameScope> für diesen Animationstyp definieren.  
  
 Lokale Animationen können nur in Code verwendet und können nicht in Stilen, Steuerelementvorlagen oder Datenvorlagen definiert werden. Eine lokale Animation kann nicht interaktiv gesteuert werden, nachdem sie gestartet wurde.  
  
 Zum Animieren mithilfe einer lokalen Animation führen Sie folgende Schritte aus.  
  
1. Erstellen <xref:System.Windows.Media.Animation.AnimationTimeline> Sie ein Objekt.  
  
2. Verwenden <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Sie die Methode des Objekts, <xref:System.Windows.Media.Animation.AnimationTimeline> das Sie animieren möchten, um die auf die angegebene Eigenschaft anzuwenden.  
  
 Das folgende Beispiel zeigt, wie die Breite <xref:System.Windows.Controls.Button>und Hintergrundfarbe einer animiert wird.  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>Uhranimationen  
 Verwenden <xref:System.Windows.Media.MediaPlayer.Clock%2A> Sie Objekte, wenn Sie <xref:System.Windows.Media.Animation.Storyboard> animieren möchten, ohne a zu verwenden, und Sie möchten komplexe Zeitpläne erstellen oder Animationen interaktiv steuern, nachdem sie gestartet wurden. Sie können Clock-Objekte verwenden, um <xref:System.Windows.Media.Animation.Animatable> eine Abhängigkeitseigenschaft eines beliebigen Objekts zu animieren.  
  
 Sie können <xref:System.Windows.Media.Animation.Clock> Objekte nicht direkt zum Animieren in Stilen, Steuerelementvorlagen oder Datenvorlagen verwenden. (Das Animations- und Timingsystem verwendet <xref:System.Windows.Media.Animation.Clock> tatsächlich Objekte zum Animieren in Stilen, <xref:System.Windows.Media.Animation.Clock> Steuerelementvorlagen und <xref:System.Windows.Media.Animation.Storyboard>Datenvorlagen, muss diese Objekte jedoch aus einer für Sie erstellen. Weitere Informationen zur Beziehung <xref:System.Windows.Media.Animation.Storyboard> zwischen <xref:System.Windows.Media.Animation.Clock> Objekten und Objekten finden Sie unter [Animation und Timing Systemoverview](animation-and-timing-system-overview.md).)  
  
 Um eine <xref:System.Windows.Media.Animation.Clock> einzelne Eigenschaft auf eine Eigenschaft anzuwenden, führen Sie die folgenden Schritte aus.  
  
1. Erstellen <xref:System.Windows.Media.Animation.AnimationTimeline> Sie ein Objekt.  
  
2. Verwenden <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> Sie die <xref:System.Windows.Media.Animation.AnimationTimeline> Methode <xref:System.Windows.Media.Animation.AnimationClock>der zum Erstellen einer .  
  
3. Verwenden <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> Sie die Methode des Objekts, <xref:System.Windows.Media.Animation.AnimationClock> das Sie animieren möchten, um die auf die angegebene Eigenschaft anzuwenden.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Media.Animation.AnimationClock> wie Sie ein erstellen und es auf zwei ähnliche Eigenschaften anwenden.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Um eine Zeitsteuerungsstruktur zu erstellen und zum Animieren von Eigenschaften zu verwenden, führen Sie die folgenden Schritte aus.  
  
1. Verwenden <xref:System.Windows.Media.Animation.ParallelTimeline> <xref:System.Windows.Media.Animation.AnimationTimeline> Sie und Objekte, um die Zeitpläne zu erstellen.  
  
2. Verwenden <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> Sie die <xref:System.Windows.Media.Animation.ParallelTimeline> des <xref:System.Windows.Media.Animation.ClockGroup>Stamms, um eine zu erstellen.  
  
3. Iterieren Sie <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> durch <xref:System.Windows.Media.Animation.ClockGroup> die der <xref:System.Windows.Media.Animation.Clock> und wenden Sie ihre untergeordneten Objekte an. Verwenden <xref:System.Windows.Media.Animation.AnimationClock> Sie für <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> jedes untergeordnete Element die Methode des <xref:System.Windows.Media.Animation.AnimationClock> Objekts, das Sie animieren möchten, um die auf die angegebene Eigenschaft anzuwenden.  
  
 Weitere Informationen zu Uhrobjekten finden Sie unter [Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md).  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>Pro-Frame-Animation: Umgehen Sie das Animations- und Zeitsteuerungssystem  
 Verwenden Sie diesen Ansatz, wenn Sie das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystem vollständig umgehen müssen. Ein Szenario für diesen Ansatz sind Animationen in der Physik. Hier setzt jeder Schritt der Animation voraus, dass Objekte basierend auf dem letzten Satz von Objektinteraktionen neu berechnet werden müssen.  
  
 Pro-Frame-Animationen können nicht innerhalb der Stile, Steuerelementvorlagen oder Datenvorlagen definiert werden.  
  
 Um Frame-by-Frame zu animieren, registrieren Sie sich für das <xref:System.Windows.Media.CompositionTarget.Rendering> Ereignis des Objekts, das die Objekte enthält, die Sie animieren möchten. Diese Ereignishandlermethode wird einmal pro Frame aufgerufen. Immer wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der visuellen Struktur für die Kompositionsstruktur marshallt, wird die Ereignishandlermethode aufgerufen.  
  
 Führen Sie im Ereignishandler alle für den Animationseffekt erforderlichen Berechnungen durch, und legen Sie die Eigenschaften der Objekte fest, die Sie mit diesen Werten animieren möchten.  
  
 Um die Präsentationszeit für den <xref:System.EventArgs> aktuellen Frame zu erhalten, kann der diesem Ereignis zugeordnete als <xref:System.Windows.Media.RenderingEventArgs>, die eine <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> Eigenschaft bereitstellen, die Sie verwenden können, um die Renderzeit des aktuellen Frames abzuerhalten.  
  
 Weitere Informationen finden <xref:System.Windows.Media.CompositionTarget.Rendering> Sie auf der Seite.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
- [Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)
- [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md)
