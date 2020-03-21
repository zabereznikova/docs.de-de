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
ms.openlocfilehash: c5f315992e8ae37bc79602e6986d90e7af591fb2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186551"
---
# <a name="custom-animations-overview"></a>Übersicht über benutzerdefinierte Animationen
In diesem Thema wird beschrieben, wie und wann das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystem durch Erstellen benutzerdefinierter Keyframes oder Animationsklassen erweitert oder durch Pro-Frame-Rückrufe umgangen wird.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Um dieses Thema zu verstehen, sollten Sie mit den verschiedenen Arten von Animationen vertraut sein, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt werden. Weitere Informationen finden Sie unter Übersicht über die From/To/By-Animationen, [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md) und [Übersicht über Pfadanimationen](path-animations-overview.md).  
  
 Da die Animationsklassen von <xref:System.Windows.Freezable> der Klasse erben, <xref:System.Windows.Freezable> sollten Sie mit Objekten <xref:System.Windows.Freezable>und dem Erben von vertraut sein. Weitere Informationen finden Sie unter der [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>
## <a name="extending-the-animation-system"></a>Erweitern des Animationssystems  
 Es gibt zahlreiche Methoden zum Erweitern des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystems, abhängig von der Ebene der integrierten Funktionen, die Sie verwenden möchten.  Es gibt drei primäre Erweiterungspunkte in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animations-Engine:  
  
- Erstellen Sie ein benutzerdefiniertes Schlüsselrahmenobjekt, * \< *indem Sie von einer <xref:System.Windows.Media.Animation.DoubleKeyFrame>der Type>KeyFrame-Klassen erben, z. B. . Dieser Ansatz verwendet die meisten der integrierten Funktionen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animations-Engine.  
  
- Erstellen Sie eine eigene Animationsklasse, <xref:System.Windows.Media.Animation.AnimationTimeline> indem Sie von einer der * \<Class>* AnimationBase-Klassen erben.  
  
- Verwenden Sie Pro-Frame-Rückruf, um Animationen auf einer Pro-Frame-Basis zu generieren. Bei diesem Ansatz werden die Animations- und Zeitsteuerungssysteme vollständig umgangen.  
  
 In der folgenden Tabelle werden einige die Szenarios zur Erweiterung des Animationssystems beschrieben.  
  
|Aktion|Vorgehensweise|  
|-------------------------|-----------------------|  
|Anpassen der Interpolation zwischen Werten eines * \< *Typs mit einem entsprechenden Typ>AnimationUsingKeyFrames|Erstellen Sie ein benutzerdefiniertes Keyframe. Weitere Informationen finden Sie im Abschnitt [Erstellen eines benutzerdefinierten Keyframe](#createacustomkeyframe).|  
|Passen Sie mehr als nur die Interpolation zwischen * \< *Werten eines Typs an, der über einen entsprechenden Typ>Animation verfügt.|Erstellen Sie eine benutzerdefinierte Animationsklasse, die von der * \<Class Type>* AnimationBase erbt, die dem Typ entspricht, den Sie animieren möchten. Weitere Informationen finden Sie im Abschnitt [Erstellen einer benutzerdefinierten Animationsklasse](#createacustomanimationtype).|  
|Animieren eines Typs, der keine entsprechende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animation besitzt|Verwenden <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> Sie eine Klasse, oder <xref:System.Windows.Media.Animation.AnimationTimeline>erstellen Sie eine Klasse, die von erbt. Weitere Informationen finden Sie im Abschnitt [Erstellen einer benutzerdefinierten Animationsklasse](#createacustomanimationtype).|  
|Animieren mehrerer Objekte mit Werten, die pro Frame berechnet werden und auf dem letzten Satz von Objektinteraktionen basieren|Verwenden Sie einen Pro-Frame-Rückruf. Weitere Informationen finden Sie im Abschnitt [Verwenden eines Pro-Frame-Rückrufs](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>
## <a name="create-a-custom-key-frame"></a>Erstellen eines benutzerdefinierten Keyframes  
 Die einfachste Möglichkeit zum Erweitern des Animationssystems ist das Erstellen einer benutzerdefinierten Keyframe-Klasse. Verwenden Sie diesen Ansatz, wenn Sie eine andere Interpolationsmethode für eine Keyframe-Animation möchten.  Wie in [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md) beschrieben ist, verwendet eine Keyframe-Animation Keyframe-Objekte, um die Ausgabewerte zu generieren. Jedes Keyframe-Objekt hat drei Funktionen:  
  
- Gibt einen Zielwert <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> mithilfe seiner Eigenschaft an.  
  
- Gibt den Zeitpunkt an, zu dem <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> dieser Wert mithilfe seiner Eigenschaft erreicht werden soll.  
  
- Interpoliert zwischen dem Wert des vorherigen Keyframes und dem eigenen Wert durch Implementieren der InterpolateValueCore-Methode.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von der * \<abstrakten Class Type>* KeyFrame ab, und implementieren Sie die InterpolateValueCore-Methode. Die InterpolateValueCore-Methode gibt den aktuellen Wert des Keyframes zurück. Es werden zwei Parameter übernommen: der Wert des vorherigen Keyframes und ein Fortschrittswert, der zwischen 0 und 1 liegt. Ein Fortschritt von 0 gibt an, dass der Schlüsselrahmen gerade gestartet wurde, und der Wert <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 1 gibt an, dass der Schlüsselrahmen gerade abgeschlossen wurde und den von seiner Eigenschaft angegebenen Wert zurückgeben sollte.  
  
 Da * \< *die Type>KeyFrame-Klassen <xref:System.Windows.Freezable> von der Klasse <xref:System.Windows.Freezable.CreateInstanceCore%2A> erben, müssen Sie auch den Kern überschreiben, um eine neue Instanz Ihrer Klasse zurückzugeben. Wenn die Klasse keine Abhängigkeitseigenschaften zum Speichern von Daten nutzt oder nach der Erstellung eine zusätzliche Initialisierung erfordert, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Nachdem Sie Ihre benutzerdefinierte * \<Type->* KeyFrame-Animation erstellt * \< *haben, können Sie sie mit dem Type>AnimationUsingKeyFrames für diesen Typ verwenden.  
  
<a name="createacustomanimationtype"></a>
## <a name="create-a-custom-animation-class"></a>Erstellen einer benutzerdefinierten Animationsklasse  
 Beim Erstellen Ihres eigenen Animationstyps können Sie besser steuern, wie ein Objekt animiert wird. Es gibt zwei empfohlene Möglichkeiten, einen eigenen Animationstyp <xref:System.Windows.Media.Animation.AnimationTimeline> zu erstellen: Sie können von der Klasse oder der * \<Type>* AnimationBase-Klasse ableiten. Das Ableiten * \< *von den * \< *Klassen Type>Animation oder Type>AnimationUsingKeyFrames wird nicht empfohlen.  
  
### <a name="derive-from-typeanimationbase"></a>Ableiten von \<Typ>AnimationBase  
 Das Ableiten * \< *von einer Type>AnimationBase-Klasse ist die einfachste Möglichkeit, einen neuen Animationstyp zu erstellen. Verwenden Sie diesen Ansatz, wenn Sie eine neue Animation * \< *für den Typ erstellen möchten, der bereits über einen entsprechenden Typ>AnimationBase-Klasse verfügt.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie * \< *von einer Type>Animation-Klasse ab, und implementieren Sie die GetCurrentValueCore-Methode. Die GetCurrentValueCore-Methode gibt den aktuellen Wert der Animation zurück. Es werden drei Parameter benötigt: ein vorgeschlagener Startwert, ein vorgeschlagener Endwert und ein <xref:System.Windows.Media.Animation.AnimationClock>, mit dem Sie den Fortschritt der Animation bestimmen.  
  
 Da * \< *die Type>AnimationBase-Klassen <xref:System.Windows.Freezable> von der Klasse <xref:System.Windows.Freezable.CreateInstanceCore%2A> erben, müssen Sie auch den Kern überschreiben, um eine neue Instanz Ihrer Klasse zurückzugeben. Wenn die Klasse keine Abhängigkeitseigenschaften zum Speichern von Daten nutzt oder nach der Erstellung eine zusätzliche Initialisierung erfordert, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Weitere Informationen finden Sie in der GetCurrentValueCore-Methodendokumentation für die * \<Type>* AnimationBase-Klasse für den Typ, den Sie animieren möchten. Ein Beispiel hierfür finden Sie unter [Beispiel für benutzerdefinierte Animation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)  
  
 **Alternative Ansätze**  
  
 Wenn Sie einfach ändern möchten, wie Animationswerte interpoliert werden, * \< *sollten Sie eine Ableitung von einer der Type>KeyFrame-Klassen in Betracht ziehen. Der von Ihnen erstellte Schlüsselrahmen * \< *kann mit dem entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Typ>AnimationUsingKeyFrames von verwendet werden.  
  
### <a name="derive-from-animationtimeline"></a>Ableiten von AnimationTimeline  
 Leiten Sie <xref:System.Windows.Media.Animation.AnimationTimeline> von der Klasse ab, wenn Sie eine Animation für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einen Typ erstellen möchten, der noch nicht über eine übereinstimmende Animation verfügt, oder wenn Sie eine Animation erstellen möchten, die nicht stark typisiert ist.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie <xref:System.Windows.Media.Animation.AnimationTimeline> die Klasse ab, und überschreiben Sie die folgenden Member:  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A>– Wenn Ihre neue Klasse konkret <xref:System.Windows.Freezable.CreateInstanceCore%2A> ist, müssen Sie überschreiben, um eine neue Instanz Ihrer Klasse zurückzugeben.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>– Überschreiben Sie diese Methode, um den aktuellen Wert Ihrer Animation zurückzugeben. Es werden drei Parameter verwendet: ein Standardursprungswert, <xref:System.Windows.Media.Animation.AnimationClock>ein Standardzielwert und ein . Verwenden <xref:System.Windows.Media.Animation.AnimationClock> Sie die, um die aktuelle Uhrzeit oder den aktuellen Fortschritt für die Animation abzubekommen. Sie können auswählen, ob die Standardursprungs- oder zielwerte verwendet werden.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>– Überschreiben Sie diese Eigenschaft, um anzugeben, ob <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> Ihre Animation den von der Methode angegebenen Standardzielwert verwendet.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>– Überschreiben Sie diese <xref:System.Type> Eigenschaft, um die Ausgabe anzuzeigen, die Ihre Animation erzeugt.  
  
 Wenn die Klasse keine Abhängigkeitseigenschaften zum Speichern von Daten nutzt oder nach der Erstellung eine zusätzliche Initialisierung erfordert, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Das empfohlene Paradigma (verwendet von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationen) besteht in der Verwendung von zwei Vererbungsebenen:  
  
1. Erstellen Sie * \< *eine abstrakte Type>AnimationBase-Klasse, die von ableitet. <xref:System.Windows.Media.Animation.AnimationTimeline> Diese Klasse sollte <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> die Methode überschreiben. Außerdem sollte eine neue abstrakte Methode, GetCurrentValueCore, eingeführt und überschrieben <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> werden, sodass die Typen des Standardursprungswerts und der Standardzielwertparameter überprüft werden und dann GetCurrentValueCore aufruft.  
  
2. Erstellen Sie eine weitere Klasse, * \< *die von Der neuen <xref:System.Windows.Freezable.CreateInstanceCore%2A> Type>AnimationBase-Klasse erbt und <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> die Methode, die von Ihnen eingeführte GetCurrentValueCore-Methode und die Eigenschaft überschreibt.  
  
 **Alternative Ansätze**  
  
 Wenn Sie einen Typ animieren möchten, der keine entsprechende Von/To/By-Animation oder Keyframe-Animation enthält, sollten Sie eine <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>verwenden. Da er schwach typisiert <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> ist, kann ein Wert jeder Art von Wert animieren. Der Nachteil dieses Ansatzes <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> ist, dass nur diskrete Interpolation unterstützt wird.  
  
<a name="useperframecallback"></a>
## <a name="use-per-frame-callback"></a>Verwenden eines Pro-Frame-Rückrufs  
 Verwenden Sie diesen Ansatz, wenn Sie das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystem vollständig umgehen müssen. Ein Szenario für diesen Ansatz sind Animationen in der Physik. Hier muss bei jedem Animationsschritt basierend auf dem letzten Satz von Objektinteraktionen eine neue Richtung oder Position des animierten Objekts berechnet werden.  
  
 **Implementierungsanweisungen**  
  
 Im Gegensatz zu den anderen in dieser Übersicht beschriebenen Methoden müssen Sie bei der Verwendung von Pro-Frame-Rückrufen keine benutzerdefinierte Animation oder Keyframe-Klasse erstellen.  
  
 Stattdessen registrieren Sie <xref:System.Windows.Media.CompositionTarget.Rendering> sich für das Ereignis des Objekts, das die Objekte enthält, die Sie animieren möchten. Diese Ereignishandlermethode wird einmal pro Frame aufgerufen. Immer wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der visuellen Struktur für die Kompositionsstruktur marshallt, wird die Ereignishandlermethode aufgerufen.  
  
 Führen Sie im Ereignishandler alle für den Animationseffekt erforderlichen Berechnungen durch, und legen Sie die Eigenschaften der Objekte fest, die Sie mit diesen Werten animieren möchten.  
  
 Um die Präsentationszeit des aktuellen <xref:System.EventArgs> Frames zu erhalten, <xref:System.Windows.Media.RenderingEventArgs>kann der <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> diesem Ereignis zugeordnete als , die eine Eigenschaft bereitstellen, die Sie verwenden können, um die Renderzeit des aktuellen Frames abzuerhalten.  
  
 Weitere Informationen finden <xref:System.Windows.Media.CompositionTarget.Rendering> Sie auf der Seite.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.IKeyFrame>
- [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Übersicht über Pfadanimationen](path-animations-overview.md)
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)
- [Benutzerdefiniertes Animationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
