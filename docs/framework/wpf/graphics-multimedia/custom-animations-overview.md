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
ms.openlocfilehash: 5a9ca51b87f73a24b90d0bd843ee306f8a1b970a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453090"
---
# <a name="custom-animations-overview"></a>Übersicht über benutzerdefinierte Animationen
In diesem Thema wird beschrieben, wie und wann das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystem durch Erstellen benutzerdefinierter Keyframes oder Animationsklassen erweitert oder durch Pro-Frame-Rückrufe umgangen wird.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie mit den verschiedenen Arten von Animationen vertraut sein, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt werden. Weitere Informationen finden Sie unter Übersicht über die From/To/By-Animationen, [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md) und [Übersicht über Pfadanimationen](path-animations-overview.md).  
  
 Da die Animations Klassen von der <xref:System.Windows.Freezable>-Klasse erben, sollten Sie mit <xref:System.Windows.Freezable> Objekten und der Vererbung von <xref:System.Windows.Freezable>vertraut sein. Weitere Informationen finden Sie unter der [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>   
## <a name="extending-the-animation-system"></a>Erweitern des Animationssystems  
 Es gibt zahlreiche Methoden zum Erweitern des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystems, abhängig von der Ebene der integrierten Funktionen, die Sie verwenden möchten.  Es gibt drei primäre Erweiterungspunkte in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animations-Engine:  
  
- Erstellen Sie ein benutzerdefiniertes Keyframe-Objekt, indem Sie von einem der *\<Typen >* Keyframe-Klassen erben, z. b. <xref:System.Windows.Media.Animation.DoubleKeyFrame>. Dieser Ansatz verwendet die meisten der integrierten Funktionen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animations-Engine.  
  
- Erstellen Sie eine eigene Animations Klasse, indem Sie von <xref:System.Windows.Media.Animation.AnimationTimeline> oder einer der *\<Type >* AnimationBase-Klassen erben.  
  
- Verwenden Sie Pro-Frame-Rückruf, um Animationen auf einer Pro-Frame-Basis zu generieren. Bei diesem Ansatz werden die Animations- und Zeitsteuerungssysteme vollständig umgangen.  
  
 In der folgenden Tabelle werden einige die Szenarios zur Erweiterung des Animationssystems beschrieben.  
  
|Aktion|Vorgehensweise|  
|-------------------------|-----------------------|  
|Anpassen der Interpolation zwischen Werten eines Typs mit einer entsprechenden *\<Typ>* AnimationUsingKeyFrames|Erstellen Sie ein benutzerdefiniertes Keyframe. Weitere Informationen finden Sie im Abschnitt [Erstellen eines benutzerdefinierten Keyframe](#createacustomkeyframe).|  
|Anpassen von mehr als einer Interpolation zwischen Werten eines Typs mit einer entsprechenden *\<Typ>* Animation|Erstellen Sie eine benutzerdefinierte Animationsklasse, die von der *\<Typ>* AnimationBase-Klasse erbt, die dem Typ entspricht, den Sie animieren möchten. Weitere Informationen finden Sie im Abschnitt [Erstellen einer benutzerdefinierten Animationsklasse](#createacustomanimationtype).|  
|Animieren eines Typs, der keine entsprechende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animation besitzt|Verwenden Sie einen <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>, oder erstellen Sie eine Klasse, die von <xref:System.Windows.Media.Animation.AnimationTimeline>erbt. Weitere Informationen finden Sie im Abschnitt [Erstellen einer benutzerdefinierten Animationsklasse](#createacustomanimationtype).|  
|Animieren mehrerer Objekte mit Werten, die pro Frame berechnet werden und auf dem letzten Satz von Objektinteraktionen basieren|Verwenden Sie einen Pro-Frame-Rückruf. Weitere Informationen finden Sie im Abschnitt [Verwenden eines Pro-Frame-Rückrufs](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## <a name="create-a-custom-key-frame"></a>Erstellen eines benutzerdefinierten Keyframes  
 Die einfachste Möglichkeit zum Erweitern des Animationssystems ist das Erstellen einer benutzerdefinierten Keyframe-Klasse. Verwenden Sie diesen Ansatz, wenn Sie eine andere Interpolationsmethode für eine Keyframe-Animation möchten.  Wie in [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md) beschrieben ist, verwendet eine Keyframe-Animation Keyframe-Objekte, um die Ausgabewerte zu generieren. Jedes Keyframe-Objekt hat drei Funktionen:  
  
- Gibt einen Zielwert mit der <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>-Eigenschaft an.  
  
- Gibt die Uhrzeit an, zu der dieser Wert mit der <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>-Eigenschaft erreicht werden soll.  
  
- Interpoliert zwischen dem Wert des vorherigen Keyframes und dem eigenen Wert durch Implementieren der InterpolateValueCore-Methode.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von der abstrakten *\<Typ>* KeyFrame-Klasse ab, und implementieren Sie die InterpolateValueCore-Methode. Die InterpolateValueCore-Methode gibt den aktuellen Wert des Keyframes zurück. Es werden zwei Parameter übernommen: der Wert des vorherigen Keyframes und ein Fortschrittswert, der zwischen 0 und 1 liegt. Der Fortschritt 0 gibt an, dass der Keyframe gerade gestartet wurde, und der Wert 1 gibt an, dass der Keyframe gerade abgeschlossen wurde, und sollte den Wert zurückgeben, der durch die <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>-Eigenschaft angegeben wird.  
  
 Da der *\<-Typ >* Keyframe-Klassen von der <xref:System.Windows.Freezable>-Klasse erben, müssen Sie auch <xref:System.Windows.Freezable.CreateInstanceCore%2A> Core überschreiben, um eine neue Instanz der Klasse zurückzugeben. Wenn die Klasse keine Abhängigkeitseigenschaften zum Speichern von Daten nutzt oder nach der Erstellung eine zusätzliche Initialisierung erfordert, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Nach der Erstellung von benutzerdefinierten *\<Typ>* KeyFrame-Animationen können Sie sie mit den *\<Typ>* AnimationUsingKeyFrames für diesen Typ verwenden.  
  
<a name="createacustomanimationtype"></a>   
## <a name="create-a-custom-animation-class"></a>Erstellen einer benutzerdefinierten Animationsklasse  
 Beim Erstellen Ihres eigenen Animationstyps können Sie besser steuern, wie ein Objekt animiert wird. Es gibt zwei empfohlene Methoden zum Erstellen eines eigenen Animations Typs: Sie können eine Ableitung von der <xref:System.Windows.Media.Animation.AnimationTimeline>-Klasse oder vom *\<-Typ >* AnimationBase-Klasse durchführen. Das Ableiten von der *\<Typ>* Animation- oder der *\<Typ>* AnimationUsingKeyFrames-Klasse wird nicht empfohlen.  
  
### <a name="derive-from-typeanimationbase"></a>Ableiten von \<Typ>AnimationBase  
 Das Ableiten von einer *\<Typ>* AnimationBase-Klasse ist die einfachste Möglichkeit zum Erstellen eines neuen Animationstyps. Verwenden Sie diesen Ansatz, wenn Sie eine neue Animation für einen Typ erstellen, der bereits über eine entsprechende *\<Typ>* AnimationBase-Klasse verfügt.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von einer *\<Typ>* Animation-Klasse ab und implementieren Sie die GetCurrentValueCore-Methode. Die GetCurrentValueCore-Methode gibt den aktuellen Wert der Animation zurück. Es werden drei Parameter benötigt: ein empfohlener Startwert, ein empfohlener Endwert und ein <xref:System.Windows.Media.Animation.AnimationClock>, mit dem der Fortschritt der Animation bestimmt wird.  
  
 Da der *\<-Typ >* AnimationBase-Klassen von der <xref:System.Windows.Freezable>-Klasse erben, müssen Sie auch <xref:System.Windows.Freezable.CreateInstanceCore%2A> Core überschreiben, um eine neue Instanz der Klasse zurückzugeben. Wenn die Klasse keine Abhängigkeitseigenschaften zum Speichern von Daten nutzt oder nach der Erstellung eine zusätzliche Initialisierung erfordert, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Weitere Informationen finden Sie in der Dokumentation zur GetCurrentValueCore-Methode für die *\<Typ>* AnimationBase-Klasse für den Typ, die Sie animieren möchten. Ein Beispiel hierfür finden Sie unter [Beispiel für benutzerdefinierte Animation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)  
  
 **Alternative Ansätze**  
  
 Wenn Sie lediglich die Art der Interpolation von Animationswerten ändern möchten, kommt eine Ableitung von einer der *\<Typ>* KeyFrame-Klassen infrage. Der von Ihnen erstellte Keyframe kann mit den entsprechenden *\<Typ>* AnimationUsingKeyFrames verwendet werden, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt werden.  
  
### <a name="derive-from-animationtimeline"></a>Ableiten von AnimationTimeline  
 Leiten Sie von der <xref:System.Windows.Media.Animation.AnimationTimeline>-Klasse ab, wenn Sie eine Animation für einen Typ erstellen möchten, der nicht bereits über eine passende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animation verfügt, oder wenn Sie eine Animation erstellen möchten, die nicht stark typisiert ist.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von der <xref:System.Windows.Media.Animation.AnimationTimeline> Klasse ab, und überschreiben Sie die folgenden Member:  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A> – wenn die neue Klasse konkret ist, müssen Sie <xref:System.Windows.Freezable.CreateInstanceCore%2A> überschreiben, um eine neue Instanz der Klasse zurückzugeben.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> – überschreiben Sie diese Methode, um den aktuellen Wert der Animation zurückzugeben. Es werden drei Parameter benötigt: ein Standardwert für den Ursprung, ein Standardzielwert und ein <xref:System.Windows.Media.Animation.AnimationClock>. Verwenden Sie die <xref:System.Windows.Media.Animation.AnimationClock>, um die aktuelle Uhrzeit oder den Fortschritt der Animation abzurufen. Sie können auswählen, ob die Standardursprungs- oder zielwerte verwendet werden.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> – überschreiben Sie diese Eigenschaft, um anzugeben, ob die Animation den von der <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>-Methode angegebenen Standard Zielwert verwendet.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> – überschreiben Sie diese Eigenschaft, um die <xref:System.Type> der Ausgabe anzugeben, die Ihre Animation erzeugt.  
  
 Wenn die Klasse keine Abhängigkeitseigenschaften zum Speichern von Daten nutzt oder nach der Erstellung eine zusätzliche Initialisierung erfordert, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Das empfohlene Paradigma (verwendet von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationen) besteht in der Verwendung von zwei Vererbungsebenen:  
  
1. Erstellen Sie einen abstrakten *\<Typ >* AnimationBase-Klasse, die von <xref:System.Windows.Media.Animation.AnimationTimeline>abgeleitet ist. Diese Klasse sollte die <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>-Methode überschreiben. Außerdem sollte eine neue abstrakte Methode, GetCurrentValueCore, eingeführt und <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> überschrieben werden, damit die Typen der Standard Ursprungs Werte und Standardzielwert-Parameter überprüft werden und dann GetCurrentValueCore aufgerufen wird.  
  
2. Erstellen Sie eine weitere Klasse, die von Ihrem neuen *\<Typ >* AnimationBase-Klasse erbt, und überschreibt die <xref:System.Windows.Freezable.CreateInstanceCore%2A>-Methode, die von Ihnen eingeführte GetCurrentValueCore-Methode und die <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>-Eigenschaft.  
  
 **Alternative Ansätze**  
  
 Wenn Sie einen Typ animieren möchten, der keine entsprechende from/to/by-Animation oder Keyframe-Animation aufweist, sollten Sie eine <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>verwenden. Da es schwach typisiert ist, kann ein <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> jeden Werttyp animieren. Der Nachteil dieses Ansatzes besteht darin, dass <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> nur diskrete Interpolationen unterstützt.  
  
<a name="useperframecallback"></a>   
## <a name="use-per-frame-callback"></a>Verwenden eines Pro-Frame-Rückrufs  
 Verwenden Sie diesen Ansatz, wenn Sie das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystem vollständig umgehen müssen. Ein Szenario für diesen Ansatz sind Animationen in der Physik. Hier muss bei jedem Animationsschritt basierend auf dem letzten Satz von Objektinteraktionen eine neue Richtung oder Position des animierten Objekts berechnet werden.  
  
 **Implementierungsanweisungen**  
  
 Im Gegensatz zu den anderen in dieser Übersicht beschriebenen Methoden müssen Sie bei der Verwendung von Pro-Frame-Rückrufen keine benutzerdefinierte Animation oder Keyframe-Klasse erstellen.  
  
 Stattdessen registrieren Sie sich für das <xref:System.Windows.Media.CompositionTarget.Rendering>-Ereignis des Objekts, das die Objekte enthält, die Sie animieren möchten. Diese Ereignishandlermethode wird einmal pro Frame aufgerufen. Immer wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der visuellen Struktur für die Kompositionsstruktur marshallt, wird die Ereignishandlermethode aufgerufen.  
  
 Führen Sie im Ereignishandler alle für den Animationseffekt erforderlichen Berechnungen durch, und legen Sie die Eigenschaften der Objekte fest, die Sie mit diesen Werten animieren möchten.  
  
 Um die Präsentationszeit des aktuellen Frames zu erhalten, können die diesem Ereignis zugeordneten <xref:System.EventArgs> in <xref:System.Windows.Media.RenderingEventArgs>umgewandelt werden, die eine <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> Eigenschaft bereitstellen, mit der Sie die Renderingzeit des aktuellen Frames abrufen können.  
  
 Weitere Informationen finden Sie auf der Seite <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.IKeyFrame>
- [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Übersicht über Pfadanimationen](path-animations-overview.md)
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)
- [Benutzerdefiniertes Animationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
