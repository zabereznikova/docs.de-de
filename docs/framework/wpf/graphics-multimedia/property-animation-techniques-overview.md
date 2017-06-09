---
title: "&#220;bersicht &#252;ber die Verfahren zur Animation von Eigenschaften | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Animation, Eigenschaften, Methoden für"
  - "Eigenschaften, Methoden für die Animation"
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber die Verfahren zur Animation von Eigenschaften
In diesem Thema werden die unterschiedlichen Ansätze zum Animieren von Eigenschaften beschrieben: Storyboard\-Animationen, lokale Animationen, Uhren\- und Pro\-Frame\-Animationen.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 Für dieses Thema sollten Sie mit den unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) beschriebenen grundlegenden Animationsfeatures vertraut sein.  
  
<a name="summary"></a>   
## Verschiedene Möglichkeiten für Animationen  
 Da es viele unterschiedliche Szenarien zum Animieren von Eigenschaften gibt, stellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mehrere Ansätze zum Animieren von Eigenschaften bereit.  
  
 Die folgende Tabelle gibt für jeden Ansatz an, ob dieser pro Instanz, in Stilen, in Steuerelementvorlagen, in Datenvorlagen oder in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet werden kann und ob Sie mit diesem Ansatz die Animation interaktiv steuern können.  "Pro Instanz" bezieht sich auf das Verfahren, wonach eine Animation oder ein Storyboard auf die Objektinstanzen direkt angewendet wird, und nicht in einem Stil, einer Steuerelementvorlage oder einer Datenvorlage.  
  
|Animationsverfahren|Szenarien|Unterstützt XAML|Interaktiv steuerbar|  
|-------------------------|---------------|----------------------|--------------------------|  
|Storyboard\-Animation|Pro Instanz, <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.DataTemplate>|Ja|Ja|  
|Lokale Animation|Pro Instanz|Nein|Nein|  
|Uhranimation|Pro Instanz|Nein|Ja|  
|Pro\-Frame\-Animation|Pro Instanz|Nein|Nicht zutreffend|  
  
<a name="storyboard_animations"></a>   
## Storyboard\-Animationen  
 Verwenden Sie ein <xref:System.Windows.Media.Animation.Storyboard>, wenn Sie die Animationen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definieren und anwenden sowie nach dem Start interaktiv steuern oder eine komplexe Animationsstruktur erstellen möchten, bzw. wenn Sie die Animationen in einem <xref:System.Windows.Style>, in einer <xref:System.Windows.Controls.ControlTemplate> oder in einer <xref:System.Windows.DataTemplate> animieren möchten.  Damit ein Objekt in einem <xref:System.Windows.Media.Animation.Storyboard> animiert werden kann, muss es sich um ein <xref:System.Windows.FrameworkElement>\-Objekt oder ein <xref:System.Windows.FrameworkContentElement>\-Objekt handeln oder es muss zum Festlegen von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> verwendet werden.  Weitere Informationen finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Ein <xref:System.Windows.Media.Animation.Storyboard> ist ein spezieller Typ einer Container\-<xref:System.Windows.Media.Animation.Timeline>, die Zielinformationen für die darin enthaltenen Animationen zur Verfügung stellt.  Um mit einem <xref:System.Windows.Media.Animation.Storyboard> zu animieren, führen Sie die folgenden drei Schritte aus.  
  
1.  Deklarieren Sie ein <xref:System.Windows.Media.Animation.Storyboard> sowie eine oder mehrere Animationen.  
  
2.  Verwenden Sie die [angefügten Eigenschaften](GTMT) <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>, um das Zielobjekt und die Eigenschaft für jede Animation anzugeben.  
  
3.  \(Nur Code\) Definieren Sie einen <xref:System.Windows.NameScope> für ein <xref:System.Windows.FrameworkElement> oder ein <xref:System.Windows.FrameworkContentElement>.  Registrieren Sie die Namen der Objekte, um mit dem <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> eine Animation durchzuführen.  
  
4.  Starten Sie das <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Wenn das <xref:System.Windows.Media.Animation.Storyboard> gestartet wird, werden die Animationen auf die zu animierenden Eigenschaften angewendet und gestartet.  Sie haben zwei Möglichkeiten, ein <xref:System.Windows.Media.Animation.Storyboard> zu starten: Sie können die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode verwenden, die von der <xref:System.Windows.Media.Animation.Storyboard>\-Klasse bereitgestellt wird, oder Sie können eine <xref:System.Windows.Media.Animation.BeginStoryboard>\-Aktion verwenden.  Die einzige Möglichkeit zur Animation in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist die Verwendung einer <xref:System.Windows.Media.Animation.BeginStoryboard>\-Aktion. Eine <xref:System.Windows.Media.Animation.BeginStoryboard>\-Aktion kann in einem <xref:System.Windows.EventTrigger>, Eigenschaften\-<xref:System.Windows.Trigger> oder <xref:System.Windows.DataTrigger> verwendet werden.  
  
 Die folgende Tabelle zeigt die unterschiedlichen Stellen, an denen die einzelnen Verfahren zum Starten von <xref:System.Windows.Media.Animation.Storyboard> unterstützt werden: Pro Instanz, Stil, Steuerelementvorlage und Datenvorlage.  
  
|Storyboard wird gestartet mit…|Pro Instanz|Format|Steuerelementvorlage|Datenvorlage|Beispiel|  
|------------------------------------|-----------------|------------|--------------------------|------------------|--------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und einem <xref:System.Windows.EventTrigger>|Ja|Ja|Ja|Ja|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und einem Eigenschaften\-<xref:System.Windows.Trigger>|Nein|Ja|Ja|Ja|[Auslösen einer Animation, wenn sich eine Eigenschaft ändert](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und einem <xref:System.Windows.DataTrigger>|Nein|Ja|Ja|Ja|[How to: Trigger an Animation When Data Changes](http://msdn.microsoft.com/de-de/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode|Ja|Nein|Nein|Nein|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Weitere Informationen zu <xref:System.Windows.Media.Animation.Storyboard>\-Objekten finden Sie in der [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
## Lokale Animationen  
 Lokale Animationen bieten ein komfortables Verfahren, um eine [Abhängigkeitseigenschaft](GTMT) eines beliebigen <xref:System.Windows.Media.Animation.Animatable>\-Objekts zu animieren.  Verwenden Sie lokale Animationen, wenn Sie eine einzelne Animation auf eine Eigenschaft anwenden möchten und die Animation nach dem Start nicht interaktiv steuern müssen.  Im Gegensatz zu einer <xref:System.Windows.Media.Animation.Storyboard>\-Animation kann eine lokale Animation ein Objekt animieren, das keinem <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> zugeordnet ist.  Sie müssen auch keinen <xref:System.Windows.NameScope> für diesen Animationstyp definieren.  
  
 Lokale Animationen können nur im Code verwendet werden. Sie können nicht in Stilen, Steuerelementvorlagen oder Datenvorlagen definiert werden.  Eine lokale Animation kann nach ihrem Start nicht interaktiv gesteuert werden.  
  
 Um mit einer lokalen Animation ein Objekt zu animieren, führen Sie die folgenden Schritte aus.  
  
1.  Erstellen Sie ein <xref:System.Windows.Media.Animation.AnimationTimeline>\-Objekt.  
  
2.  Verwenden Sie die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode des zu animierenden Objekts, um die <xref:System.Windows.Media.Animation.AnimationTimeline> auf die von Ihnen angegebene Eigenschaft anzuwenden.  
  
 Im folgenden Beispiel wird die Animierung von Breite und Hintergrundfarbe einer <xref:System.Windows.Controls.Button> dargestellt.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## Uhranimationen  
 Verwenden Sie <xref:System.Windows.Media.MediaPlayer.Clock%2A>\-Objekte, wenn die Animation ohne ein <xref:System.Windows.Media.Animation.Storyboard> ausgeführt werden soll und Sie komplexe Zeitstrukturen erstellen oder die Animationen nach dem Start interaktiv steuern möchten.  Sie können Uhrobjekte verwenden, um eine [Abhängigkeitseigenschaft](GTMT) eines beliebigen <xref:System.Windows.Media.Animation.Animatable>\-Objekts zu animieren.  
  
 Sie können die <xref:System.Windows.Media.Animation.Clock>\-Objekte nicht direkt verwenden, um eine Animation in Stilen, Steuerelementvorlagen oder Datenvorlagen auszuführen.  \(Das Animations\- und Zeitsteuerungssystem verwendet zwar <xref:System.Windows.Media.Animation.Clock>\-Objekte zur Animation in Stilen, Steuerelementvorlagen und Datenvorlagen, muss diese <xref:System.Windows.Media.Animation.Clock>\-Objekte jedoch aus einem <xref:System.Windows.Media.Animation.Storyboard> erstellen.  Weitere Informationen über die Beziehung zwischen <xref:System.Windows.Media.Animation.Storyboard>\-Objekten und <xref:System.Windows.Media.Animation.Clock>\-Objekten finden Sie unter [Übersicht über das Animations\- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).\)  
  
 Um ein einzelnes <xref:System.Windows.Media.Animation.Clock>\-Objekt auf eine Eigenschaft anzuwenden, führen Sie die folgenden Schritte aus.  
  
1.  Erstellen Sie ein <xref:System.Windows.Media.Animation.AnimationTimeline>\-Objekt.  
  
2.  Verwenden Sie die <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A>\-Methode der <xref:System.Windows.Media.Animation.AnimationTimeline>, um eine <xref:System.Windows.Media.Animation.AnimationClock> zu erstellen.  
  
3.  Verwenden Sie die <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A>\-Methode des zu animierenden Objekts, um die <xref:System.Windows.Media.Animation.AnimationClock> auf die von Ihnen angegebene Eigenschaft anzuwenden.  
  
 Das folgende Beispiel zeigt, wie eine <xref:System.Windows.Media.Animation.AnimationClock> erstellt und auf zwei ähnliche Eigenschaften angewendet wird.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Um eine Zeitstruktur zu erstellen und sie zum Animieren von Eigenschaften zu verwenden, führen Sie die folgenden Schritte aus.  
  
1.  Verwenden Sie <xref:System.Windows.Media.Animation.ParallelTimeline>\-Objekte und <xref:System.Windows.Media.Animation.AnimationTimeline>\-Objekte, um die Zeitstruktur zu erstellen.  
  
2.  Verwenden Sie die <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A>\-Methode der Stamm\-<xref:System.Windows.Media.Animation.ParallelTimeline>, um eine <xref:System.Windows.Media.Animation.ClockGroup> zu erstellen.  
  
3.  Durchlaufen Sie die <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> der <xref:System.Windows.Media.Animation.ClockGroup>, und wenden Sie deren untergeordneten <xref:System.Windows.Media.Animation.Clock>\-Objekte an.  Verwenden Sie für jede untergeordnete <xref:System.Windows.Media.Animation.AnimationClock> die <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A>\-Methode des zu animierenden Objekts, um die <xref:System.Windows.Media.Animation.AnimationClock> auf die von Ihnen angegebene Eigenschaft anzuwenden.  
  
 Weitere Informationen über Uhrobjekte finden Sie unter [Übersicht über das Animations\- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## Pro\-Frame\-Animation: Umgehen des Animations\- und Zeitsteuerungssystems  
 Verwenden Sie diesen Ansatz, wenn Sie das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationssystem vollständig umgehen müssen.  Ein Szenario für diesen Ansatz sind Animationen in der Physik, wonach jeder Animationsschritt eine Neuberechnung der Objekte auf Basis des letzten Satzes der Objektinteraktionen erfordert.  
  
 Pro\-Frame\-Animationen können nicht innerhalb von Stilen, Steuerelementvorlagen und Datenvorlagen definiert werden.  
  
 Um einen Frame nach dem anderen zu animieren, registrieren Sie sich für das <xref:System.Windows.Media.CompositionTarget.Rendering>\-Ereignis des Objekts, das die zu animierenden Objekte enthält.  Diese Ereignishandlermethode wird einmal pro Frame aufgerufen.  Immer wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der [visuellen Struktur](GTMT) für die Kompositionsstruktur marshallt, wird die Ereignishandlermethode aufgerufen.  
  
 Führen Sie im Ereignishandler alle für den Animationseffekt erforderlichen Berechnungen durch, und legen Sie die Eigenschaften der Objekte fest, die mit diesen Werten animiert werden sollen.  
  
 Um die Präsentationszeit des aktuellen Frames abzurufen, kann die diesem Ereignis zugewiesene <xref:System.EventArgs>\-Klasse in <xref:System.Windows.Media.RenderingEventArgs> umgewandelt werden. Hierdurch wird eine <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A>\-Eigenschaft bereitgestellt, mit deren Hilfe Sie die Renderingzeit des aktuellen Frames abrufen können.  
  
 Weitere Informationen finden Sie auf der Seite <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Übersicht über das Animations\- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)