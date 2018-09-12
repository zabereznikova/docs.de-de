---
title: Übersicht über benutzerdefinierte Animationen
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes [WPF], animation
- key frames [WPF], custom
- custom key frames [WPF]
- animation [WPF], custom classes
- custom animation classes [WPF]
ms.assetid: 9be69d50-3384-4938-886f-08ce00e4a7a6
ms.openlocfilehash: a18898f340c68b7890c56b586c87870c50fd4686
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44511892"
---
# <a name="custom-animations-overview"></a>Übersicht über benutzerdefinierte Animationen
In diesem Thema wird beschrieben, wie und wann das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystem durch Erstellen benutzerdefinierter Keyframes oder Animationsklassen erweitert oder durch Pro-Frame-Rückrufe umgangen wird.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie mit den verschiedenen Arten von Animationen vertraut sein, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt werden. Weitere Informationen finden Sie unter Übersicht über die From/To/By-Animationen, [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) und [Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 Da die Animationsklassen erben die <xref:System.Windows.Freezable> -Klasse, Sie sollten mit vertraut sein <xref:System.Windows.Freezable> Objekte "und" Gewusst wie: erben von <xref:System.Windows.Freezable>. Weitere Informationen finden Sie unter der [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>   
## <a name="extending-the-animation-system"></a>Erweitern des Animationssystems  
 Es gibt zahlreiche Methoden zum Erweitern des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystems, abhängig von der Ebene der integrierten Funktionen, die Sie verwenden möchten.  Es gibt drei primäre Erweiterungspunkte in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animations-Engine:  
  
-   Erstellen Sie ein benutzerdefiniertes Keyframe-Objekt durch Erben von einer von der  *\<Typ >* KeyFrame-Klassen, z. B. <xref:System.Windows.Media.Animation.DoubleKeyFrame>. Dieser Ansatz verwendet die meisten der integrierten Funktionen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animations-Engine.  
  
-   Erstellen Sie eine eigene Animationsklasse durch Vererbung von <xref:System.Windows.Media.Animation.AnimationTimeline> mindestens eine der  *\<Typ >* AnimationBase-Klassen.  
  
-   Verwenden Sie Pro-Frame-Rückruf, um Animationen auf einer Pro-Frame-Basis zu generieren. Bei diesem Ansatz werden die Animations- und Zeitsteuerungssysteme vollständig umgangen.  
  
 In der folgenden Tabelle werden einige die Szenarios zur Erweiterung des Animationssystems beschrieben.  
  
|Aktion|Vorgehensweise|  
|-------------------------|-----------------------|  
|Anpassen der Interpolation zwischen Werten eines Typs mit einer entsprechenden *\<Typ>* AnimationUsingKeyFrames|Erstellen Sie ein benutzerdefiniertes Keyframe. Weitere Informationen finden Sie im Abschnitt [Erstellen eines benutzerdefinierten Keyframe](#createacustomkeyframe).|  
|Anpassen von mehr als einer Interpolation zwischen Werten eines Typs mit einer entsprechenden *\<Typ>* Animation|Erstellen Sie eine benutzerdefinierte Animationsklasse, die von der *\<Typ>* AnimationBase-Klasse erbt, die dem Typ entspricht, den Sie animieren möchten. Weitere Informationen finden Sie im Abschnitt [Erstellen einer benutzerdefinierten Animationsklasse](#createacustomanimationtype).|  
|Animieren eines Typs, der keine entsprechende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animation besitzt|Verwenden einer <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> oder erstellen Sie eine Klasse, die von erbt <xref:System.Windows.Media.Animation.AnimationTimeline>. Weitere Informationen finden Sie im Abschnitt [Erstellen einer benutzerdefinierten Animationsklasse](#createacustomanimationtype).|  
|Animieren mehrerer Objekte mit Werten, die pro Frame berechnet werden und auf dem letzten Satz von Objektinteraktionen basieren|Verwenden Sie einen Pro-Frame-Rückruf. Weitere Informationen finden Sie im Abschnitt [Verwenden eines Pro-Frame-Rückrufs](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## <a name="create-a-custom-key-frame"></a>Erstellen eines benutzerdefinierten Keyframes  
 Die einfachste Möglichkeit zum Erweitern des Animationssystems ist das Erstellen einer benutzerdefinierten Keyframe-Klasse. Verwenden Sie diesen Ansatz, wenn Sie eine andere Interpolationsmethode für eine Keyframe-Animation möchten.  Wie in [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) beschrieben ist, verwendet eine Keyframe-Animation Keyframe-Objekte, um die Ausgabewerte zu generieren. Jedes Keyframe-Objekt hat drei Funktionen:  
  
-   Gibt an, ein Ziel mithilfe der <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> Eigenschaft.  
  
-   Gibt die Uhrzeit, an dem dieser Wert erreicht sein soll mithilfe, der <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> Eigenschaft.  
  
-   Interpoliert zwischen dem Wert des vorherigen Keyframes und dem eigenen Wert durch Implementieren der InterpolateValueCore-Methode.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von der abstrakten *\<Typ>* KeyFrame-Klasse ab, und implementieren Sie die InterpolateValueCore-Methode. Die InterpolateValueCore-Methode gibt den aktuellen Wert des Keyframes zurück. Es werden zwei Parameter übernommen: der Wert des vorherigen Keyframes und ein Fortschrittswert, der zwischen 0 und 1 liegt. Ein Fortschrittswert von 0 gibt an, der Keyframe gerade gestartet wurde, und der Wert 1 gibt an, dass der Keyframe gerade abgeschlossen wurde, und sollte den Wert von zurückgeben seiner <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> Eigenschaft.  
  
 Da die  *\<Typ >* KeyFrame-Klassen erben von der <xref:System.Windows.Freezable> -Klasse, müssen Sie auch überschreiben <xref:System.Windows.Freezable.CreateInstanceCore%2A> Core, um eine neue Instanz der Klasse zurückzugeben. Wenn die Klasse keine Abhängigkeitseigenschaften zum Speichern von Daten nutzt oder nach der Erstellung eine zusätzliche Initialisierung erfordert, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Nach der Erstellung von benutzerdefinierten *\<Typ>* KeyFrame-Animationen können Sie sie mit den *\<Typ>* AnimationUsingKeyFrames für diesen Typ verwenden.  
  
<a name="createacustomanimationtype"></a>   
## <a name="create-a-custom-animation-class"></a>Erstellen einer benutzerdefinierten Animationsklasse  
 Beim Erstellen Ihres eigenen Animationstyps können Sie besser steuern, wie ein Objekt animiert wird. Es gibt zwei empfohlene Methoden zur Erstellung Ihrer eigenen Animationstyps: Es sind ableitungen von den <xref:System.Windows.Media.Animation.AnimationTimeline> Klasse oder die  *\<Typ >* AnimationBase-Klasse. Das Ableiten von der *\<Typ>* Animation- oder der *\<Typ>* AnimationUsingKeyFrames-Klasse wird nicht empfohlen.  
  
### <a name="derive-from-typeanimationbase"></a>Ableiten von \<Typ>AnimationBase  
 Das Ableiten von einer *\<Typ>* AnimationBase-Klasse ist die einfachste Möglichkeit zum Erstellen eines neuen Animationstyps. Verwenden Sie diesen Ansatz, wenn Sie eine neue Animation für einen Typ erstellen, der bereits über eine entsprechende *\<Typ>* AnimationBase-Klasse verfügt.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von einer *\<Typ>* Animation-Klasse ab und implementieren Sie die GetCurrentValueCore-Methode. Die GetCurrentValueCore-Methode gibt den aktuellen Wert der Animation zurück. Es werden drei Parameter übernommen: Ein vorgeschlagener Anfangswert, ein vorgeschlagener Endwert und eine <xref:System.Windows.Media.Animation.AnimationClock>, die Sie verwenden, um den Fortschritt der Animation zu bestimmen.  
  
 Da die  *\<Typ >* AnimationBase-Klassen erben von der <xref:System.Windows.Freezable> -Klasse, müssen Sie auch überschreiben <xref:System.Windows.Freezable.CreateInstanceCore%2A> Core, um eine neue Instanz der Klasse zurückzugeben. Wenn die Klasse keine Abhängigkeitseigenschaften zum Speichern von Daten nutzt oder nach der Erstellung eine zusätzliche Initialisierung erfordert, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Weitere Informationen finden Sie in der Dokumentation zur GetCurrentValueCore-Methode für die *\<Typ>* AnimationBase-Klasse für den Typ, die Sie animieren möchten. Ein Beispiel hierfür finden Sie unter [Beispiel für benutzerdefinierte Animation](https://go.microsoft.com/fwlink/?LinkID=159981)  
  
 **Alternative Ansätze**  
  
 Wenn Sie lediglich die Art der Interpolation von Animationswerten ändern möchten, kommt eine Ableitung von einer der *\<Typ>* KeyFrame-Klassen infrage. Der von Ihnen erstellte Keyframe kann mit den entsprechenden *\<Typ>* AnimationUsingKeyFrames verwendet werden, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt werden.  
  
### <a name="derive-from-animationtimeline"></a>Ableiten von AnimationTimeline  
 Leiten Sie von der <xref:System.Windows.Media.Animation.AnimationTimeline> Klasse, wenn Sie möchten eine Animation für einen Typ erstellen, das bereits ein entsprechendes keine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animation, oder Sie möchten eine Animation zu erstellen, die nicht stark typisiert ist.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von der <xref:System.Windows.Media.Animation.AnimationTimeline> Klasse, und überschreiben Sie die folgenden Elemente:  
  
-   <xref:System.Windows.Freezable.CreateInstanceCore%2A> – Wenn die neue Klasse konkret ist, müssen Sie Sie überschreiben <xref:System.Windows.Freezable.CreateInstanceCore%2A> um eine neue Instanz der Klasse zurückzugeben.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> – Überschreiben Sie diese Methode, um den aktuellen Wert Ihrer Animation zurückzugeben. Es werden drei Parameter übernommen: ein Standardursprungswert, ein Standardzielwert und eine <xref:System.Windows.Media.Animation.AnimationClock>. Verwenden der <xref:System.Windows.Media.Animation.AnimationClock> um die aktuelle Uhrzeit oder den Fortschritt der Animation zu erhalten. Sie können auswählen, ob die Standardursprungs- oder zielwerte verwendet werden.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> – Überschreiben Sie diese Eigenschaft, um anzugeben, ob die Animation den Standardzielwert gemäß verwendet die <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> Methode.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> – Überschreiben Sie diese Eigenschaft an, dass die <xref:System.Type> der Ausgabe der Animation erzeugten.  
  
 Wenn die Klasse keine Abhängigkeitseigenschaften zum Speichern von Daten nutzt oder nach der Erstellung eine zusätzliche Initialisierung erfordert, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Das empfohlene Paradigma (verwendet von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationen) besteht in der Verwendung von zwei Vererbungsebenen:  
  
1.  Erstellen Sie eine abstrakte  *\<Typ >* AnimationBase-Klasse, die von abgeleitet <xref:System.Windows.Media.Animation.AnimationTimeline>. Diese Klasse sollte überschreiben die <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> Methode. Sollte auch eine neue abstrakte Methode GetCurrentValueCore, einführen und außer Kraft setzen <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> , damit sie die Typen des Standardursprungswerts und Parameter überprüft hat, ruft Sie GetCurrentValueCore.  
  
2.  Erstellen Sie eine andere Klasse, die erbt von der neuen  *\<Typ >* AnimationBase-Klasse und überschreibt die <xref:System.Windows.Freezable.CreateInstanceCore%2A> -Methode, die GetCurrentValueCore-Methode, die Sie eingeführt, und die <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> Eigenschaft.  
  
 **Alternative Ansätze**  
  
 Wenn Sie einen Typ zu animieren, die ohne entsprechende From/To/By-Animation Keyframe-Animation oder möchten, sollten Sie verwenden eine <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>. Da schwach typisiert ist, ist ein <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> können jede Art von Wert animieren. Der Nachteil dieses Ansatzes besteht darin, die <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> unterstützt nur diskreten Interpolation.  
  
<a name="useperframecallback"></a>   
## <a name="use-per-frame-callback"></a>Verwenden eines Pro-Frame-Rückrufs  
 Verwenden Sie diesen Ansatz, wenn Sie das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystem vollständig umgehen müssen. Ein Szenario für diesen Ansatz sind Animationen in der Physik. Hier muss bei jedem Animationsschritt basierend auf dem letzten Satz von Objektinteraktionen eine neue Richtung oder Position des animierten Objekts berechnet werden.  
  
 **Implementierungsanweisungen**  
  
 Im Gegensatz zu den anderen in dieser Übersicht beschriebenen Methoden müssen Sie bei der Verwendung von Pro-Frame-Rückrufen keine benutzerdefinierte Animation oder Keyframe-Klasse erstellen.  
  
 Stattdessen registrieren Sie sich für die <xref:System.Windows.Media.CompositionTarget.Rendering> -Ereignis des Objekts, das die Objekte enthält, Sie animieren möchten. Diese Ereignishandlermethode wird einmal pro Frame aufgerufen. Immer wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der visuellen Struktur für die Kompositionsstruktur marshallt, wird die Ereignishandlermethode aufgerufen.  
  
 Führen Sie im Ereignishandler alle für den Animationseffekt erforderlichen Berechnungen durch, und legen Sie die Eigenschaften der Objekte fest, die Sie mit diesen Werten animieren möchten.  
  
 Um die Präsentationszeit des aktuellen Frames, erhalten die <xref:System.EventArgs> zugeordnete Ereignis umgewandelt werden kann <xref:System.Windows.Media.RenderingEventArgs>, bieten eine <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> -Eigenschaft, die Sie verwenden können, um den aktuellen Frame abzurufen des rendering-Zeit.  
  
 Weitere Informationen finden Sie unter den <xref:System.Windows.Media.CompositionTarget.Rendering> Seite.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.AnimationTimeline>  
 <xref:System.Windows.Media.Animation.IKeyFrame>  
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über das Animations- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Benutzerdefiniertes Animationsbeispiel](https://go.microsoft.com/fwlink/?LinkID=159981)
