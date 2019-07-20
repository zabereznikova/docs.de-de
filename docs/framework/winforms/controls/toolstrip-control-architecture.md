---
title: Architektur des ToolStrip-Steuerelements
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: d0a1441e9bae8d2c1f938e7399c11e736708da4d
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363826"
---
# <a name="toolstrip-control-architecture"></a>Architektur des ToolStrip-Steuerelements

Die <xref:System.Windows.Forms.ToolStrip> Klassen <xref:System.Windows.Forms.ToolStripItem> und stellen ein flexibles, erweiterbares System zum Anzeigen von Symbolleisten-, Status-und Menü Elementen bereit. Diese Klassen sind alle im- <xref:System.Windows.Forms> Namespace enthalten. Sie werden in der Regel mit dem Präfix "ToolStrip" ( <xref:System.Windows.Forms.ToolStripOverflow>z. b.) oder mit dem Suffix "Strip" <xref:System.Windows.Forms.MenuStrip>benannt (z. b.).

## <a name="toolstrip"></a>ToolStrip

In den folgenden Themen <xref:System.Windows.Forms.ToolStrip> werden und die Steuerelemente beschrieben, die davon abgeleitet sind.

<xref:System.Windows.Forms.ToolStrip>ist die abstrakte Basisklasse für <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>und <xref:System.Windows.Forms.ContextMenuStrip>. Das folgende Objektmodell zeigt die <xref:System.Windows.Forms.ToolStrip> Vererbungs Hierarchie.

![Diagramm, das das ToolStrip-Objektmodell anzeigt.](./media/toolstrip-control-architecture/toolstrip-object-model.gif)

Sie können auf alle Elemente in einem <xref:System.Windows.Forms.ToolStrip> über die <xref:System.Windows.Forms.ToolStrip.Items%2A> -Auflistung zugreifen. Sie können auf alle Elemente in einem <xref:System.Windows.Forms.ToolStripDropDownItem> über die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> -Auflistung zugreifen. In einer von <xref:System.Windows.Forms.ToolStrip>abgeleiteten Klasse können Sie auch die <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> -Eigenschaft verwenden, um nur auf die gegenwärtig angezeigten Elemente zuzugreifen. Dies sind die Elemente, die sich derzeit nicht in einem Überlauf Menü befinden.

Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in allen Ausrichtungen konzipiert. Sie sind standardmäßig zur Entwurfszeit für das <xref:System.Windows.Forms.ToolStrip> -Steuerelement verfügbar:

- <xref:System.Windows.Forms.ToolStripButton>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="menustrip"></a>MenuStrip

<xref:System.Windows.Forms.MenuStrip>ist der Container der obersten Ebene, der den <xref:System.Windows.Forms.MainMenu>ablöst. Außerdem werden Schlüssel Behandlung und MDI-Funktionen (Multiple Document Interface) bereitstellt. <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ToolStripItem>Funktional und funktionieren<xref:System.Windows.Forms.ToolStripMenuItem> zusammen mit, obwohl Sie von abgeleitet sind. <xref:System.Windows.Forms.ToolStripDropDownItem>

Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in allen Ausrichtungen konzipiert. Sie sind standardmäßig zur Entwurfszeit für das <xref:System.Windows.Forms.MenuStrip> -Steuerelement verfügbar:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="statusstrip"></a>StatusStrip

<xref:System.Windows.Forms.StatusStrip>ersetzt das <xref:System.Windows.Forms.StatusBar> -Steuerelement. Zu den besonderen <xref:System.Windows.Forms.StatusStrip> Features von gehören ein benutzerdefiniertes Tabellenlayout, Unterstützung für die Größenanpassung und das `Spring` Verschieben des Formulars sowie die <xref:System.Windows.Forms.ToolStripStatusLabel> -Eigenschaft, mit der ein verfügbarer Speicher automatisch aufgefüllt werden kann.

Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in allen Ausrichtungen konzipiert. Sie sind standardmäßig zur Entwurfszeit für das <xref:System.Windows.Forms.StatusStrip> -Steuerelement verfügbar:

- <xref:System.Windows.Forms.ToolStripStatusLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripProgressBar>

### <a name="contextmenustrip"></a>ContextMenuStrip

<xref:System.Windows.Forms.ContextMenuStrip> ersetzt <xref:System.Windows.Forms.ContextMenu>. Sie können einem beliebiges Steuerelement einen <xref:System.Windows.Forms.ContextMenuStrip> zuordnen, und mit der rechten Maustaste wird automatisch das Kontextmenü (oder das Kontextmenü) angezeigt. Sie können einen <xref:System.Windows.Forms.ContextMenuStrip> Programm gesteuert mithilfe der <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> -Methode anzeigen. <xref:System.Windows.Forms.ContextMenuStrip>unterstützt <xref:System.Windows.Forms.ToolStripDropDown.Opening> abgebrochen <xref:System.Windows.Forms.ToolStripDropDown.Closing> -und-Ereignisse zur Behandlung dynamischer auffüllungs-und multiclick-Szenarios. <xref:System.Windows.Forms.ContextMenuStrip>unterstützt Bilder, den Zustand der Menü Element Überprüfung, Text, Zugriffstasten, Verknüpfungen und Kaskadierende Menüs.

Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in allen Ausrichtungen konzipiert. Sie sind standardmäßig zur Entwurfszeit für das <xref:System.Windows.Forms.ContextMenuStrip> -Steuerelement verfügbar:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="toolstrip-generic-features"></a>Generische Funktionen von ToolStrip

In den folgenden Themen werden Funktionen und das Verhalten beschrieben, die <xref:System.Windows.Forms.ToolStrip> für die abgeleiteten Steuerelemente und generisch sind.

#### <a name="painting"></a>Be

Es gibt mehrere Möglichkeiten, Benutzer <xref:System.Windows.Forms.ToolStrip> definierte Zeichen in Steuerelementen zu zeichnen. Wie bei anderen Windows Forms-Steuerelementen <xref:System.Windows.Forms.ToolStrip> verfügen <xref:System.Windows.Forms.ToolStripItem> sowohl die-als auch `OnPaint` die- `Paint` Methode über schreibbare Methoden und Ereignisse. Wie bei der regulären Darstellung ist das Koordinatensystem relativ zum Client Bereich des Steuer Elements. Das heißt, die linke obere Ecke des Steuer Elements ist 0, 0. Das `Paint` Ereignis und `OnPaint` die Methode für <xref:System.Windows.Forms.ToolStripItem> ein Verhalten sich wie andere Steuerelemente zum Zeichnen von Steuerelementen.

Die <xref:System.Windows.Forms.ToolStrip> Steuerelemente bieten außerdem einen präziseteren Zugriff auf das Rendering von Elementen und <xref:System.Windows.Forms.ToolStripRenderer> Containern über die-Klasse, die über schreibbare Methoden zum Zeichnen von Hintergrund, Element Hintergrund, Element Bild, Element Pfeil, Element Text und Rahmen des <xref:System.Windows.Forms.ToolStrip>. Die Ereignis Argumente für diese Methoden machen verschiedene Eigenschaften verfügbar, z. b. Rechtecke, Farben und Textformate, die Sie nach Bedarf anpassen können.

Um nur einige Aspekte der Art und Weise anzupassen, wie ein Element gezeichnet wird, über <xref:System.Windows.Forms.ToolStripRenderer>schreiben Sie in der Regel den.

Wenn Sie ein neues Element schreiben und alle Aspekte des Bildes steuern möchten, überschreiben Sie die `OnPaint` -Methode. Innerhalb `OnPaint`von können Sie Methoden aus der <xref:System.Windows.Forms.ToolStripRenderer>verwenden.

Standardmäßig ist der <xref:System.Windows.Forms.ToolStrip> doppelt gepuffert und nutzt die <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> -Einstellung.

#### <a name="parenting"></a>Geordnet

Das Konzept von Container Besitz und-Verarbeitung ist in <xref:System.Windows.Forms.ToolStrip> Steuerelementen komplexer als in anderen Windows Forms Container-Steuerelementen. Dies ist für die Unterstützung dynamischer Szenarien erforderlich, wie z. b. Überlauf, Freigabe <xref:System.Windows.Forms.ToolStrip> von Dropdown Elementen über mehrere Elemente hinweg und <xref:System.Windows.Forms.ContextMenuStrip> Unterstützung der Generierung eines von einem-Steuerelement.

In der folgenden Liste werden die Elemente beschrieben, die sich auf die über-und deren Verwendung beziehen.

- <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A>greift auf das Element zu, bei dem es sich um die Quelle des Dropdown Elements handelt. Dies ist vergleichbar mit <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, aber anstelle eines-Steuer Elements wird ein <xref:System.Windows.Forms.ToolStripItem>zurückgegeben.

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>bestimmt, welches Steuerelement die Quelle von <xref:System.Windows.Forms.ContextMenuStrip> ist, wenn mehrere Steuerelemente <xref:System.Windows.Forms.ContextMenuStrip>gleich sind.

- <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A>ist ein Schreib geschützter Accessor für die <xref:System.Windows.Forms.ToolStripItem.Parent%2A> -Eigenschaft. Ein übergeordnetes Element unterscheidet sich von einem Besitzer darin, dass ein über <xref:System.Windows.Forms.ToolStrip> geordnetes Element den zurückgegebenen aktuellen angibt, in dem das Element angezeigt wird, das möglicherweise im Überlauf Bereich angezeigt wird.

- <xref:System.Windows.Forms.ToolStripItem.Owner%2A>Gibt das <xref:System.Windows.Forms.ToolStrip> -Element zurück, dessen Items <xref:System.Windows.Forms.ToolStripItem>-Auflistung den aktuellen enthält. Dies ist die beste Möglichkeit, auf <xref:System.Windows.Forms.ToolStrip.ImageList%2A> oder andere Eigenschaften in der obersten Ebene <xref:System.Windows.Forms.ToolStrip> zu verweisen, ohne speziellen Code zum Behandeln von Überlauf zu schreiben.

#### <a name="behavior-of-inherited-controls"></a>Verhalten von geerbten Steuerelementen

Die folgenden Steuerelemente werden gesperrt, wenn Sie in Vererbung verwendet werden:

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.ToolStripPanel>, die die Bereiche eines <xref:System.Windows.Forms.ToolStripContainer> und auch einzelner <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente enthält.

Erstellen Sie z. b. eine neue Windows Forms Anwendung, indem Sie eines oder mehrere der Steuerelemente in der vorherigen Liste verwenden. Legen Sie den Zugriffsmodifizierer für `public` ein `protected`oder mehrere Steuerelemente auf oder fest, und erstellen Sie dann das Projekt. Fügen Sie ein Formular hinzu, das vom ersten Formular erbt, und wählen Sie dann ein geerbtes Steuerelement aus. Das-Steuerelement wird als `private`gesperrt angezeigt

#### <a name="toolstripcontainer-support-of-inheritance"></a>ToolStripContainer-Unterstützung für Vererbung

Das <xref:System.Windows.Forms.ToolStripContainer> -Steuerelement unterstützt eingeschränkte geerbte Szenarien, ähnlich wie im folgenden Beispiel:

1. Erstellen Sie eine neue Windows Forms-Anwendung.

2. Fügen Sie dem Formular eine <xref:System.Windows.Forms.ToolStripContainer> hinzu.

3. Legen <xref:System.Windows.Forms.ToolStripContainer> Sie den Zugriffsmodifizierer von auf `public` oder `protected`fest.

4. Fügen <xref:System.Windows.Forms.ToolStrip>Sie den Bereichendes<xref:System.Windows.Forms.ToolStripContainer>eine beliebige <xref:System.Windows.Forms.ContextMenuStrip> Kombination von-, <xref:System.Windows.Forms.MenuStrip>-und-Steuerelementen hinzu. <xref:System.Windows.Forms.ToolStripPanel>

5. Erstellen Sie das Projekt.

6. Fügen Sie ein Formular hinzu, das vom ersten Formular erbt.

7. Wählen Sie die <xref:System.Windows.Forms.ToolStripContainer> geerbte im Formular aus.

#### <a name="inherited-behavior-of-child-controls"></a>Vererbte Verhalten von untergeordneten Steuerelementen

Nachdem Sie die vorherigen Schritte ausgeführt haben, tritt das folgende geerbte Verhalten auf:

- Im Designer wird das-Steuerelement mit einem geerbten Symbol angezeigt.

- Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente sind gesperrt. Sie können ihren Inhalt nicht auswählen oder neu anordnen.

- Sie können der <xref:System.Windows.Forms.ToolStripContentPanel>Steuerelemente hinzufügen, die Steuerelemente verschieben und Sie als untergeordnete Steuer <xref:System.Windows.Forms.ToolStripContentPanel>Elemente des-Elements festlegen.

- Die Änderungen bleiben nach dem Erstellen des Formulars erhalten.

  > [!NOTE]
  > Entfernen Sie die Zugriffsmodifizierer aus allen <xref:System.Windows.Forms.ToolStripPanel> Steuerelementen, die Teil <xref:System.Windows.Forms.ToolStripContainer>eines sind. Der Zugriffsmodifizierer des <xref:System.Windows.Forms.ToolStripContainer> steuert das gesamte Steuerelement.

#### <a name="partial-trust"></a>Teilweise Vertrauenswürdigkeit

Die Einschränkungen von `ToolStrip`s bei teilweiser Vertrauenswürdigkeit sind so konzipiert, dass ein unbeabsichtigter Eintrag persönlicher Informationen vermieden wird, die möglicherweise von nicht autorisierten Personen oder Diensten verwendet werden. Die Schutzmaßnahmen lauten wie folgt:

- `ToolStripDropDown`-Steuer <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> Elemente erfordern, dass Elemente <xref:System.Windows.Forms.ToolStripControlHost>in einer angezeigt werden. Dies gilt sowohl für systeminterne Steuerelemente <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>wie z <xref:System.Windows.Forms.ToolStripProgressBar> . b., und, als auch für Benutzer erstellte Steuerelemente. Wenn diese Anforderung nicht erfüllt wird, werden diese Elemente nicht angezeigt. Es werden keine Ausnahmen ausgelöst.

- Das Festlegen <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> der- `false` Eigenschaft auf ist nicht zulässig, und der <xref:System.Windows.Forms.ToolStripDropDown.Closing> abgebrochen-Ereignis Parameter wird ignoriert. Dadurch ist es unmöglich, mehr als einen Tastatur Strich einzugeben, ohne das Dropdown Element zu verwerfen. Wenn diese Anforderung nicht erfüllt wird, werden diese Elemente nicht angezeigt. Es werden keine Ausnahmen ausgelöst.

- Viele Tastatur Schlag Ereignisse werden nicht ausgelöst, wenn Sie in teilweise vertrauenswürdigen Kontexten als <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>auftreten.

- Zugriffsschlüssel werden nicht verarbeitet, <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> wenn nicht gewährt wird.

#### <a name="usage"></a>Verwendung

Die folgenden Verwendungs Muster haben einen Einfluss auf <xref:System.Windows.Forms.ToolStrip> Layout, Tastatur Interaktion und Endbenutzer Verhalten:

- Verknüpft in<xref:System.Windows.Forms.ToolStripPanel>

  Der <xref:System.Windows.Forms.ToolStrip> kann <xref:System.Windows.Forms.ToolStripPanel>innerhalb von und über s neu positioniert werden. <xref:System.Windows.Forms.ToolStripPanel> Die `Dock` -Eigenschaft wird ignoriert, und wenn <xref:System.Windows.Forms.ToolStrip.Stretch%2A> die- `false`Eigenschaft den Wert hat, <xref:System.Windows.Forms.ToolStrip> wird die Größe der Vergrößerung <xref:System.Windows.Forms.ToolStripPanel>vergrößert. In der Regel <xref:System.Windows.Forms.ToolStrip> ist der nicht an der Aktivier Reihenfolge beteiligt.

- Angedockt

  Die <xref:System.Windows.Forms.ToolStrip> wird auf einer Seite eines Containers an einer festgelegten Position platziert, und die Größe wird über den gesamten Rand erweitert, an dem Sie angedockt ist. In der Regel <xref:System.Windows.Forms.ToolStrip> ist der nicht an der Aktivier Reihenfolge beteiligt.

- Absolut positioniert

  Die <xref:System.Windows.Forms.ToolStrip> ähnelt anderen Steuerelementen, da Sie von der <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft platziert wird, eine festgelegte Größe aufweist und in der Regel an der Aktivier Reihenfolge teilnimmt.

#### <a name="keyboard-interaction"></a>Tastatur Interaktion

##### <a name="access-keys"></a>Zugriffsschlüssel

In Kombination mit oder nach der Alt-Taste sind Zugriffstasten eine Möglichkeit zum Aktivieren eines Steuer Elements über die Tastatur. <xref:System.Windows.Forms.ToolStrip>unterstützt sowohl explizite als auch implizite Zugriffsschlüssel. Eine explizite Definition verwendet ein kaufmännisches und-Zeichen (&), das dem Buchstaben vorangestellt ist. Die implizite Definition verwendet einen Algorithmus, der versucht, ein übereinstimmendes Element auf Grundlage der Reihenfolge der `Text` Zeichen in einer bestimmten Eigenschaft zu finden.

##### <a name="shortcut-keys"></a>Tastenkombinationen

Die Tastenkombinationen, die von <xref:System.Windows.Forms.MenuStrip> einem verwendet werden, verwenden <xref:System.Windows.Forms.Keys> eine Kombination aus der-Enumeration (die nicht Reihen folgen spezifisch ist), um die Tastenkombination zu definieren. Sie können auch die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> -Eigenschaft verwenden, um eine Tastenkombination mit nur einem Text anzuzeigen, z. b. "del" anstelle von "Delete".

##### <a name="navigation"></a>Navigation

Die Alt-Taste aktiviert <xref:System.Windows.Forms.MenuStrip> den, auf <xref:System.Windows.Forms.Form.MainMenuStrip%2A>den von gezeigt wird. Von dort aus werden STRG + TAB zwischen <xref:System.Windows.Forms.ToolStrip> Steuerelementen in `ToolStripPanel`s navigiert. Die Tab-Taste und die Pfeiltasten auf der numerischen Tastatur werden zwischen den Elementen in <xref:System.Windows.Forms.ToolStrip>einem navigiert. Ein spezieller Algorithmus behandelt die Navigation im Überlauf Bereich. Leertaste wählt <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>oder <xref:System.Windows.Forms.ToolStripSplitButton>aus.

##### <a name="focus-and-validation"></a>Fokus und Validierung

Bei Aktivierung durch die Alt-Taste wird <xref:System.Windows.Forms.MenuStrip> der <xref:System.Windows.Forms.ToolStrip> Fokus von oder in der Regel weder von dem Steuerelement entfernt, das derzeit den Fokus besitzt. Wenn ein-Steuerelement innerhalb <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MenuStrip>von oder in einem Dropdown Element von gehostet wird, erhält das Steuerelement den Fokus, wenn der Benutzer die Tab-Taste drückt. Im Allgemeinen werden die <xref:System.Windows.Forms.Control.GotFocus>- <xref:System.Windows.Forms.Control.LostFocus> <xref:System.Windows.Forms.Control.Enter>,-, <xref:System.Windows.Forms.Control.Leave> -und <xref:System.Windows.Forms.MenuStrip> -Ereignisse von möglicherweise nicht ausgelöst, wenn Sie von der Tastatur aktiviert werden. Verwenden Sie in solchen Fällen stattdessen <xref:System.Windows.Forms.MenuStrip.MenuActivate> das <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> -Ereignis und das-Ereignis.

Standardmäßig <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> ist `false`. Geben <xref:System.Windows.Forms.ContainerControl.Validate%2A> Sie explizit auf dem Formular ein, um die Validierung auszuführen.

#### <a name="layout"></a>Layout

Sie steuern <xref:System.Windows.Forms.ToolStrip> das Layout, indem Sie eines der Member <xref:System.Windows.Forms.ToolStripLayoutStyle> von mit <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> der-Eigenschaft auswählen.

##### <a name="stack-layouts"></a>Stapel Layouts

Das Stapeln ist das Anordnen von Elementen an beiden Enden von <xref:System.Windows.Forms.ToolStrip>nebeneinander. In der folgenden Liste werden die Stapel Layouts beschrieben.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>der Standardwert ist. Diese Einstellung bewirkt, <xref:System.Windows.Forms.ToolStrip> dass das Layout automatisch in Übereinstimmung mit der <xref:System.Windows.Forms.ToolStrip.Orientation%2A> -Eigenschaft ändert, um Drag & amp; Andock Szenarios zu verarbeiten.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>Rendert <xref:System.Windows.Forms.ToolStrip> die Elemente nebeneinander nebeneinander.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow>Rendert <xref:System.Windows.Forms.ToolStrip> die Elemente nebeneinander nebeneinander.

##### <a name="other-features-of-stack-layouts"></a>Weitere Features von Stapel Layouts

<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>bestimmt das Ende der <xref:System.Windows.Forms.ToolStrip> , an die das Element ausgerichtet wird.

Wenn Elemente nicht in <xref:System.Windows.Forms.ToolStrip>passen, wird automatisch eine Überlauf Schaltfläche angezeigt. Die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> -Eigenschafts Einstellung bestimmt, ob ein Element immer, bei Bedarf im Überlauf Bereich angezeigt wird, oder nie.

Im- <xref:System.Windows.Forms.ToolStripItem.Placement%2A> <xref:System.Windows.Forms.ToolStrip>Ereignis können Sie die-Eigenschaft überprüfen, um zu bestimmen, ob ein Element auf dem Haupt- <xref:System.Windows.Forms.ToolStrip>, dem Überlauf oder derzeit überhaupt nicht angezeigt wird. <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> Der typische Grund, warum ein Element nicht angezeigt wird, ist, dass das Element nicht in den <xref:System.Windows.Forms.ToolStrip> Haupt- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> und dessen-Eigenschaft <xref:System.Windows.Forms.ToolStripItemOverflow.Never>auf festgelegt wurde.

Verschieben Sie <xref:System.Windows.Forms.ToolStrip> einen verschiebbaren Wert, <xref:System.Windows.Forms.ToolStripPanel> indem Sie ihn in <xref:System.Windows.Forms.ToolStripGripStyle.Visible>einem einfügen und dessen <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> auf festlegen.

##### <a name="other-layout-options"></a>Weitere Layoutoptionen

Die anderen Layoutoptionen <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> sind <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>und.

##### <a name="flow-layout"></a>Flusslayout

<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>Layout ist die Standardeinstellung <xref:System.Windows.Forms.ContextMenuStrip>für <xref:System.Windows.Forms.ToolStripDropDownMenu>, und <xref:System.Windows.Forms.ToolStripOverflow>. Sie ähnelt dem <xref:System.Windows.Forms.FlowLayoutPanel>. Die Merkmale des <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layouts lauten wie folgt:

- Alle Funktionen von <xref:System.Windows.Forms.FlowLayoutPanel> werden von der <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> -Eigenschaft verfügbar gemacht. Sie müssen die <xref:System.Windows.Forms.LayoutSettings> Klasse in eine <xref:System.Windows.Forms.FlowLayoutSettings> Klasse umwandeln.

- Sie können die <xref:System.Windows.Forms.ToolStripItem.Dock%2A> -Eigenschaft <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> und die-Eigenschaft im Code verwenden, um die Elemente in der Zeile auszurichten.

- Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>-Eigenschaft wird ignoriert.

- Im- <xref:System.Windows.Forms.ToolStripItem.Placement%2A> <xref:System.Windows.Forms.ToolStrip> Ereignis können Sie die-Eigenschaft überprüfen, um zu bestimmen, ob ein Element in den Haupt-oder nicht passt. <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>

- Der Ziehpunkt wird nicht gerendert, <xref:System.Windows.Forms.ToolStrip> daher <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> kann ein im Layoutstil in einem <xref:System.Windows.Forms.ToolStripPanel> nicht verschoben werden.

- Die <xref:System.Windows.Forms.ToolStrip> Überlauf Schaltfläche wird nicht gerendert und <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> wird ignoriert.

##### <a name="table-layout"></a>Tabellenlayout

<xref:System.Windows.Forms.ToolStripLayoutStyle.Table>Layout ist die Standardeinstellung <xref:System.Windows.Forms.StatusStrip>für. Dies ist vergleichbar mit <xref:System.Windows.Forms.TableLayoutPanel>. Die Merkmale des <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layouts lauten wie folgt:

- Alle Funktionen von <xref:System.Windows.Forms.TableLayoutPanel> werden von der <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> -Eigenschaft verfügbar gemacht. Sie müssen die <xref:System.Windows.Forms.LayoutSettings> Klasse in eine <xref:System.Windows.Forms.TableLayoutSettings> Klasse umwandeln.

- Sie können die <xref:System.Windows.Forms.ToolStripItem.Dock%2A> -Eigenschaft <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> und die-Eigenschaft im Code verwenden, um die Elemente in der Tabellenzelle auszurichten.

- Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>-Eigenschaft wird ignoriert.

- Im- <xref:System.Windows.Forms.ToolStripItem.Placement%2A> <xref:System.Windows.Forms.ToolStrip> Ereignis können Sie die-Eigenschaft überprüfen, um zu bestimmen, ob ein Element in den Haupt-oder nicht passt. <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>

- Der Ziehpunkt wird nicht gerendert, <xref:System.Windows.Forms.ToolStrip> daher <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> kann ein im Layoutstil in einem <xref:System.Windows.Forms.ToolStripPanel> nicht verschoben werden.

- Die <xref:System.Windows.Forms.ToolStrip> Überlauf Schaltfläche wird nicht gerendert und <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> wird ignoriert.

## <a name="toolstripitem"></a>ToolStripItem

In den folgenden Themen <xref:System.Windows.Forms.ToolStripItem> werden und die Steuerelemente beschrieben, die davon abgeleitet sind.

<xref:System.Windows.Forms.ToolStripItem>ist die abstrakte Basisklasse für alle Elemente, die in ein <xref:System.Windows.Forms.ToolStrip>-Element gelangen. Das folgende Objektmodell zeigt die <xref:System.Windows.Forms.ToolStripItem> Vererbungs Hierarchie.

![Diagramm, das das ToolStripItem-Objektmodell zeigt.](./media/toolstrip-control-architecture/toolstripitem-object-model.gif)

<xref:System.Windows.Forms.ToolStripItem>Klassen erben entweder direkt von <xref:System.Windows.Forms.ToolStripItem>, oder Sie erben indirekt von <xref:System.Windows.Forms.ToolStripItem> durch <xref:System.Windows.Forms.ToolStripControlHost> oder <xref:System.Windows.Forms.ToolStripDropDownItem>.

<xref:System.Windows.Forms.ToolStripItem>Steuerelemente müssen <xref:System.Windows.Forms.ToolStrip>in, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>oder <xref:System.Windows.Forms.ContextMenuStrip> enthalten sein und können nicht direkt zu einem Formular hinzugefügt werden. Die verschiedenen Containerklassen sind so konzipiert, dass Sie eine geeignete Teilmenge der <xref:System.Windows.Forms.ToolStripItem> Steuerelemente enthalten.

In der folgenden Tabelle sind die <xref:System.Windows.Forms.ToolStripItem> Aktien Steuerelemente und die Container aufgeführt, in denen Sie am besten aussehen. Obwohl ein <xref:System.Windows.Forms.ToolStrip> beliebiges Element in einem beliebigen <xref:System.Windows.Forms.ToolStrip>von abgeleiteten Container gehostet werden kann, wurden diese Elemente so entworfen, dass Sie am besten in den folgenden Containern aussehen:

> [!NOTE]
> <xref:System.Windows.Forms.ToolStripDropDown>wird nicht in der Designer-Toolbox angezeigt.

|Enthaltenes Element|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|
|<xref:System.Windows.Forms.ToolStripButton>|Ja|Nein|Nein|Nein|Ja|
|<xref:System.Windows.Forms.ToolStripComboBox>|Ja|Ja|Ja|Nein|Ja|
|<xref:System.Windows.Forms.ToolStripSplitButton>|Ja|Nein|Nein|Ja|Ja|
|<xref:System.Windows.Forms.ToolStripLabel>|Ja|Nein|Nein|Ja|Ja|
|<xref:System.Windows.Forms.ToolStripSeparator>|Ja|Ja|Ja|Nein|Ja|
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Ja|Nein|Nein|Ja|Ja|
|<xref:System.Windows.Forms.ToolStripTextBox>|Ja|Ja|Ja|Nein|Ja|
|<xref:System.Windows.Forms.ToolStripMenuItem>|Nein|Ja|Ja|Nein|Nein|
|<xref:System.Windows.Forms.ToolStripStatusLabel>|Nein|Nein|Nein|Ja|Nein|
|<xref:System.Windows.Forms.ToolStripProgressBar>|Ja|Nein|Nein|Ja|Nein|
|<xref:System.Windows.Forms.ToolStripControlHost>|Ja|Ja|Nein|Ja|Ja|

### <a name="toolstripbutton"></a>ToolStripButton

<xref:System.Windows.Forms.ToolStripButton>ist das Schaltflächen Element <xref:System.Windows.Forms.ToolStrip>für. Sie können Sie mit verschiedenen Rahmen Formaten anzeigen, und Sie können Sie verwenden, um Betriebszustände darzustellen und zu aktivieren. Sie können auch festlegen, dass der Fokus standardmäßig festgelegt wird.

### <a name="toolstriplabel"></a>ToolStripLabel

Bietet Bezeichnungs Funktionen in <xref:System.Windows.Forms.ToolStrip> -Steuerelementen. <xref:System.Windows.Forms.ToolStripLabel> Das <xref:System.Windows.Forms.ToolStripLabel> -ist wie <xref:System.Windows.Forms.ToolStripButton> ein, das nicht standardmäßig den Fokus erhält und nicht als per pushübertragung oder hervorgehoben dargestellt wird.

<xref:System.Windows.Forms.ToolStripLabel>als gehostete Elemente unterstützt Zugriffsschlüssel.

Verwenden Sie <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>die <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>Eigenschaften, <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> und in einem <xref:System.Windows.Forms.ToolStripLabel> , um das Link Steuerelement <xref:System.Windows.Forms.ToolStrip>in einem zu unterstützen.

### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel

<xref:System.Windows.Forms.ToolStripStatusLabel>ist eine Version von <xref:System.Windows.Forms.ToolStripLabel> , die speziell für die <xref:System.Windows.Forms.StatusStrip>Verwendung in entworfen wurde. Zu den besonderen Features <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>zählen <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>, und <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.

### <a name="toolstripseparator"></a>ToolStripSeparator

Der <xref:System.Windows.Forms.ToolStripSeparator> fügt einer Symbolleiste oder einem Menü abhängig von der Ausrichtung eine vertikale oder horizontale Linie hinzu. Sie ermöglicht das Gruppieren von oder unterschieden zwischen Elementen, z. b. in einem Menü.

Sie können ein <xref:System.Windows.Forms.ToolStripSeparator> zur Entwurfszeit hinzufügen, indem Sie es in einer Dropdown Liste auswählen. Sie können jedoch auch automatisch erstellen <xref:System.Windows.Forms.ToolStripSeparator> , indem Sie einen Bindestrich (-) entweder im Designer-Vorlagen Knoten oder in der <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> -Methode eingeben.

### <a name="toolstripcontrolhost"></a>ToolStripControlHost

<xref:System.Windows.Forms.ToolStripControlHost>ist die abstrakte Basisklasse für <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>und <xref:System.Windows.Forms.ToolStripProgressBar>. <xref:System.Windows.Forms.ToolStripControlHost>kann andere Steuerelemente, einschließlich benutzerdefinierter Steuerelemente, auf zwei Arten hosten:

- Erstellen Sie <xref:System.Windows.Forms.ToolStripControlHost> eine mit einer Klasse, die <xref:System.Windows.Forms.Control>von abgeleitet wird. Um vollständigen Zugriff auf das gehostete Steuerelement und die Eigenschaften <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> zu erhalten, müssen Sie die Eigenschaft wieder in die tatsächliche Klasse umwandeln, die Sie repräsentiert

- Erweitern <xref:System.Windows.Forms.ToolStripControlHost>Sie und im Parameter losen Konstruktor der geerbten Klasse den Basisklassenkonstruktor, und übergeben Sie eine Klasse, <xref:System.Windows.Forms.Control>die von abgeleitet wird. Mit dieser Option können Sie allgemeine Steuerelement Methoden und-Eigenschaften für den einfachen <xref:System.Windows.Forms.ToolStrip>Zugriff in einem einschließen.

### <a name="toolstripcombobox"></a>ToolStripComboBox

<xref:System.Windows.Forms.ToolStripComboBox>ist das <xref:System.Windows.Forms.ComboBox> für das Hosting in einem <xref:System.Windows.Forms.ToolStrip>optimierte. Eine Teilmenge der Eigenschaften und Ereignisse des gehosteten Steuer Elements wird auf der <xref:System.Windows.Forms.ToolStripComboBox> -Ebene verfügbar gemacht, <xref:System.Windows.Forms.ComboBox> aber auf das zugrunde liegende Steuer <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> Element kann über die-Eigenschaft vollständig zugegriffen werden.

### <a name="toolstriptextbox"></a>ToolStripTextBox

<xref:System.Windows.Forms.ToolStripTextBox>ist das <xref:System.Windows.Forms.TextBox> für das Hosting in einem <xref:System.Windows.Forms.ToolStrip>optimierte. Eine Teilmenge der Eigenschaften und Ereignisse des gehosteten Steuer Elements wird auf der <xref:System.Windows.Forms.ToolStripTextBox> -Ebene verfügbar gemacht, <xref:System.Windows.Forms.TextBox> aber auf das zugrunde liegende Steuer <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> Element kann über die-Eigenschaft vollständig zugegriffen werden.

### <a name="toolstripprogressbar"></a>ToolStripProgressBar

<xref:System.Windows.Forms.ToolStripProgressBar>ist das <xref:System.Windows.Forms.ProgressBar> für das Hosting in einem <xref:System.Windows.Forms.ToolStrip>optimierte. Eine Teilmenge der Eigenschaften und Ereignisse des gehosteten Steuer Elements wird auf der <xref:System.Windows.Forms.ToolStripProgressBar> -Ebene verfügbar gemacht, <xref:System.Windows.Forms.ProgressBar> aber auf das zugrunde liegende Steuer <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> Element kann über die-Eigenschaft vollständig zugegriffen werden.

### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem

<xref:System.Windows.Forms.ToolStripDropDownItem>ist die abstrakte Basisklasse für <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>und <xref:System.Windows.Forms.ToolStripSplitButton>, die Elemente direkt hosten oder zusätzliche Elemente in einem Dropdown Container hosten kann. <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> Hierzu legen Sie die <xref:System.Windows.Forms.ToolStripDropDown> -Eigenschaft auf fest und legen die <xref:System.Windows.Forms.ToolStrip.Items%2A> -Eigenschaft von <xref:System.Windows.Forms.ToolStripDropDown>fest. Greifen Sie direkt über die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> -Eigenschaft auf diese Dropdown Elemente zu.

### <a name="toolstripmenuitem"></a>ToolStripMenuItem

<xref:System.Windows.Forms.ToolStripMenuItem>ist eine <xref:System.Windows.Forms.ToolStripDropDownItem> , die mit <xref:System.Windows.Forms.ToolStripDropDownMenu> und <xref:System.Windows.Forms.ContextMenuStrip> verwendet wird, um die besondere Hervorhebung, das Layout und die Spalten Anordnung für Menüs zu verarbeiten.

### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton

<xref:System.Windows.Forms.ToolStripDropDownButton>sieht wie <xref:System.Windows.Forms.ToolStripButton>aus, aber es wird ein Dropdown Bereich angezeigt, wenn der Benutzer darauf klickt. Blenden Sie den Dropdown Pfeil durch Festlegen der <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> -Eigenschaft aus, oder zeigen Sie ihn an. <xref:System.Windows.Forms.ToolStripDropDownButton>hostet <xref:System.Windows.Forms.ToolStripOverflowButton> einen, der Elemente anzeigt, <xref:System.Windows.Forms.ToolStrip>die überlaufen.

### <a name="toolstripsplitbutton"></a>ToolStripSplitButton

<xref:System.Windows.Forms.ToolStripSplitButton>kombiniert Schaltfläche und Dropdown-Schaltflächen Funktionalität.

Verwenden Sie <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> die-Eigenschaft, <xref:System.Windows.Forms.Control.Click> um das-Ereignis des ausgewählten Dropdown Elements mit dem Element zu synchronisieren, das auf der Schaltfläche angezeigt wird.

### <a name="toolstripitem-generic-features"></a>Generische Features von ToolStripItem

<xref:System.Windows.Forms.ToolStripItem>bietet die folgenden allgemeinen Features und Optionen zum Erben von Steuerelementen:

- Core-Ereignisse

- Bildverarbeitung

- Ausrichtung

- Text-und Bild Beziehung

- Anzeige Stil

#### <a name="core-events"></a>Core-Ereignisse

<xref:System.Windows.Forms.ToolStripItem>Steuerelemente empfangen eigene Click-, Maus-und Zeichnungs Ereignisse und können auch eine bestimmte Tastatur Vorverarbeitung durchführen.

#### <a name="image-handling"></a>Bildverarbeitung

Die <xref:System.Windows.Forms.ToolStripItem.Image%2A>Eigenschaften <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, ,<xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A> ,<xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>und beziehen<xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> sich auf verschiedene Aspekte der Bildverarbeitung. Verwenden Sie Bilder <xref:System.Windows.Forms.ToolStrip> in Steuerelementen, indem Sie diese Eigenschaften direkt oder durch Festlegen der Eigenschaft Lauf <xref:System.Windows.Forms.ToolStrip.ImageList%2A> Zeit – only festlegen.

Die Bildskalierung wird durch die Interaktion von Eigenschaften sowohl <xref:System.Windows.Forms.ToolStrip> in <xref:System.Windows.Forms.ToolStripItem>als auch in festgelegt, wie im folgenden dargestellt:

- <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A>die Skala des endgültigen Bilds, wie durch die Kombination der Image- <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> Einstellung und der <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> Einstellung des Containers bestimmt.

  - Wenn <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> ( `true` der Standardwert) ist <xref:System.Windows.Forms.ToolStripItemImageScaling> und <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>ist, wird keine Bildskalierung durch <xref:System.Windows.Forms.ToolStrip> geführt, und die Größe entspricht dem größten Element oder einer vorgeschriebenen Mindestgröße.

  - Wenn <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> ist `false` und <xref:System.Windows.Forms.ToolStripItemImageScaling> <xref:System.Windows.Forms.ToolStrip> den Wert hat,erfolgtwedereinBildnocheineSkalierung.<xref:System.Windows.Forms.ToolStripItemImageScaling.None>

#### <a name="alignment"></a>Ausrichtung

Der Wert <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> der-Eigenschaft bestimmt das Ende <xref:System.Windows.Forms.ToolStrip> der, an der ein Element angezeigt wird. Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> -Eigenschaft kann nur verwendet werden, wenn die <xref:System.Windows.Forms.ToolStrip> layoutart des auf einen der Stapelüberlauf Werte festgelegt ist.

Elemente werden in der Reihen <xref:System.Windows.Forms.ToolStrip> Folge platziert, in der die Elemente in der Items-Auflistung angezeigt werden. Um die Position eines Elements Programm gesteuert zu ändern, verwenden Sie die <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> -Methode, um das Element in der Auflistung zu verschieben. Mit dieser Methode wird das Element verschoben, aber nicht dupliziert.

#### <a name="text-and-image-relationship"></a>Text-und Bild Beziehung

Die <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> -Eigenschaft definiert die relative Platzierung des Bilds in Bezug auf den Text auf <xref:System.Windows.Forms.ToolStripItem>einem. Elemente, die nicht über ein Bild, Text oder beides verfügen, werden als Sonderfälle behandelt <xref:System.Windows.Forms.ToolStripItem> , sodass für das fehlende Element oder die fehlenden Elemente keine leere Stelle anzeigt.

#### <a name="display-style"></a>Anzeige Stil

<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>ermöglicht das Festlegen der Werte für die Text-und Bildeigenschaften eines Elements, während nur die gewünschten Elemente angezeigt werden. Dies wird normalerweise verwendet, um nur den Anzeige Stil zu ändern, wenn das gleiche Element in einem anderen Kontext angezeigt wird.

## <a name="accessory-classes"></a>Zubehör Klassen

Zu den Klassen, die verschiedene andere Funktionen bieten, gehören:

- <xref:System.Windows.Forms.ToolStripManager>unter <xref:System.Windows.Forms.ToolStrip>stützt-bezogene Aufgaben für ganze Anwendungen, wie z. b. Zusammenführung, Einstellungen und rendereroptionen.

- <xref:System.Windows.Forms.ToolStripRenderer>ermöglicht es Ihnen, ein bestimmtes Format oder Design auf <xref:System.Windows.Forms.ToolStrip> einfache Weise zu verwenden.

- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>erstellt Stifte und Pinsel auf der Grundlage einer ersetzbaren Farb<xref:System.Windows.Forms.ProfessionalColorTable>Tabelle ().

- <xref:System.Windows.Forms.ToolStripSystemRenderer>wendet Systemfarben und einen flachen visuellen Stil auf <xref:System.Windows.Forms.ToolStrip> Anwendungen an.

- <xref:System.Windows.Forms.ToolStripContainer>ähnelt <xref:System.Windows.Forms.SplitContainer>. Er verwendet vier angedockte Seitenbereiche (Instanzen <xref:System.Windows.Forms.ToolStripPanel>von) und einen zentralen Bereich (eine Instanz <xref:System.Windows.Forms.ToolStripContentPanel>von), um eine typische Anordnung zu erstellen. Sie können die Seitenbereiche nicht entfernen, aber Sie können Sie ausblenden. Sie können den zentralen Bereich weder entfernen noch ausblenden. Sie können ein oder mehrere <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip>Steuerelemente, oder <xref:System.Windows.Forms.StatusStrip> in den Seiten Bereichen anordnen, und Sie können den zentralen Bereich für andere Steuerelemente verwenden. Bietet <xref:System.Windows.Forms.ToolStripContentPanel> auch eine Möglichkeit, rendererunterstützung für eine konsistente Darstellung in den Hauptteil Ihres Formulars zu bringen. <xref:System.Windows.Forms.ToolStripContainer>bietet keine Unterstützung für Multiple Document Interface (MDI).

- <xref:System.Windows.Forms.ToolStripPanel>bietet Platz zum Verschieben und anordnen <xref:System.Windows.Forms.ToolStrip> von Steuerelementen. Sie können nur einen Panel verwenden, wenn Sie dies auswählen, <xref:System.Windows.Forms.ToolStripPanel> und in MDI-Szenarien gut funktionieren.

## <a name="see-also"></a>Siehe auch

- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
- [ToolStrip-Steuerelement](toolstrip-control-windows-forms.md)
- [MenuStrip-Steuerelement](menustrip-control-windows-forms.md)
- [StatusStrip-Steuerelement](statusstrip-control.md)
- [ContextMenuStrip-Steuerelement](contextmenustrip-control.md)
- [BindingNavigator-Steuerelement](bindingnavigator-control-windows-forms.md)
