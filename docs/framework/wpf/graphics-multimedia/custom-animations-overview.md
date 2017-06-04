---
title: "&#220;bersicht &#252;ber benutzerdefinierte Animationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Animation, Benutzerdefinierte Klassen"
  - "Benutzerdefinierte Animationsklassen"
  - "Benutzerdefinierte Klassen, Animation"
  - "Benutzerdefinierte Keyframes"
  - "Keyframes, Benutzerdefiniert"
ms.assetid: 9be69d50-3384-4938-886f-08ce00e4a7a6
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber benutzerdefinierte Animationen
In diesem Thema wird beschrieben, wie und wann das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationssystem durch Erstellen benutzerdefinierter Keyframes oder Animationsklassen erweitert wird oder mithilfe von Pro\-Frame\-Rückrufen umgangen wird.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 Für dieses Thema sollten Sie mit den verschiedenen Animationstypen vertraut sein, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt werden.  Weitere Informationen finden Sie unter [Übersicht über From\/To\/By\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md), [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) und [Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 Weil die Animationsklassen von der <xref:System.Windows.Freezable>\-Klasse erben, sollten Sie mit <xref:System.Windows.Freezable>\-Objekten und den Möglichkeiten der Vererbung von <xref:System.Windows.Freezable> vertraut sein.  Weitere Informationen finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>   
## Erweitern des Animationssystems  
 Je nach der integrierten Funktionalitätsebene, die Sie verwenden möchten, gibt es mehrere Möglichkeiten zur Erweiterung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationssystems.  Im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationsmodul gibt es drei primäre Erweiterungspunkte:  
  
-   Erstellen Sie ein benutzerdefiniertes Keyframeobjekt durch Vererbung von einer der *\<Typ\>*KeyFrame\-Klassen, z. B. <xref:System.Windows.Media.Animation.DoubleKeyFrame>.  Bei diesem Ansatz werden die meisten der integrierten Funktionen des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationsmoduls verwendet.  
  
-   Erstellen Sie eine eigene Animationsklasse durch Vererbung von <xref:System.Windows.Media.Animation.AnimationTimeline> oder von einer der *\<Typ\>*AnimationBase\-Klassen.  
  
-   Generieren Sie durch Pro\-Frame\-Rückrufe Animationen auf einer Pro\-Frame\-Basis.  Bei diesem Ansatz wird das Animations\- und Zeitsteuerungssystem völlig umgangen.  
  
 In der folgenden Tabelle werden einige der Szenarien zur Erweiterung des Animationssystems beschrieben.  
  
|Aktion|Vorgehensweise|  
|------------|--------------------|  
|Anpassen der Interpolation zwischen Werten eines Typs mit einer entsprechenden *\<Typ\>*AnimationUsingKeyFrames\-Klasse|Erstellen Sie einen benutzerdefinierten Keyframe.  Weitere Informationen finden Sie im Abschnitt [Erstellen eines benutzerdefinierten Keyframes](#createacustomkeyframe).|  
|Anpassen nicht nur der Interpolation zwischen Werten eines Typs mit entsprechender *\<Typ\>*Animation\-Klasse.|Erstellen Sie eine benutzerdefinierte Animationsklasse, die von der *\<Typ\>*AnimationBase\-Klasse erbt, die dem zu animierenden Typ entspricht.  Weitere Informationen finden Sie im Abschnitt [Erstellen einer benutzerdefinierten Animationsklasse](#createcustomanimationtype).|  
|Animieren eines Typs ohne entsprechende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animation|Verwenden Sie <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>, oder erstellen Sie eine Klasse, die von <xref:System.Windows.Media.Animation.AnimationTimeline> erbt.  Weitere Informationen finden Sie im Abschnitt [Erstellen einer benutzerdefinierten Animationsklasse](#createcustomanimationtype).|  
|Animieren mehrerer Objekte mit Werten, die pro Frame berechnet werden und auf dem letzten Satz von Objektinteraktionen basieren|Verwenden Sie Pro\-Frame\-Rückrufe.  Weitere Informationen finden Sie im Abschnitt [Verwenden eines Pro\-Frame\-Rückrufs](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## Erstellen eines benutzerdefinierten Keyframes  
 Die einfachste Möglichkeit zur Erweiterung des Animationssystems ist das Erstellen einer benutzerdefinierten Keyframeklasse.  Verwenden Sie diesen Ansatz, wenn Sie eine andere Interpolationsmethode für eine Keyframeanimation verwenden möchten.  Wie in [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) beschrieben ist, verwendet eine Keyframeanimation Keyframeobjekte, um die Ausgabewerte zu generieren.  Jedes Keyframeobjekt hat drei Funktionen:  
  
-   Angeben eines Zielwerts mithilfe der <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>\-Eigenschaft  
  
-   Angeben der Zeit, zu der der Wert erreicht sein soll, mithilfe der <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>\-Eigenschaft  
  
-   Interpolieren zwischen dem Wert des vorherigen Keyframes und dem eigenen Wert durch Implementieren der InterpolateValueCore\-Methode  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von der abstrakten *\<Typ\>*KeyFrame\-Klasse ab, und implementieren Sie die InterpolateValueCore\-Methode.  Die InterpolateValueCore\-Methode gibt den aktuellen Wert des Keyframes zurück.  Es werden zwei Parameter übernommen: der Wert des vorherigen Keyframes und ein Fortschrittswert zwischen 0 und 1.  Der Fortschrittswert 0 gibt an, dass der Keyframe gerade gestartet wurde. Der Wert 1 gibt an, dass der Keyframe gerade abgeschlossen wurde und den von der entsprechenden <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>\-Eigenschaft festgelegten Wert zurückgeben sollte.  
  
 Da die *\<Typ\>*KeyFrame\-Klassen von der <xref:System.Windows.Freezable>\-Klasse erben, müssen Sie auch den <xref:System.Windows.Freezable.CreateInstanceCore%2A>\-Kern überschreiben, damit eine neue Instanz der Klasse zurückgegeben wird.  Falls die Klasse zur Speicherung der Daten keine [Abhängigkeitseigenschaften](GTMT) verwendet oder nach der Erstellung eine zusätzliche Initialisierung erforderlich ist, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Nachdem Sie die benutzerdefinierte *\<Typ\>*KeyFrame\-Animation erstellt haben, können Sie diese gemeinsam mit *\<Typ\>*AnimationUsingKeyFrames für diesen Typ verwenden.  
  
<a name="createacustomanimationtype"></a>   
## Erstellen einer benutzerdefinierten Animationsklasse  
 Durch Erstellen eines eigenen Animationstyps können Sie besser steuern, wie ein Objekt animiert wird.  Zum Erstellen eines eigenen Animationstyps werden zwei Möglichkeiten empfohlen: Sie können von der <xref:System.Windows.Media.Animation.AnimationTimeline>\-Klasse oder von der *\<Typ\>*AnimationBase\-Klasse ableiten.  Es wird davon abgeraten, von der *\<Typ\>*Animation\-Klasse oder von der *\<Typ\>*AnimationUsingKeyFrames\-Klasse abzuleiten.  
  
### Ableiten von \<Typ\>AnimationBase  
 Die Ableitung von einer *\<Typ\>*AnimationBase\-Klasse ist die einfachste Methode zur Erstellung eines neuen Animationstyps.  Verwenden Sie diesen Ansatz, wenn Sie eine neue Animation für einen Typ erstellen möchten, der bereits über eine entsprechende *\<Typ\>*AnimationBase\-Klasse verfügt.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von einer *\<Typ\>*Animation\-Klasse ab, und implementieren Sie die GetCurrentValueCore\-Methode.  Die GetCurrentValueCore\-Methode gibt den aktuellen Wert der Animation zurück.  Es werden drei Parameter übernommen: ein vorgeschlagener Anfangswert, ein vorgeschlagener Endwert und <xref:System.Windows.Media.Animation.AnimationClock>. Damit bestimmen Sie den Fortschritt der Animation.  
  
 Da die *\<Typ\>*AnimationBase\-Klassen von der <xref:System.Windows.Freezable>\-Klasse erben, müssen Sie auch den <xref:System.Windows.Freezable.CreateInstanceCore%2A>\-Kern überschreiben, damit eine neue Instanz der Klasse zurückgegeben wird.  Falls die Klasse zur Speicherung der Daten keine [Abhängigkeitseigenschaften](GTMT) verwendet oder nach der Erstellung eine zusätzliche Initialisierung erforderlich ist, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Weitere Informationen finden Sie in der Dokumentation zur GetCurrentValueCore\-Methode für die *\<Typ\>*AnimationBase\-Klasse des zu animierenden Typs.  Ein Beispiel hierfür finden Sie unter [Beispiel für benutzerdefinierte Animation](http://go.microsoft.com/fwlink/?LinkID=159981)  
  
 **Alternative Ansätze**  
  
 Wenn Sie lediglich die Art der Interpolation von Animationswerten ändern möchten, kommt eine Ableitung von einer der *\<Typ\>*KeyFrame\-Klassen infrage.  Der von Ihnen erstellte Keyframe kann mit den entsprechenden *\<Typ\>*AnimationUsingKeyFrames verwendet werden, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt werden.  
  
### Ableiten von AnimationTimeline  
 Leiten Sie von der <xref:System.Windows.Media.Animation.AnimationTimeline>\-Klasse ab, wenn Sie eine Animation für einen Typ erstellen möchten, der noch nicht über eine entsprechende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animation verfügt, oder wenn Sie eine Animation ohne starke Typisierung erstellen möchten.  
  
 **Implementierungsanweisungen**  
  
 Leiten Sie von der <xref:System.Windows.Media.Animation.AnimationTimeline>\-Klasse ab, und überschreiben Sie die folgenden Member:  
  
-   <xref:System.Windows.Freezable.CreateInstanceCore%2A> – Wenn es sich bei der neuen Klasse um eine konkrete Klasse handelt, müssen Sie <xref:System.Windows.Freezable.CreateInstanceCore%2A> überschreiben, damit eine neue Instanz der Klasse zurückgegeben wird.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> – Überschreiben Sie diese Methode, damit der aktuelle Wert der Animation zurückgegeben wird.  Übernommen werden drei Parameter: ein Standardursprungswert, ein Standardzielwert und ein <xref:System.Windows.Media.Animation.AnimationClock>\-Wert.  Verwenden Sie <xref:System.Windows.Media.Animation.AnimationClock>, um die aktuelle Zeit oder den Fortschritt für die Animation abzurufen.  Sie können festlegen, ob die Standardursprungs\- und \-zielwerte verwendet werden.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> – Überschreiben Sie diese Eigenschaft, um anzugeben, ob die Animation den von der <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>\-Methode angegebenen Standardzielwert verwendet.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> – Überschreiben Sie diese Eigenschaft, um den <xref:System.Type> von der Animation erzeugten Ausgabe anzugeben.  
  
 Falls die Klasse zur Speicherung der Daten keine [Abhängigkeitseigenschaften](GTMT) verwendet oder nach der Erstellung eine zusätzliche Initialisierung erforderlich ist, müssen Sie möglicherweise zusätzliche Methoden überschreiben. Weitere Informationen finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Das empfohlene Paradigma \(es wird von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationen verwendet\) besteht in der Verwendung von zwei Vererbungsebenen:  
  
1.  Erstellen Sie eine abstrakte *\<Type\>*AnimationBase\-Klasse, die von <xref:System.Windows.Media.Animation.AnimationTimeline> abgeleitet wird.  Diese Klasse sollte die <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>\-Methode überschreiben.  Darüber hinaus sollte sie eine neue abstrakte Methode \(GetCurrentValueCore\) einführen und <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> überschreiben, um die Typen der Parameter des Standardursprungswerts und des Standardzielwerts zu überprüfen. Anschließend ruft sie GetCurrentValueCore auf.  
  
2.  Erstellen Sie eine weitere Klasse, die von der neuen *\<Type\>*AnimationBase\-Klasse erbt und die <xref:System.Windows.Freezable.CreateInstanceCore%2A>\-Methode, die von Ihnen eingeführte GetCurrentValueCore\-Methode sowie die <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>\-Eigenschaft überschreibt.  
  
 **Alternative Ansätze**  
  
 Wenn Sie einen Typ ohne entsprechende From\/To\/By\-Animation oder Keyframeanimation erstellen möchten, sollten Sie <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> verwenden.  Da <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> schwach typisiert ist, lassen sich damit sämtliche Typen von Werten animieren.  Der Nachteil dieses Ansatzes ist, dass <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> nur die [diskrete Interpolation](GTMT) unterstützt.  
  
<a name="useperframecallback"></a>   
## Verwenden eines Pro\-Frame\-Rückrufs  
 Verwenden Sie diesen Ansatz, wenn Sie das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationssystem vollständig umgehen müssen.  Ein Szenario für diesen Ansatz sind Animationen in der Physik. Hier muss bei jedem Animationsschritt basierend auf dem letzten Satz von Objektinteraktionen eine neue Richtung oder Position des animierten Objekts berechnet werden.  
  
 **Implementierungsanweisungen**  
  
 Anders als bei den anderen in dieser Übersicht beschriebenen Ansätzen brauchen Sie zur Verwendung von Pro\-Frame\-Rückrufen keine benutzerdefinierte Animation oder Keyframeklasse zu erstellen.  
  
 Stattdessen registrieren Sie sich für das <xref:System.Windows.Media.CompositionTarget.Rendering>\-Ereignis des Objekts, das die zu animierenden Objekte enthält.  Diese Ereignishandlermethode wird einmal pro Frame aufgerufen.  Immer wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der [visuellen Struktur](GTMT) für die Kompositionsstruktur marshallt, wird die Ereignishandlermethode aufgerufen.  
  
 Führen Sie im Ereignishandler alle für den Animationseffekt erforderlichen Berechnungen durch, und legen Sie die Eigenschaften der Objekte fest, die mit diesen Werten animiert werden sollen.  
  
 Um die Präsentationszeit des aktuellen Frames abzurufen, können die diesem Ereignis zugewiesenen <xref:System.EventArgs> in <xref:System.Windows.Media.RenderingEventArgs> umgewandelt werden. Hierdurch wird eine <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A>\-Eigenschaft bereitgestellt, mit deren Hilfe Sie die Renderingzeit des aktuellen Frames abrufen können.  
  
 Weitere Informationen finden Sie auf der Seite <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.AnimationTimeline>   
 <xref:System.Windows.Media.Animation.IKeyFrame>   
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Übersicht über From\/To\/By\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md)   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über das Animations\- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Beispiel für benutzerdefinierte Animation](http://go.microsoft.com/fwlink/?LinkID=159981)