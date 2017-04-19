---
title: "Richtlinien zum Entwerfen formatierbarer Steuerelemente | Microsoft Docs"
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
  - "Steuerelemente, Formatentwurf"
  - "Formatentwurf für Steuerelemente"
ms.assetid: c52dde45-a311-4531-af4c-853371c4d5f4
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Richtlinien zum Entwerfen formatierbarer Steuerelemente
In diesem Dokument werden die bewährten Methoden zusammengefasst, die beim Entwickeln eines Steuerelements zu berücksichtigen sind, das Sie auf einfache Weise formatieren und als Vorlage verwenden möchten.  Diese bewährten Methoden sind während der Arbeit an den Formatvorlagen für Designsteuerelemente für die integrierte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelementgruppe durch Versuch und Irrtum zusammengestellt worden.  Es hat sich gezeigt, dass eine erfolgreiche Formatierung sowohl eine Funktion eines gut entworfenen Objektmodells als auch des eigentlichen Stils darstellt.  Dieses Dokument richtet sich an Autoren von Steuerelementen und nicht an Autoren von Stilen.  
  
   
  
<a name="Terminology"></a>   
## Terminologie  
 "Formatierung und Vorlagen" bezieht sich auf die Suite von Technologien, die es einem Autor von Steuerelementen ermöglichen, die visuellen Aspekte des Steuerelements erst bei Stil und Vorlage des Steuerelements zu berücksichtigen.  Diese Suite von Technologien umfasst:  
  
-   Stile \(einschließlich Eigenschaftensetter, Trigger und Storyboards\)  
  
-   Ressourcen  
  
-   Steuerelementvorlagen  
  
-   Datenvorlagen  
  
 Eine Einführung in Formatierung und Vorlagen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="Before_You_Start__Understanding_Your_Control"></a>   
## Vor dem Start: Verstehen des Steuerelements  
 Bevor Sie sich mit diesen Richtlinien beschäftigen, sollten Sie die typische Verwendung des Steuerelements verstanden und definiert haben.  Beim Formatieren stehen häufig zahlreiche Möglichkeiten zur Verfügung.  Bei Steuerelementen, die für eine allgemeine Verwendung \(in vielen Anwendungen, von vielen Entwicklern\) geschrieben werden, kann die visuelle Darstellung des Steuerelements durch Formatierungen grundlegend geändert werden.  Möglicherweise hat das formatierte Steuerelement keinerlei Ähnlichkeit mehr mit dem vom Autor geplanten Steuerelement.  Da die Flexibilität der Formatierung nahezu grenzenlos ist, können Sie Ihre Entscheidungen auf der Grundlage der typischen Verwendung treffen.  
  
 Um die typische Verwendung des Steuerelements zu verstehen, sollten Sie über die Vorteile des Steuerelements nachdenken.  Was trägt das Steuerelement zur Tabelle bei, das kein anderes Steuerelement anbieten kann?  Die typische Verwendung setzt keine bestimmte visuelle Darstellung voraus. Es geht vielmehr um die Philosophie des Steuerelements und um realistische Erwartungen hinsichtlich der Verwendung.  Mithilfe dieser Kenntnisse können Sie Vermutungen über das Kompositionsmodell und das formatdefinierte Verhalten des Steuerelements in der typischen Verwendung anstellen.  Bei einem <xref:System.Windows.Controls.ComboBox> gibt Ihnen das Verständnis der typischen Anwendung keinen Aufschluss darüber, ob ein bestimmtes <xref:System.Windows.Controls.ComboBox> abgerundete Ecken aufweist. Es zeigt Ihnen jedoch, dass das <xref:System.Windows.Controls.ComboBox> vermutlich ein Popupfenster und Elemente zum Umschalten benötigt.  
  
<a name="General_Guidelines"></a>   
## Allgemeine Richtlinien  
  
-   **Setzen Sie Vorlagenverträge nicht strikt durch.** Der Vorlagenvertrag eines Steuerelements kann aus Elementen, Befehlen, Bindungen, Triggern oder auch Eigenschafteneinstellungen bestehen, die für die ordnungsgemäße Funktionsweise eines Steuerelements erforderlich sind oder erwartet werden.  
  
    -   Minimieren Sie Verträge so weit wie möglich.  
  
    -   Gehen Sie beim Entwurf von der Annahme aus, dass sich eine Steuerelementvorlage zur Entwurfszeit \(d. h. beim Verwenden eines Entwurftools\) häufig in einem unvollständigen Zustand befindet.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet keine Zustandsinfrastruktur für die Erstellung. Deshalb muss bei der Erstellung von Steuerelementen davon ausgegangen werden, dass ein solcher Zustand gültig sein kann.  
  
    -   Lösen Sie keine Ausnahmen aus, wenn ein Aspekt eines Vorlagenvertrags nicht beachtet wird.  Dementsprechend sollten Bereiche keine Ausnahmen auslösen, wenn sie zu viele oder zu wenige untergeordnete Elemente aufweisen.  
  
-   **Unterteilen Sie die periphere Funktionalität in Vorlagenhilfselemente.** Der Schwerpunkt jedes Steuerelements sollte auf der Basisfunktionalität sowie den wirklichen Vorteilen liegen, und die Definition sollte auf der typischen Verwendung des Steuerelements basieren.  Verwenden Sie dazu Kompositions\- und Hilfselemente in der Vorlage, um Peripherieverhalten und \-darstellungen zu aktivieren, d. h., Verhalten und Darstellungen, die nicht zur Basisfunktionalität des Steuerelements beitragen.  Hilfselemente lassen sich in drei Kategorien einteilen:  
  
    -   **Eigenständige** Hilfstypen sind öffentliche und wieder verwendbare Steuerelemente oder Primitiven, die in einer Vorlage "anonym" verwendet werden, sodass weder das Hilfselement noch das formatierte Steuerelement das jeweils andere Element bemerkt.  Technisch gesehen kann jedes Element anonym sein, aber in diesem Kontext beschreibt dieser Begriff die Typen, die spezialisierte Funktionalität kapseln, um Zielszenarien zu aktivieren.  
  
    -   **Typbasierte** Hilfselemente sind neue Typen, die spezialisierte Funktionalität kapseln.  Diese Elemente werden in der Regel mit einer geringeren Bandbreite an Funktionalität entworfen als allgemeine Steuerelemente oder Primitive.  Im Gegensatz zu eigenständigen Hilfselementen erkennen typbasierte Hilfselemente den Kontext, in dem sie verwendet werden, und müssen in der Regel die Daten mit dem Steuerelement gemeinsam nutzen, zu dessen Vorlage sie gehören.  
  
    -   **Benannt** Hilfselemente sind allgemeine Steuerelemente oder Primitive, nach denen ein Steuerelement anhand des Namens in der Vorlage sucht. Diese Elemente erhalten einen bekannten Namen in der Vorlage, damit das Steuerelement das Element finden und programmgesteuert mit ihm interagieren kann.  In jeder Vorlage kann es nur ein Element mit einem bestimmten Namen geben.  
  
     In der folgenden Tabelle werden die Hilfselemente aufgelistet, die derzeit von Steuerelementen verwendet werden \(diese Liste ist nicht vollständig\):  
  
    |Element|Typ|Verwendet von|  
    |-------------|---------|-------------------|  
    |<xref:System.Windows.Controls.ContentPresenter>|Typbasiert|<xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.Frame> usw. \(alle <xref:System.Windows.Controls.ContentControl>\-Typen\)|  
    |<xref:System.Windows.Controls.ItemsPresenter>|Typbasiert|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu> usw. \(alle <xref:System.Windows.Controls.ItemsControl>\-Typen\)|  
    |<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Benannt|<xref:System.Windows.Controls.ToolBar>|  
    |<xref:System.Windows.Controls.Primitives.Popup>|Eigenständig|<xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ToolBar>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolTip> usw.|  
    |<xref:System.Windows.Controls.Primitives.RepeatButton>|Benannt|<xref:System.Windows.Controls.Slider>, <xref:System.Windows.Controls.Primitives.ScrollBar> usw.|  
    |<xref:System.Windows.Controls.Primitives.ScrollBar>|Benannt|<xref:System.Windows.Controls.ScrollViewer>|  
    |<xref:System.Windows.Controls.ScrollViewer>|Eigenständig|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.Frame> usw.|  
    |<xref:System.Windows.Controls.Primitives.TabPanel>|Eigenständig|<xref:System.Windows.Controls.TabControl>|  
    |<xref:System.Windows.Controls.TextBox>|Benannt|<xref:System.Windows.Controls.ComboBox>|  
    |<xref:System.Windows.Controls.Primitives.TickBar>|Typbasiert|<xref:System.Windows.Controls.Slider>|  
  
-   **Minimieren Sie erforderliche vom Benutzer angegebene Bindungen oder Eigenschafteneinstellungen für Hilfselemente**.  Für Hilfselemente sind in der Regel bestimmte Bindungen oder Eigenschafteneinstellungen erforderlich, damit sie in der Steuerelementvorlage ordnungsgemäß funktionieren.  Das Hilfselement und das Steuerelement mit Vorlagen sollten diese Einstellungen so weit wie möglich festlegen.  Beim Festlegen von Eigenschaften oder Bindungen muss darauf geachtet werden, dass keine vom Benutzer festgelegten Werte überschrieben werden.  Bestimmte bewährte Methoden lauten wie folgt:  
  
    -   Benannte Hilfselemente sollten durch das übergeordnete Element identifiziert werden, und das übergeordnete Element sollte alle erforderlichen Einstellungen für das Hilfselement vornehmen.  
  
    -   Typbasierte Hilfselemente sollten alle erforderlichen Einstellungen unmittelbar selbst vornehmen.  Dazu muss das Hilfselement möglicherweise Informationskontext abfragen, in dem es verwendet wird, einschließlich `TemplatedParent` \(der Steuerelementtyp der Vorlage, in dem es verwendet wird\).  <xref:System.Windows.Controls.ContentPresenter> bindet beispielsweise automatisch die `Content`\-Eigenschaft für sein `TemplatedParent` an seine <xref:System.Windows.Controls.ContentPresenter.Content%2A>\-Eigenschaft, wenn die Verwendung in einem von <xref:System.Windows.Controls.ContentControl> abgeleiteten Typ erfolgt.  
  
    -   Eigenständige Hilfselemente können nicht auf diese Weise optimiert werden, da per Definition weder das Hilfselement noch das übergeordnete Element das jeweils andere Element bemerkt.  
  
-   **Verwenden Sie die Name\-Eigenschaft, um Elemente innerhalb einer Vorlage zu kennzeichnen**.  Ein Steuerelement, das ein Element in seinem Stil finden muss, um programmgesteuert darauf zuzugreifen, sollte dazu die `Name`\-Eigenschaft und das `FindName`\-Paradigma verwenden.  Ein Steuerelement sollte keine Ausnahme auslösen, wenn ein Element nicht gefunden wird. Stattdessen sollte die Funktionalität, die dieses Element erfordert, automatisch und ordnungsgemäß deaktiviert werden.  
  
-   **Verwenden Sie die bewährten Methoden, um Zustand und Verhalten des Steuerelements in einem Stil auszudrücken.** Es folgt eine sortierte Liste der bewährten Methoden, um Änderungen an Zustand und Verhalten des Steuerelements in einem Stil auszudrücken.  Verwenden Sie das erste Element aus der Liste, das das Szenario aktiviert.  
  
    1.  Eigenschaftenbindung.  Beispiel: Bindung zwischen <xref:System.Windows.Controls.ComboBox.IsDropDownOpen%2A?displayProperty=fullName> und <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A?displayProperty=fullName>.  
  
    2.  Ausgelöste Eigenschaftenänderungen oder Eigenschaftenanimationen.  Beispiel: Der Hoverzustand eines <xref:System.Windows.Controls.Button>.  
  
    3.  Befehl.  Beispiel: <xref:System.Windows.Controls.Primitives.ScrollBar.LineUpCommand>\/<xref:System.Windows.Controls.Primitives.ScrollBar.LineDownCommand> in <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
    4.  Eigenständige Hilfselemente.  Beispiel: <xref:System.Windows.Controls.Primitives.TabPanel> in <xref:System.Windows.Controls.TabControl>.  
  
    5.  Typbasierte Hilfstypen.  Beispiel: <xref:System.Windows.Controls.ContentPresenter> in <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Primitives.TickBar> in <xref:System.Windows.Controls.Slider>.  
  
    6.  Benannte Hilfselemente.  Beispiel: <xref:System.Windows.Controls.TextBox> in <xref:System.Windows.Controls.ComboBox>.  
  
    7.  Bubbled\-Ereignisse aus benannten Hilfstypen.  Wenn Sie Bubbled\-Ereignisse aus einem Stilelement überwachen, fordern Sie an, dass das Element, das das Ereignis generiert, eindeutig identifiziert werden kann.  Beispiel: <xref:System.Windows.Controls.Primitives.Thumb> in <xref:System.Windows.Controls.ToolBar>.  
  
    8.  Benutzerdefiniertes `OnRender`\-Verhalten.  Beispiel: <xref:Microsoft.Windows.Themes.ButtonChrome> in <xref:System.Windows.Controls.Button>.  
  
-   **Verwenden Sie Stiltrigger \(im Gegensatz zu Vorlagentriggern\) sparsam**.  Trigger, die Eigenschaften für Elemente in der Vorlage beeinflussen, müssen in der Vorlage deklariert werden.  Trigger, die Eigenschaften für das Steuerelement \(kein `TargetName`\) beeinflussen, können im Stil deklariert werden, sofern bekannt ist, dass beim Ändern der Vorlage auch der Trigger zerstört wird.  
  
-   **Bleiben Sie mit vorhandenen Formatierungsmustern konsistent.** Oft gibt es mehrere Möglichkeiten, ein Problem zu lösen.  Beachten Sie dies, und bleiben Sie nach Möglichkeit mit den vorhandenen Formatierungsmustern für Steuerelemente konsistent.  Dies ist besonders bei Steuerelementen wichtig, die von demselben Basistyp abgeleitet werden \(beispielsweise <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.Primitives.RangeBase> usw.\).  
  
-   **Machen Sie Eigenschaften verfügbar, um allgemeine Anpassungsszenarien ohne eine erneute Vorlagenerstellung zu aktivieren**.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt keine austauschbaren\/anpassbaren Teile. Steuerelementbenutzer stehen daher nur zwei Möglichkeiten der Anpassung zur Verfügung: direktes Festlegen der Eigenschaften oder Festlegen der Eigenschaften mithilfe von Stilen.  Daher ist es angemessen, eine begrenzte Anzahl Eigenschaften für sehr allgemeine Anpassungsszenarien mit hoher Priorität festzulegen, für die ansonsten eine erneute Vorlagenerstellung erforderlich wäre.  Es folgen bewährte Methoden, die angeben, wann und wie Anpassungsszenarien aktiviert werden sollen:  
  
    -   Sehr allgemeine Anpassungen sollten als Eigenschaften für das Steuerelement verfügbar gemacht und von der Vorlage verwendet werden.  
  
    -   Weniger allgemeine \(obwohl nicht seltene\) Anpassungen sollten als angefügte Eigenschaften verfügbar gemacht und von der Vorlage verwendet werden.  
  
    -   Es ist zulässig, dass für bekannte \(aber seltene\) Anpassungen eine erneute Vorlagenerstellung erforderlich wird.  
  
<a name="Theme_Considerations"></a>   
## Designüberlegungen  
  
-   **Designstile sollten designübergreifend eine konsistente Eigenschaftensemantik aufweisen. Eine Garantie ist jedoch nicht möglich**.  Die Dokumentation des Steuerelements sollte ein Dokument enthalten, das die Eigenschaftensemantik des Steuerelements beschreibt, d. h. die Bedeutung einer Eigenschaft für ein Steuerelement.  Zum Beispiel sollte das <xref:System.Windows.Controls.ComboBox>\-Steuerelement die Bedeutung der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft für <xref:System.Windows.Controls.ComboBox> definieren.  Die Standardstile für das Steuerelement sollten die in diesem Dokument definierte Semantik designübergreifend befolgen.  Steuerelementbenutzer sollten sich jedoch der Tatsache bewusst sein, dass die Eigenschaftensemantik je nach Design variieren kann.  In manchen Fällen lässt sich eine bestimmte Eigenschaft wegen visueller Einschränkungen, die ein bestimmtes Design erfordert, möglicherweise nicht ausdrücken.  \(Das Design Classic verfügt z. B. über keinen Einzelrahmen, auf den `Thickness` für viele Steuerelemente angewendet werden kann.\)  
  
-   **Designstile müssen keine designübergreifende konsistente Triggersemantik aufweisen**.  Das durch Trigger von einem Steuerelementformat verfügbar gemachte Verhalten oder Animationen können je nach Design variieren.  Steuerelementbenutzer sollten sich der Tatsache bewusst sein, dass ein Steuerelement nicht in allen Designs denselben Mechanismus einsetzt, um ein bestimmtes Verhalten zu erzielen.  In einem Design wird Hoververhalten möglicherweise mit einer Animation ausgedrückt, während in einem anderen Design ein Trigger verwendet wird.  Dies kann beim Beibehalten des Verhaltens für angepasste Steuerelemente zu Inkonsistenzen führen.  \(Das Ändern der Eigenschaft für den Hintergrund wirkt sich möglicherweise nicht auf den Hoverzustand des Steuerelements aus, wenn der Zustand mit einem Trigger ausgedrückt wird.  Wenn der Hoverzustand jedoch mit einer Animation implementiert wurde, kann eine Änderung des Hintergrunds die Animation und damit auch den Zustandsübergang irreparabel beschädigen.\)  
  
-   **Designstile müssen keine designübergreifende konsistente "Layoutsemantik" aufweisen**.  Für den Standardstil ist z. B. keine Garantie erforderlich, dass ein Steuerelement in allen Designs dieselbe Größe einnimmt oder in allen Designs dieselben Inhaltsränder\/Abstände aufweist.  
  
## Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md)