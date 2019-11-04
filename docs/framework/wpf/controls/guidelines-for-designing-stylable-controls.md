---
title: Richtlinien zum Entwerfen formatierbarer Steuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- style design for controls [WPF]
- controls [WPF], style design
ms.assetid: c52dde45-a311-4531-af4c-853371c4d5f4
ms.openlocfilehash: 0fbb515afbeac05168ced6f0a99f50eb29a5c848
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459658"
---
# <a name="guidelines-for-designing-stylable-controls"></a>Richtlinien zum Entwerfen formatierbarer Steuerelemente

Dieses Dokument fasst eine Reihe bewährter Methoden zusammen, die zu berücksichtigen sind, wenn Sie ein Steuerelement erstellen, das einfach zu formatieren ist und damit bequem Vorlagen damit erstellt werden können. Wir kamen durch Experimentieren zu dieser Reihe bewährter Methoden, während wir an Steuerelementstilen für Designs für die integrierten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente gearbeitet haben. Wir haben gelernt, dass die erfolgreiche Formatierung genau so eine Funktion eines gut strukturierten Objektmodells ist wie für den Stil selbst. Die Zielgruppe für dieses Dokument sind die Autoren des Steuerelements und nicht der Autoren der Stile.

<a name="Terminology"></a>

## <a name="terminology"></a>Terminologie

„Erstellen von Formaten und Vorlagen“ bezieht sich auf die Technologiesuite, mit der Steuerelementautor die visuellen Aspekte des Steuerelements bis zum Stil und der Vorlage des Steuerelements verzögern kann. Diese Technologiesuite enthält:

- Stile (einschließlich Eigenschaftssetter, Trigger und Storyboards).

- Ressourcen.

- Steuerelementvorlagen.

- Datenvorlagen.

Eine Einführung zum Beispiel zu Stilen und Vorlagen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

<a name="Before_You_Start__Understanding_Your_Control"></a>

## <a name="before-you-start-understanding-your-control"></a>Vor dem Start: Verstehen des Steuerelements

Bevor Sie zu diesen Richtlinien springen, ist es wichtig, dass Sie die häufigste Verwendung Ihres Steuerelements verstehen und definiert haben. Stil stellt eine häufig unübersichtliche Palette von Möglichkeiten dar. Steuerelemente, die geschrieben werden, um in großen Umfang verwendet zu werden (in vielen Anwendungen von vielen Entwicklern), stehen vor der Herausforderung, dass Stil verwendet werden kann, um umfangreiche Änderungen an der visuellen Darstellung des Steuerelements vorzunehmen. Tatsächlich sieht das formatierte Steuerelement möglicherweise den Absichten des Autors des Steuerelements nicht ähnlich. Da die Flexibilität von Stilen grenzenlosen ist, können Sie das Konzept der häufigen Verwendung nutzen, um Ihren Entscheidungsspielraum zu vergrößern.

Um die häufige Verwendung des Steuerelements zu verstehen, denken Sie am besten an den Wertbeitrag des Steuerelements. Was bringt das Steuerelement der Tabelle, was kein anderes Steuerelement sonst bieten kann? Die häufige Verwendung impliziert eine bestimme visuelle Darstellen, sondern eher die Philosophie des Steuerelements und eine beachtliche Reihe von Erwartungen gegenüber seinem Gebrauch. Mit diesem Verständnis können Sie einige Annahmen über das Kompositionsmodell und die durch den Stil definierten häufigen Verhalten des Steuerelements durchführen. Wenn <xref:System.Windows.Controls.ComboBox>beispielsweise die allgemeine Verwendung verstehen, erhalten Sie keine Einblicke, ob eine bestimmte <xref:System.Windows.Controls.ComboBox> über abgerundete Ecken verfügt. Sie erhalten jedoch Einblicke in die Tatsache, dass die <xref:System.Windows.Controls.ComboBox> wahrscheinlich ein Popup Fenster benötigt und eine bestimmte Art von Schaltet ein, ob es geöffnet ist.

<a name="General_Guidelines"></a>

## <a name="general-guidelines"></a>Allgemeine Richtlinien

- **Erzwingen Sie die Vorlagenverträge nicht unbedingt.** Der Vorlagenvertrag eines Steuerelements besteht womöglich aus Elementen, Befehlen, Bindungen, Trigger oder sogar aus Eigenschafteneinstellungen, die erforderlich sind, dass ein Steuerelement ordnungsgemäß funktioniert, bzw. dass das von ihnen erwartet wird.

  - Minimieren Sie Verträge so weit wie möglich.

  - Entfernen Sie sich beim Entwerfen von der Anforderung, das es während der Entwurfszeit (wenn ein Entwurfstool verwendet wird) für eine Steuerelementvorlage gang und gäbe ist, sich in einem unvollständigen Zustand zu befinden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet keine „zusammengesetzte“ Statusinfrastruktur, deshalb müssen Steuerelemente mit der Anforderung erstellt werden, dass ein solcher Status womöglich gültig sein kann.

  - Lösen Sie keine Ausnahme aus, wenn auch nur ein Punkt eines Vorlagenvertrags nicht befolgt wird. Laut den Anforderungen dürfen Bereiche keine Ausnahme auslösen, wenn Sie zu viele oder zu wenige untergeordnete Elemente besitzen.

- **Faktor peripherer Funktionalität in Vorlagenhilfselementen.** Jedes Steuerelement sollte auf seine Kernfunktionalität und seinen wahren Wertbeitrag fokussiert sein und durch die häufige Verwendung des Steuerelements definiert sein. Verwenden Sie schlussendlich zusammengesetzte Elemente und Hilfselemente innerhalb der Vorlage, um Peripherieverhalten und -visualisierungen zu aktivieren. Dies sind jedoch die Verhalten und Visualisierungen, die nicht zur Kernfunktionalität des Steuerelements beitragen. Hilfselemente lassen sich in drei Kategorien unterteilen:

  - **Eigenständige** Hilfstypen sind öffentliche und wieder verwendbaren Steuerelemente oder Primitive, die „anonym“ in einer Vorlage verwendet werden, was bedeutet, dass weder das Hilfselement noch das formatierte Steuerelement vom jeweils anderen weiß. Technisch gesehen kann jedes Element ein anonymer Typ sein. In diesem Kontext beschreibt jedoch der Begriff diese Typen, die bestimmte Funktionen kapseln, um Zielszenarios zuzulassen.

  - **Typbasierte** Hilfselemente sind neue Typen, die speziellen Funktionen kapseln. Diese Elemente werden in der Regel mit einem geringeren Spektrum an Funktionalität als allgemeine Steuerelemente oder Primitive entworfen. Im Gegensatz zu eigenständigen Hilfselementen kennen typbasierte Hilfselemente den Kontext, in dem sie verwendet werden, und in dem sie in der Regel Daten müssen mit dem Steuerelement gemeinsam nutzen müssen, zu dessen Vorlage sie gehören.

  - **Benannte** Hilfselemente sind allgemeine Steuerelemente oder Primitive, die ein Steuerelement in seiner Vorlage nach Namen suchen kann. Diese Elemente erhalten einen bekannten Namen innerhalb der Vorlage, was es einem Steuerelement ermöglicht, das Element zu finden und programmgesteuert mit ihm zu interagieren. Es kann nur ein Element mit einem bestimmten Namen in jeder Vorlage vorhanden sein.

  In der folgenden Tabelle werden die Hilfselemente aufgeführt, die heute von Steuerelementstilen genutzt werden (diese Liste ist nicht vollständig):

  |Element|Geben Sie Folgendes ein:|Verwendung|
  |-------------|----------|-------------|
  |<xref:System.Windows.Controls.ContentPresenter>|Typbasiert|<xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.Frame>usw. (alle <xref:System.Windows.Controls.ContentControl> Typen)|
  |<xref:System.Windows.Controls.ItemsPresenter>|Typbasiert|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>usw. (alle <xref:System.Windows.Controls.ItemsControl> Typen)|
  |<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Benannt|<xref:System.Windows.Controls.ToolBar>|
  |<xref:System.Windows.Controls.Primitives.Popup>|Eigenständig|<xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ToolBar>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolTip>usw.|
  |<xref:System.Windows.Controls.Primitives.RepeatButton>|Benannt|<xref:System.Windows.Controls.Slider>, <xref:System.Windows.Controls.Primitives.ScrollBar>usw.|
  |<xref:System.Windows.Controls.Primitives.ScrollBar>|Benannt|<xref:System.Windows.Controls.ScrollViewer>|
  |<xref:System.Windows.Controls.ScrollViewer>|Eigenständig|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.Frame>usw.|
  |<xref:System.Windows.Controls.Primitives.TabPanel>|Eigenständig|<xref:System.Windows.Controls.TabControl>|
  |<xref:System.Windows.Controls.TextBox>|Benannt|<xref:System.Windows.Controls.ComboBox>|
  |<xref:System.Windows.Controls.Primitives.TickBar>|Typbasiert|<xref:System.Windows.Controls.Slider>|

- **Minimieren der erforderlichen benutzerdefinierten Bindungen oder Eigenschaften auf Hilfselementen**. Es ist üblich für ein Hilfselement, dass es bestimmte Bindungen oder Eigenschafteneinstellungen benötigt, um ordnungsgemäß innerhalb der Steuerelementvorlage zu funktionieren. Das Hilfselement und das Steuerelement mit Vorlagen sollten – so weit wie möglich – diese Einstellungen einrichten. Beim Festlegen von Eigenschaften oder beim Einrichten von Bindungen sollte darauf geachtet werden, keine vom Benutzer festgelegten Werte außer Kraft zu setzen. Bestimmte bewährte Methoden lauten wie folgt:

  - Benannte Hilfselemente sollten vom übergeordneten Element angegeben werden, und das übergeordnete Element sollte alle erforderlichen Einstellungen für das Hilfselement herstellen.

  - Typbasierte Hilfselemente sollten alle erforderlichen Einstellungen für sich selbst festlegen. Dazu muss das Hilfselement möglicherweise eine Abfrage durchführen, um Informationen über den Kontext zu erhalten, in dem es verwendet wird, einschließlich dessen `TemplatedParent` (der Steuerelementtyp der Vorlage, indem es verwendet wird). <xref:System.Windows.Controls.ContentPresenter> bindet z. b. die `Content`-Eigenschaft des `TemplatedParent` automatisch an die <xref:System.Windows.Controls.ContentPresenter.Content%2A>-Eigenschaft, wenn Sie in einem <xref:System.Windows.Controls.ContentControl> abgeleiteten Typ verwendet wird.

  - Eigenständige Hilfselemente können nicht auf diese Weise optimiert werden, da per Definition weder das Hilfselement noch das übergeordnete Element der anderen kennt.

- **Verwenden Sie die Name-Eigenschaft, um Elemente innerhalb einer Vorlage zu kennzeichnen**. Ein Steuerelement, das ein Element in seinem Stil finden muss, um programmgesteuert darauf zugreifen, sollte dazu die `Name`-Eigenschaft und das `FindName`-Paradigma verwenden. Ein Steuerelement sollte keine Ausnahme auslösen, wenn ein Element nicht gefunden wird, jedoch im Hintergrund und diskret die Funktionalität deaktivieren, die dieses Element benötigt hat.

- **Verwenden Sie bewährte Methoden zum Ausdrücken des Steuerelementzustands und des Verhaltens in einem Stil.** Im Folgenden finden Sie eine geordnete Liste der bewährten Methoden zum Ausdrücken von Änderungen des Steuerelementzustands und von Verhalten in einem Stil. Verwenden Sie das erste Element in der Liste, die das Szenario aktiviert.

  1. Eigenschaftenbindung Beispiel: Bindung zwischen <xref:System.Windows.Controls.ComboBox.IsDropDownOpen%2A?displayProperty=nameWithType> und <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A?displayProperty=nameWithType>.

  2. Hat Eigenschaftsänderungen oder -animationen ausgelöst. Beispiel: der Hover-Zustand einer <xref:System.Windows.Controls.Button>.

  3. Befehl. Beispiel: <xref:System.Windows.Controls.Primitives.ScrollBar.LineUpCommand> / <xref:System.Windows.Controls.Primitives.ScrollBar.LineDownCommand> in <xref:System.Windows.Controls.Primitives.ScrollBar>.

  4. Eigenständige Hilfselemente. Beispiel: <xref:System.Windows.Controls.Primitives.TabPanel> in <xref:System.Windows.Controls.TabControl>.

  5. Typbasierte Hilfstypen. Beispiel: <xref:System.Windows.Controls.ContentPresenter> in <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.TickBar> in <xref:System.Windows.Controls.Slider>.

  6. Benannte Hilfselemente. Beispiel: <xref:System.Windows.Controls.TextBox> in <xref:System.Windows.Controls.ComboBox>.

  7. Übergebene Ereignisse aus benannten Hilfstypen. Wenn Sie übergeben Ereignisse aus einem Stilelement überwachen, sollten Sie anfordern, dass das Element, das das Ereignis generiert, eindeutig identifiziert werden kann. Beispiel: <xref:System.Windows.Controls.Primitives.Thumb> in <xref:System.Windows.Controls.ToolBar>.

  8. Benutzerdefiniertes `OnRender`-Verhalten. Beispiel: <xref:Microsoft.Windows.Themes.ButtonChrome> in <xref:System.Windows.Controls.Button>.

- **Verwenden Sie die Formattrigger (im Gegensatz zu Vorlagentrigger) sparsam**. Trigger, die Eigenschaften für Elemente in der Vorlage beeinflussen, müssen in der Vorlage deklariert werden. Trigger, die Eigenschaften des Steuerelements beeinflussen (keine `TargetName`) können im Stil deklariert werden, es sei denn, Sie wissen, dass eine Änderung der Vorlage auch den Trigger zerstören wird.

- **Seien Sie mit vorhandenen Formatierungsmustern konsistent.** Oft gibt es mehrere Methoden zur Lösung eines Problems. Beachten Sie, und – wenn möglich – seien Sie konsistent vorhandenen Stilentwürfen des Steuerelements. Dies ist insbesondere für Steuerelemente wichtig, die vom gleichen Basistyp abgeleitet werden (z. b. <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.Primitives.RangeBase>usw.).

- **Machen Sie Eigenschaften verfügbar, um allgemeine Anpassungszenarios ohne neue Vorlagen zuzulassen**. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt keine austauschbaren/anpassbaren Teile,also bleibt ein Benutzer des Steuerelements mit nur zwei Methoden der Anpassung zurück: direktes Festlegen von Eigenschaften oder Festlegen von Eigenschaften mit Formatvorlagen. Wenn Sie das bedenken, können Sie eine begrenzte Anzahl an Eigenschaften für sehr häufige Anpassungsszenarios mit hoher Priorität darzustellen, die andernfalls eine neue Vorlage erfordern. Hier sind die bewährten Methoden dargestellt, wenn und wie Anpassungsszenarios aktiviert werden:

  - Sehr häufige Anpassungen sollten als Eigenschaften des Steuerelements verfügbar gemacht werden und von der Vorlage genutzt werden.

  - Weniger allgemeine (wenn auch keine seltenen) Anpassungen sollten als angefügte Eigenschaften verfügbar gemacht werden und von der Vorlage genutzt werden.

  - Für bekannte aber seltene Anpassungen sind erforderliche neue Vorlagen akzeptabel.

<a name="Theme_Considerations"></a>

## <a name="theme-considerations"></a>Überlegungen zum Design

- **Designstile sollten versuchen, über konsistente Eigenschaftensemantik auf allen Designs zu verfügen, aber es gibt keine Garantie dafür**. Als Teil der Dokumentation sollte das Steuerelement über ein Dokument zur Beschreibung der Eigenschaftensemantik des Steuerelements verfügen, also die „Bedeutung“ einer Eigenschaft für ein Steuerelement. Beispielsweise sollte das <xref:System.Windows.Controls.ComboBox>-Steuerelement die Bedeutung der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft innerhalb <xref:System.Windows.Controls.ComboBox>definieren. Die Standardstile für das Steuerelement sollten versuchen, die für alle Designs in diesem Dokument definierte Semantik zu befolgen. Benutzer des Steuerelements sollten sich jedoch auch bewusst sein, dass die Eigenschaftensemantik von Design zu Design verschieden sein kann. In bestimmten Fällen kann eine bestimmte Eigenschaft unter den visuellen Einschränkungen, die von einem bestimmten Design benötigt werden, nicht ausgedrückt werden. (Das Classic-Design verfügt z.B. über keine einzelne Grenze für die `Thickness` für viele Steuerelemente angewendet werden kann.)

- **Designstile müssen nicht über konsistente Triggersemantik zwischen allen Designs verfügen**. Das Verhalten, das von einem Steuerelementstil durch Trigger oder Animationen verfügbar gemacht wird, kann je nach Design variieren. Benutzer sollten bedenken, dass ein Steuerelement nicht zwangsläufig denselben Mechanismus nutzt, um alle ein bestimmtes Verhalten für alle Designs zu erzielen. Ein Design kann z.B. eine Animation verwenden, um das Hover-Verhalten zu verdeutlichen, während ein anderes Design einen Trigger verwendet. Dies kann zu Inkonsistenzen bei der Beibehaltung des Verhaltens in benutzerdefinierten Steuerelementen führen. (Das Ändern von beispielsweise der Hintergrundeigenschaft kann den Hoverzustand des Steuerelements womöglich nicht beeinflussen, wenn dieser Zustand mithilfe eines Triggers ausgelöst wird. Wenn der Hoverzustand allerdings mithilfe einer Animation implementiert wurde, kann das Wechseln zum Hintergrund zu einer irreparablen Zerstörung der Animation und somit auch des Zustandsübergangs führen.)

- **Designstile müssen nicht über konsistente „Layoutsemantik“ über allen Designs verfügen**. Das Standardformat muss z.B: nicht garantieren, dass ein Steuerelement die gleiche Größe in allen Designs übernimmt oder dass ein Steuerelement über dieselben Ränder/Abstände des Inhalts in allen Designs verfügt.

## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Übersicht über das Erstellen von Steuerelementen](control-authoring-overview.md)
