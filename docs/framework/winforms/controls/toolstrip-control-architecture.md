---
title: Architektur des ToolStrip-Steuerelements
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: d972e738305b14f44910acf755e0ffc1d7297e49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547052"
---
# <a name="toolstrip-control-architecture"></a>Architektur des ToolStrip-Steuerelements
Die <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStripItem> Klassen bieten ein flexibles, erweiterbares System zum Anzeigen der Symbolleiste, Status und Menüelementen. Diese Klassen sind in enthalten die <xref:System.Windows.Forms> -Namespace, und sie werden alle in der Regel mit dem Präfix "ToolStrip" benannt (z. B. <xref:System.Windows.Forms.ToolStripOverflow>) oder mit dem Suffix "Entfernen" (z. B. <xref:System.Windows.Forms.MenuStrip>).  
  
## <a name="toolstrip"></a>ToolStrip  
 Die folgenden Themen beschreiben <xref:System.Windows.Forms.ToolStrip> und die Steuerelemente, die von ihr abgeleitet werden.  
  
 <xref:System.Windows.Forms.ToolStrip> ist die abstrakte Basisklasse für <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, und <xref:System.Windows.Forms.ContextMenuStrip>. Das folgende Objekt Modell zeigt das <xref:System.Windows.Forms.ToolStrip> Vererbungshierarchie.  
  
 ![ToolStrip-Objektmodell](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.gif "ToolStripObjectModel")  
ToolStrip-Objektmodell  
  
 Es stehen alle Elemente in einem <xref:System.Windows.Forms.ToolStrip> über die <xref:System.Windows.Forms.ToolStrip.Items%2A> Auflistung. Es stehen alle Elemente in einem <xref:System.Windows.Forms.ToolStripDropDownItem> über die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> Auflistung. In einer Klasse abgeleitet <xref:System.Windows.Forms.ToolStrip>, können Sie auch die <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> Eigenschaft, um nur die Elemente zuzugreifen, die gerade angezeigt werden. Dies sind die Elemente, die derzeit nicht in ein Überlaufmenü befinden.  
  
 Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit sowohl <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in alle Ausrichtungen. Sie stehen standardmäßig zur Entwurfszeit für die <xref:System.Windows.Forms.ToolStrip> Steuerelement:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="menustrip"></a>MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> ist der Container der obersten Ebene, die ersetzt <xref:System.Windows.Forms.MainMenu>. Darüber hinaus schlüsselverarbeitung und mehrere Dokumente (Interface-) Funktionen. Funktionell <xref:System.Windows.Forms.ToolStripDropDownItem> und <xref:System.Windows.Forms.ToolStripMenuItem> arbeiten zusammen mit <xref:System.Windows.Forms.MenuStrip>, obwohl sie abgeleitet sind <xref:System.Windows.Forms.ToolStripItem>.  
  
 Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit sowohl <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in alle Ausrichtungen. Sie stehen standardmäßig zur Entwurfszeit für die <xref:System.Windows.Forms.MenuStrip> Steuerelement:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="statusstrip"></a>StatusStrip  
 <xref:System.Windows.Forms.StatusStrip> ersetzt die <xref:System.Windows.Forms.StatusBar> Steuerelement. Besondere Features von <xref:System.Windows.Forms.StatusStrip> ein benutzerdefiniertes Tabellenlayout enthalten, die Unterstützung für die Form der größenanpassung und verschieben zurechtzukommen, passte, und die `Spring` -Eigenschaft, die ermöglicht eine <xref:System.Windows.Forms.ToolStripStatusLabel> automatisch Platz zu füllen.  
  
 Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit sowohl <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in alle Ausrichtungen. Sie stehen standardmäßig zur Entwurfszeit für die <xref:System.Windows.Forms.StatusStrip> Steuerelement:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### <a name="contextmenustrip"></a>ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip> ersetzt <xref:System.Windows.Forms.ContextMenu>. Sie können Zuordnen einer <xref:System.Windows.Forms.ContextMenuStrip> mit jedes Steuerelement, und der rechten Maustaste auf automatisch zeigt an, die Kontext-Menü (oder das Kontextmenü). Sie können anzeigen, eine <xref:System.Windows.Forms.ContextMenuStrip> programmgesteuert durch die Verwendung der <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> Methode. <xref:System.Windows.Forms.ContextMenuStrip> unterstützt abbrechbare <xref:System.Windows.Forms.ToolStripDropDown.Opening> und <xref:System.Windows.Forms.ToolStripDropDown.Closing> Ereignisse, um dynamische Auffüllung und auf mehrere Szenarien zu behandeln. <xref:System.Windows.Forms.ContextMenuStrip> Bilder, Menüelemente Aktivierungszustand, Text, Zugriffsschlüssel, Verknüpfungen und hierarchische Menüs unterstützt.  
  
 Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit sowohl <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in alle Ausrichtungen. Sie stehen standardmäßig zur Entwurfszeit für die <xref:System.Windows.Forms.ContextMenuStrip> Steuerelement:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="toolstrip-generic-features"></a>ToolStrip-generische Funktionen  
 Die folgenden Themen beschreiben, Features und Verhaltensweisen, die generisch ist, sind die <xref:System.Windows.Forms.ToolStrip> und abgeleitete Steuerelemente.  
  
#### <a name="painting"></a>Zeichnen  
 Sie tun können benutzerdefinierte Darstellung <xref:System.Windows.Forms.ToolStrip> Steuerelemente auf unterschiedliche Weise. Wie bei anderen Windows Forms-Steuerelemente, die <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStripItem> beide verfügen über eine überschreibbare `OnPaint` Methoden und `Paint` Ereignisse. Wie bei regulären zeichnen, das Koordinatensystem relativ zum Clientbereich des Steuerelements; der oberen linken Ecke des Steuerelements ist 0, 0. Die `Paint` Ereignis und `OnPaint` -Methode für eine <xref:System.Windows.Forms.ToolStripItem> Verhalten sich wie andere Steuerelement Paint-Ereignisse.  
  
 Die <xref:System.Windows.Forms.ToolStrip> Steuerelemente bieten auch eine präzisere Zugriff auf das Rendern der Elemente und der Container über die <xref:System.Windows.Forms.ToolStripRenderer> -Klasse, die überschreibbare Methoden für das Zeichnen der Hintergrund, Hintergrund des Elements, Bild, Element-Taste, Elementtext verfügt, und Rahmen der <xref:System.Windows.Forms.ToolStrip>. Die Ereignisargumente für diese Methoden verfügbar machen, mehrere Eigenschaften wie z. B. Rechtecke, Farben und Textformate, die Sie nach Bedarf anpassen können.  
  
 Um nur einige Aspekte wie ein Element gezeichnet wird angepasst, Sie in der Regel außer Kraft setzen der <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Wenn Sie ein neues Element schreiben und alle Zeichenvorgänge steuern möchten, überschreiben die `OnPaint` Methode. Aus `OnPaint`, können Sie Methoden aus der <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 In der Standardeinstellung die <xref:System.Windows.Forms.ToolStrip> double wird gepuffert, nutzen die <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> festlegen.  
  
#### <a name="parenting"></a>Überordnen von  
 Das Konzept der Container den Besitz und Überordnung ist komplexer in <xref:System.Windows.Forms.ToolStrip> als in anderen Containersteuerelementen Windows Forms steuert. Dies ist erforderlich zur Unterstützung dynamischer Szenarien wie z. B. Überlauf, gemeinsames Verwenden von Dropdown--Elementen über mehrere <xref:System.Windows.Forms.ToolStrip> Elemente, und unterstützen die Generierung einer <xref:System.Windows.Forms.ContextMenuStrip> von einem Steuerelement.  
  
 Die folgende Liste beschreibt im Zusammenhang mit übergeordneter Elemente und erläutert deren Verwendung.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> greift auf das Element, das die Quelle des Dropdown-Elements ist. Dies ist vergleichbar mit <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, anstatt ein Steuerelement zu verwenden, gibt jedoch eine <xref:System.Windows.Forms.ToolStripItem>.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> Bestimmt, welches Steuerelement die Quelle ist von der <xref:System.Windows.Forms.ContextMenuStrip> Wenn mehrere Steuerelemente nutzen die gleiche <xref:System.Windows.Forms.ContextMenuStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> ist ein nur-Lese Accessor für die <xref:System.Windows.Forms.ToolStripItem.Parent%2A> Eigenschaft. Ein übergeordnetes Element unterscheidet sich von einem Besitzer, da ein übergeordnetes Element steht für die zurückgegebene aktuelle <xref:System.Windows.Forms.ToolStrip> in dem das Element angezeigt wird, die möglicherweise im Überlaufbereich,.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A> Gibt die <xref:System.Windows.Forms.ToolStrip> , deren Auflistung Elemente enthält, die aktuelle <xref:System.Windows.Forms.ToolStripItem>. Dies ist die beste Möglichkeit zum Verweisen auf <xref:System.Windows.Forms.ToolStrip.ImageList%2A> oder andere Eigenschaften der obersten Ebene <xref:System.Windows.Forms.ToolStrip> ohne speziellen Code zur Behandlung des Überlaufs schreiben.  
  
#### <a name="behavior-of-inherited-controls"></a>Verhalten des geerbten-Steuerelementen  
 Die folgenden Steuerelemente sind gesperrt, wenn sie bei der Vererbung verwendet werden:  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel> beinhaltet die Bereiche in einer <xref:System.Windows.Forms.ToolStripContainer> und einzelne <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.  
  
 Erstellen Sie z. B. eine neue Windows Forms-Anwendung mit mindestens einem der Steuerelemente in der vorherigen Liste. Legen Sie den Zugriffsmodifizierer von ein oder mehrere Steuerelemente, `public` oder `protected`, und klicken Sie dann das Projekt zu erstellen. Fügen Sie ein Formular, das aus dem ersten Formular erbt, und wählen Sie dann ein geerbtes Steuerelement. Das Steuerelement wird gesperrt, verhält sich wie bei der Zugriffsmodifizierer wurde `private`.  
  
#### <a name="toolstripcontainer-support-of-inheritance"></a>ToolStripContainer-Unterstützung von Vererbung  
 Die <xref:System.Windows.Forms.ToolStripContainer> -Steuerelement unterstützt beschränkte geerbte Szenarien, die im folgenden Beispiel ähnelt:  
  
1.  Erstellen Sie eine neue Windows Forms-Anwendung.  
  
2.  Fügen Sie dem Formular eine <xref:System.Windows.Forms.ToolStripContainer> hinzu.  
  
3.  Legen Sie den Zugriffsmodifizierer des der <xref:System.Windows.Forms.ToolStripContainer> zu `public` oder `protected`.  
  
4.  Fügen Sie eine beliebige Kombination von <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, und <xref:System.Windows.Forms.ContextMenuStrip> -Steuerelementen an die <xref:System.Windows.Forms.ToolStripPanel> Regionen die <xref:System.Windows.Forms.ToolStripContainer>.  
  
5.  Erstellen Sie das Projekt.  
  
6.  Fügen Sie ein Formular, das aus dem ersten Formular erbt.  
  
7.  Wählen Sie den geerbten <xref:System.Windows.Forms.ToolStripContainer> auf dem Formular.  
  
#### <a name="inherited-behavior-of-child-controls"></a>Geerbte Verhalten der untergeordneten Steuerelemente  
 Nachdem Sie die vorherigen Schritte abgeschlossen haben, tritt das folgende Verhalten des geerbte:  
  
-   Wird Sie im Designer das Steuerelement mit einem geerbten Symbol angezeigt.  
  
-   Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente sind gesperrt, die Sie nicht auswählen oder neu anordnen von deren Inhalt.  
  
-   Sie können Steuerelemente zum Hinzufügen der <xref:System.Windows.Forms.ToolStripContentPanel>, verschieben Sie die Steuerelemente und untergeordnete Steuerelemente von machen die <xref:System.Windows.Forms.ToolStripContentPanel>.  
  
-   Ihre Änderungen bleiben erhalten, nach dem Erstellen des Formulars.  
  
    > [!NOTE]
    >  Entfernen Sie den Zugriffsmodifizierer aus allen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente, die Teil einer <xref:System.Windows.Forms.ToolStripContainer>. Der Zugriffsmodifizierer des der <xref:System.Windows.Forms.ToolStripContainer> steuert das gesamte Steuerelement.  
  
#### <a name="partial-trust"></a>Teilweise Vertrauenswürdigkeit  
 Die Einschränkungen des `ToolStrip`s mit teilweiser Vertrauenswürdigkeit dienen zum Verhindern von unbeabsichtigten Eingabe von persönlichen Informationen, die durch nicht autorisierte Personen oder Dienste verwendet werden kann. Die Schutzmaßnahmen lauten wie folgt aus:  
  
-   `ToolStripDropDown` Steuerelemente erfordern <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> zum Anzeigen von Elementen in einem <xref:System.Windows.Forms.ToolStripControlHost>. Dies gilt für sowohl für systeminterne Steuerelemente wie z. B. <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>, und <xref:System.Windows.Forms.ToolStripProgressBar> wie auch, dass Benutzer erstellt steuert. Wenn diese Anforderung nicht erfüllt ist, werden diese Elemente nicht angezeigt. Es werden keine Ausnahmen ausgelöst.  
  
-   Festlegen der <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> Eigenschaft `false` ist nicht zulässig, und die abgebrochen werden <xref:System.Windows.Forms.ToolStripDropDown.Closing> Ereignisparameter wird ignoriert. Dies macht es unmöglich, die mehr als eine Tastenkombination, die ohne das Dropdownelement geschlossen wird, geben zu verwenden. Wenn diese Anforderung nicht erfüllt ist, werden diese Elemente nicht angezeigt. Es werden keine Ausnahmen ausgelöst.  
  
-   Viele Tastatureingaben Ereignisbehandlung wird nicht ausgelöst, wenn sie außer in teilweise vertrauenswürdigen Kontext auftreten <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>.  
  
-   Zugriffsschlüssel werden nicht verarbeitet, wenn <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> nicht gewährt wird.  
  
#### <a name="usage"></a>Verwendung  
 Die folgenden Verwendungsmuster haben einen Einfluss auf <xref:System.Windows.Forms.ToolStrip> Layout, Tastaturinteraktion und Endbenutzerverhalten:  
  
-   Kam ein <xref:System.Windows.Forms.ToolStripPanel>  
  
     Die <xref:System.Windows.Forms.ToolStrip> neu angeordnet werden können, innerhalb der <xref:System.Windows.Forms.ToolStripPanel> und über <xref:System.Windows.Forms.ToolStripPanel>s. Die `Dock` Eigenschaft wird ignoriert, und, wenn die <xref:System.Windows.Forms.ToolStrip.Stretch%2A> -Eigenschaft ist `false`, wird die Größe des der <xref:System.Windows.Forms.ToolStrip> wächst, wenn Elemente hinzugefügt werden die <xref:System.Windows.Forms.ToolStripPanel>. In der Regel die <xref:System.Windows.Forms.ToolStrip> der Tab-Reihenfolge nicht beteiligt.  
  
-   Angedockt  
  
     Die <xref:System.Windows.Forms.ToolStrip> befindet sich auf einer Seite eines Containers in einer festen Position, und seine Größe erstreckt sich über die ganze Kante, die an dem er angedockt ist. In der Regel die <xref:System.Windows.Forms.ToolStrip> der Tab-Reihenfolge nicht beteiligt.  
  
-   Absolut positioniert  
  
     Die <xref:System.Windows.Forms.ToolStrip> ist wie bei anderen Steuerelementen, da es gespeichert wird die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft, eine feste Größe hat, und in der Regel in der Aktivierreihenfolge beteiligt ist.  
  
#### <a name="keyboard-interaction"></a>Tastaturinteraktion  
  
##### <a name="access-keys"></a>Zugriffsschlüssel  
 In Kombination mit oder nach der ALT-Taste-Zugriffsschlüssel sind eine Möglichkeit zum Aktivieren eines Steuerelements über die Tastatur. <xref:System.Windows.Forms.ToolStrip> unterstützt sowohl explizite und implizite Tastenkombinationen. Explizite Definition verwendet, ein kaufmännisches und-Zeichen (&) vor dem Buchstaben. Implizite Definition verwendet einen Algorithmus, der versucht, finden ein übereinstimmendes Element entsprechend der Reihenfolge der Zeichen in einer bestimmten `Text` Eigenschaft.  
  
##### <a name="shortcut-keys"></a>Tastenkombinationen  
 Die Tastenkombination ein, die eine <xref:System.Windows.Forms.MenuStrip> verwenden eine Kombination der <xref:System.Windows.Forms.Keys> -Aufzählung (nicht auftragsspezifische) definieren Sie die Tastenkombination. Sie können auch die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> Eigenschaft, um eine Tastenkombination mit nur-Text anzuzeigen, z. B. das Anzeigen von "Del" anstelle von "Delete".  
  
##### <a name="navigation"></a>Navigation  
 Die ALT-Taste aktiviert die <xref:System.Windows.Forms.MenuStrip> verweist <xref:System.Windows.Forms.Form.MainMenuStrip%2A>. Von dort STRG + TAB zwischen navigiert <xref:System.Windows.Forms.ToolStrip> -Steuerelementen innerhalb `ToolStripPanel`s. Die TAB-Taste und die Pfeiltasten auf der Zehnertastatur Navigieren zwischen Elementen in einem <xref:System.Windows.Forms.ToolStrip>. Ein spezieller Algorithmus behandelt die Navigation im Überlaufbereich. LEERTASTE wählt eine <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, oder <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
##### <a name="focus-and-validation"></a>Fokus und Validierung  
 Bei der Aktivierung über die ALT-Taste, die <xref:System.Windows.Forms.MenuStrip> oder <xref:System.Windows.Forms.ToolStrip> in der Regel keine übernehmen und entfernen Sie den Fokus aus dem Steuerelement, der gerade den Fokus besitzt. Wenn ein gehostet wird Steuerelement, in der <xref:System.Windows.Forms.MenuStrip> oder eine Dropdownliste der <xref:System.Windows.Forms.MenuStrip>, das Steuerelement den Fokus erhält, wenn der Benutzer die TAB-Taste drückt. Im Allgemeinen die <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter>, und <xref:System.Windows.Forms.Control.Leave> Ereignisse <xref:System.Windows.Forms.MenuStrip> möglicherweise nicht ausgelöst werden, wenn sie über die Tastatur aktiviert werden. In solchen Fällen verwenden die <xref:System.Windows.Forms.MenuStrip.MenuActivate> und <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> Ereignisse stattdessen.  
  
 In der Standardeinstellung <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> ist `false`. Rufen Sie <xref:System.Windows.Forms.ContainerControl.Validate%2A> explizit in Ihrem Formular eine Überprüfung durchführen.  
  
#### <a name="layout"></a>Layout  
 Sie steuern, <xref:System.Windows.Forms.ToolStrip> Layout durch Auswahl einer der Member der <xref:System.Windows.Forms.ToolStripLayoutStyle> mit der <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> Eigenschaft.  
  
##### <a name="stack-layouts"></a>Stack-Layouts  
 Stapeln wird das Anordnen der Elemente nebeneinander an beiden Enden der <xref:System.Windows.Forms.ToolStrip>. Die folgende Liste beschreibt die Stack-Layouts.  
  
-   Standardmäßig ist <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow> festgelegt. Diese Einstellung bewirkt, dass die <xref:System.Windows.Forms.ToolStrip> sein Layout automatisch in Übereinstimmung mit der <xref:System.Windows.Forms.ToolStrip.Orientation%2A> Eigenschaft um Zieh- und zu verarbeiten.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow> Rendert die <xref:System.Windows.Forms.ToolStrip> Elemente nebeneinander vertikal.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow> Rendert die <xref:System.Windows.Forms.ToolStrip> horizontal nebeneinander Elemente.  
  
##### <a name="other-features-of-stack-layouts"></a>Andere Funktionen von Stapeln von Layouts  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Bestimmt das Ende der <xref:System.Windows.Forms.ToolStrip> an dem das Element ausgerichtet ist.  
  
 Wenn Elemente nicht in passen die <xref:System.Windows.Forms.ToolStrip>, eine Schaltfläche "Überlauf" automatisch angezeigt wird. Die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> eigenschafteneinstellung bestimmt, ob ein Element im Überlaufbereich stets, je nach Bedarf oder nie angezeigt wird.  
  
 In der <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> Ereignis können Sie überprüfen die <xref:System.Windows.Forms.ToolStripItem.Placement%2A> Eigenschaft, um zu bestimmen, ob ein Element, auf dem hauptblatt platziert wurde <xref:System.Windows.Forms.ToolStrip>, der Überlauf <xref:System.Windows.Forms.ToolStrip>, oder wenn Sie derzeit nicht angezeigt wird. Die typische Gründe, warum ein Element wird nicht angezeigt, werden, dass das Element nicht auf dem hauptblatt passen <xref:System.Windows.Forms.ToolStrip> und die zugehörige <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> -Eigenschaft wurde festgelegt, um <xref:System.Windows.Forms.ToolStripItemOverflow.Never>.  
  
 Stellen eine <xref:System.Windows.Forms.ToolStrip> verschoben, wenn man diese Anwendungen einer <xref:System.Windows.Forms.ToolStripPanel> und seine <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> zu <xref:System.Windows.Forms.ToolStripGripStyle.Visible>.  
  
##### <a name="other-layout-options"></a>Andere Optionen für Layout  
 Die anderen Layoutoptionen sind <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> und <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>.  
  
##### <a name="flow-layout"></a>Flusslayout  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layout ist die Standardeinstellung für <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, und <xref:System.Windows.Forms.ToolStripOverflow>. Es ähnelt der <xref:System.Windows.Forms.FlowLayoutPanel>. Die Funktionen von <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layout lauten wie folgt:  
  
-   Alle Funktionen der <xref:System.Windows.Forms.FlowLayoutPanel> verfügbar gemacht werden die <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> Eigenschaft. Müssen Sie eine Umwandlung der <xref:System.Windows.Forms.LayoutSettings> -Klasse eine <xref:System.Windows.Forms.FlowLayoutSettings> Klasse.  
  
-   Sie können die <xref:System.Windows.Forms.ToolStripItem.Dock%2A> und <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> Eigenschaften im Code, um die Elemente in der Zeile ausgerichtet.  
  
-   Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>-Eigenschaft wird ignoriert.  
  
-   In der <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> Ereignis können Sie überprüfen die <xref:System.Windows.Forms.ToolStripItem.Placement%2A> Eigenschaft, um zu bestimmen, ob ein Element, auf dem hauptblatt platziert wurde <xref:System.Windows.Forms.ToolStrip> oder nicht geeignet.  
  
-   Der Ziehpunkt wird nicht gerendert, und daher eine <xref:System.Windows.Forms.ToolStrip> in <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layoutstil in eine <xref:System.Windows.Forms.ToolStripPanel> kann nicht verschoben werden.  
  
-   Die <xref:System.Windows.Forms.ToolStrip> dokumentüberlauf-Schaltfläche wird nicht gerendert, und <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> wird ignoriert.  
  
##### <a name="table-layout"></a>Tabellenlayout  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> Layout ist die Standardeinstellung für <xref:System.Windows.Forms.StatusStrip>. Sie ähnelt damit <xref:System.Windows.Forms.TableLayoutPanel>. Die Funktionen von <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layout lauten wie folgt:  
  
-   Alle Funktionen der <xref:System.Windows.Forms.TableLayoutPanel> verfügbar gemacht werden die <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> Eigenschaft. Müssen Sie eine Umwandlung der <xref:System.Windows.Forms.LayoutSettings> -Klasse eine <xref:System.Windows.Forms.TableLayoutSettings> Klasse.  
  
-   Sie können die <xref:System.Windows.Forms.ToolStripItem.Dock%2A> und <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> Eigenschaften im Code, um die Elemente in der Tabellenzelle ausrichten.  
  
-   Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>-Eigenschaft wird ignoriert.  
  
-   In der <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> Ereignis können Sie überprüfen die <xref:System.Windows.Forms.ToolStripItem.Placement%2A> Eigenschaft, um zu bestimmen, ob ein Element, auf dem hauptblatt platziert wurde <xref:System.Windows.Forms.ToolStrip> oder nicht geeignet.  
  
-   Der Ziehpunkt wird nicht gerendert, und daher eine <xref:System.Windows.Forms.ToolStrip> in <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> Layoutstil in eine <xref:System.Windows.Forms.ToolStripPanel> kann nicht verschoben werden.  
  
-   Die <xref:System.Windows.Forms.ToolStrip> dokumentüberlauf-Schaltfläche wird nicht gerendert, und <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> wird ignoriert.  
  
## <a name="toolstripitem"></a>ToolStripItem  
 Die folgenden Themen beschreiben <xref:System.Windows.Forms.ToolStripItem> und die Steuerelemente, die von ihr abgeleitet werden.  
  
 <xref:System.Windows.Forms.ToolStripItem> ist die abstrakte Basisklasse für alle Elemente, die näher betrachten einen <xref:System.Windows.Forms.ToolStrip>. Das folgende Objekt Modell zeigt das <xref:System.Windows.Forms.ToolStripItem> Vererbungshierarchie.  
  
 ![ToolStripItem-Objektmodell](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.gif "ToolStripItemObjectModel")  
ToolStripItem-Objektmodell  
  
 <xref:System.Windows.Forms.ToolStripItem> Klassen, die entweder direkt von erben <xref:System.Windows.Forms.ToolStripItem>, oder indirekt von <xref:System.Windows.Forms.ToolStripItem> über <xref:System.Windows.Forms.ToolStripControlHost> oder <xref:System.Windows.Forms.ToolStripDropDownItem>.  
  
 <xref:System.Windows.Forms.ToolStripItem> Steuerelemente müssen enthalten sein, einem <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, oder <xref:System.Windows.Forms.ContextMenuStrip> und kann nicht direkt zu einem Formular hinzugefügt werden. Die verschiedenen Containerklassen enthalten eine geeignete Teilmenge von <xref:System.Windows.Forms.ToolStripItem> Steuerelemente.  
  
 Die folgende Tabelle enthält die Aktie <xref:System.Windows.Forms.ToolStripItem> Steuerelemente und die Container, in dem sie am besten aussehen. Obwohl alle <xref:System.Windows.Forms.ToolStrip> Element gehostet werden kann, in einem <xref:System.Windows.Forms.ToolStrip>-abgeleiteten Container diese Elemente wurden entworfen, um die beste, in den folgenden Containern suchen:  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown> wird in der Designer-Toolbox nicht angezeigt.  
  
|Enthaltene Element|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
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
 <xref:System.Windows.Forms.ToolStripButton> ist das Schaltflächenelement für <xref:System.Windows.Forms.ToolStrip>. Sie können mit verschiedenen Rahmenarten anzeigen, und können Sie sie zum darstellen und Betriebszustände aktivieren. Sie können auch definieren, um standardmäßig den Fokus haben.  
  
### <a name="toolstriplabel"></a>ToolStripLabel  
 Die <xref:System.Windows.Forms.ToolStripLabel> Bezeichnung ist der Funktionsumfang in <xref:System.Windows.Forms.ToolStrip> Steuerelemente. Die <xref:System.Windows.Forms.ToolStripLabel> ähnelt einem <xref:System.Windows.Forms.ToolStripButton> , die Fokus standardmäßig keine ab und, die nicht als mithilfe von Push übertragene oder ausgewählte gerendert.  
  
 <xref:System.Windows.Forms.ToolStripLabel> unterstützt als gehostetes Element Zugriffsschlüssel ein.  
  
 Verwenden der <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, und <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> Eigenschaften für eine <xref:System.Windows.Forms.ToolStripLabel> zur Unterstützung von Link-Steuerelement in einem <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel> ist eine Version von <xref:System.Windows.Forms.ToolStripLabel> entwickelt, die speziell zur Verwendung in <xref:System.Windows.Forms.StatusStrip>. Besondere Features umfassen <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>, und <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
### <a name="toolstripseparator"></a>ToolStripSeparator  
 Die <xref:System.Windows.Forms.ToolStripSeparator> Fügt eine vertikale oder horizontale Linie zu einer Symbolleiste oder im Menü, je nach Ausrichtung. Mit dieser Lösung Gruppierung oder Unterschied zwischen den Elementen, z. B. in einem Menü.  
  
 Sie können Hinzufügen einer <xref:System.Windows.Forms.ToolStripSeparator> zur Entwurfszeit durch Auswahl in einem Dropdown-Liste. Sie können jedoch auch automatisch erstellen eine <xref:System.Windows.Forms.ToolStripSeparator> durch Eingabe eines Bindestrichs (-) in den Designer Vorlagenknoten oder in der <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Methode.  
  
### <a name="toolstripcontrolhost"></a>ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost> ist die abstrakte Basisklasse für <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>, und <xref:System.Windows.Forms.ToolStripProgressBar>. <xref:System.Windows.Forms.ToolStripControlHost> können andere Steuerelemente, einschließlich benutzerdefinierter Steuerelemente, auf zwei Arten hosten:  
  
-   Erstellen einer <xref:System.Windows.Forms.ToolStripControlHost> mit eine abgeleitete Klasse <xref:System.Windows.Forms.Control>. Um das gehostete Steuerelement und Eigenschaften vollständig zugreifen zu können, müssen Sie eine Umwandlung der <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> Eigenschaft, um die tatsächliche Klasse darstellt.  
  
-   Erweitern Sie <xref:System.Windows.Forms.ToolStripControlHost>, und rufen Sie in der geerbten Klasse den Standardkonstruktor, den Konstruktor der Basisklasse übergeben eine abgeleitete Klasse <xref:System.Windows.Forms.Control>. Mit dieser Option können Sie das allgemeine Steuerelementmethoden und Eigenschaften für den leichteren Zugriff im umschließen einer <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripcombobox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox> ist die <xref:System.Windows.Forms.ComboBox> optimiert, für das Hosten in einem <xref:System.Windows.Forms.ToolStrip>. Eine Teilmenge der Eigenschaften und Ereignisse des gehosteten Steuerelements werden verfügbar gemacht, an die <xref:System.Windows.Forms.ToolStripComboBox> Ebene, aber die zugrunde liegende <xref:System.Windows.Forms.ComboBox> Steuerelement ist vollständig zugegriffen werden kann, über die <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> Eigenschaft.  
  
### <a name="toolstriptextbox"></a>ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox> ist die <xref:System.Windows.Forms.TextBox> optimiert, für das Hosten in einem <xref:System.Windows.Forms.ToolStrip>. Eine Teilmenge der Eigenschaften und Ereignisse des gehosteten Steuerelements werden verfügbar gemacht, an die <xref:System.Windows.Forms.ToolStripTextBox> Ebene, aber die zugrunde liegende <xref:System.Windows.Forms.TextBox> Steuerelement ist vollständig zugegriffen werden kann, über die <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> Eigenschaft.  
  
### <a name="toolstripprogressbar"></a>ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar> ist die <xref:System.Windows.Forms.ProgressBar> optimiert, für das Hosten in einem <xref:System.Windows.Forms.ToolStrip>. Eine Teilmenge der Eigenschaften und Ereignisse des gehosteten Steuerelements werden verfügbar gemacht, an die <xref:System.Windows.Forms.ToolStripProgressBar> Ebene, aber die zugrunde liegende <xref:System.Windows.Forms.ProgressBar> Steuerelement ist vollständig zugegriffen werden kann, über die <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> Eigenschaft.  
  
### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem> ist die abstrakte Basisklasse für <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>, und <xref:System.Windows.Forms.ToolStripSplitButton>, die können Elemente direkt hosten oder zusätzliche Elemente in einem Dropdown--Container hostet. Diesem Zweck legen die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> Eigenschaft, um eine <xref:System.Windows.Forms.ToolStripDropDown> und Einstellung der <xref:System.Windows.Forms.ToolStrip.Items%2A> Eigenschaft der <xref:System.Windows.Forms.ToolStripDropDown>. Zugriff auf diese Dropdown-Elemente, die direkt über die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> Eigenschaft.  
  
### <a name="toolstripmenuitem"></a>ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem> ist eine <xref:System.Windows.Forms.ToolStripDropDownItem> dieses Produkt funktioniert mit <xref:System.Windows.Forms.ToolStripDropDownMenu> und <xref:System.Windows.Forms.ContextMenuStrip> die besondere Hervorhebung, Layout und Spalte Anordnung für Menüs zu behandeln.  
  
### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton> sieht wie <xref:System.Windows.Forms.ToolStripButton>, aber es zeigt einen Dropdownbereich, wenn der Benutzer darauf klickt. Ein- oder Ausblenden der Dropdown-Pfeil durch Festlegen der <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> Eigenschaft. <xref:System.Windows.Forms.ToolStripDropDownButton> hostet eine <xref:System.Windows.Forms.ToolStripOverflowButton> , die Elemente angezeigt, die overflow der <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripsplitbutton"></a>ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton> kombiniert die Schaltfläche und Funktionalität der Dropdown-Schaltfläche.  
  
 Verwenden der <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> Eigenschaft zum Synchronisieren der <xref:System.Windows.Forms.Control.Click> Ereignis des ausgewählten Dropdown-Elements mit dem Element, auf die Schaltfläche angezeigt.  
  
### <a name="toolstripitem-generic-features"></a>ToolStripItem-generische Funktionen  
 <xref:System.Windows.Forms.ToolStripItem> bietet die folgenden allgemeinen Features und Optionen für erbende Steuerelemente:  
  
-   Core-Ereignisse  
  
-   Handhabung von Images  
  
-   Ausrichtung  
  
-   Die Beziehung zwischen Text und Bild  
  
-   Anzeigestil  
  
#### <a name="core-events"></a>Core-Ereignisse  
 <xref:System.Windows.Forms.ToolStripItem> Steuerelemente erhalten ihre eigenen klicken, Maus und Paint-Ereignisse und können einige vorverarbeitung auch Tastatur ausführen.  
  
#### <a name="image-handling"></a>Handhabung von Images  
 Die <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>, und <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> Eigenschaften beziehen sich auf verschiedene Aspekte der Bildbehandlung. Verwenden von Bildern in <xref:System.Windows.Forms.ToolStrip> Steuerelemente durch Festlegen dieser Eigenschaften direkt oder durch Festlegen der Ausführung nur zur Laufzeit <xref:System.Windows.Forms.ToolStrip.ImageList%2A> Eigenschaft.  
  
 Bildskalierung richtet sich nach die Interaktion der Eigenschaften, die in beiden <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStripItem>wie folgt:  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> die Dezimalstellen des das endgültige Bild wie festgelegt durch die Kombination des Bilds <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> Einstellung und des Containers <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> festlegen.  
  
    -   Wenn <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> ist `true` (Standard) und <xref:System.Windows.Forms.ToolStripItemImageScaling> ist <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, keine Bildskalierung, und die <xref:System.Windows.Forms.ToolStrip> Größe ist, das größte Element oder eine vorgegebene Mindestgröße.  
  
    -   Wenn <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> ist `false` und <xref:System.Windows.Forms.ToolStripItemImageScaling> ist <xref:System.Windows.Forms.ToolStripItemImageScaling.None>, weder das Bild noch <xref:System.Windows.Forms.ToolStrip> Skalierung erfolgt.  
  
#### <a name="alignment"></a>Ausrichtung  
 Der Wert des der <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> -Eigenschaft bestimmt das Ende der <xref:System.Windows.Forms.ToolStrip> an der ein Element erscheint. Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Eigenschaft funktioniert nur, wenn den Layoutstil eines der <xref:System.Windows.Forms.ToolStrip> auf einen der Stack Overflow-Werte festgelegt ist.  
  
 Elemente befinden sich auf die <xref:System.Windows.Forms.ToolStrip> in der Reihenfolge, in dem die Elemente angezeigt, in der Items-Auflistung werden. Um programmgesteuert zu ändern, in dem ein Element angeordnet wird, verwenden Sie die <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> Methode, um das Element in der Auflistung verschoben werden. Diese Methode verschiebt das Element aber nicht dupliziert werden.  
  
#### <a name="text-and-image-relationship"></a>Text- und Image-Beziehung  
 Die <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> -Eigenschaft definiert die relative Platzierung des Bilds in Bezug auf den Text auf einer <xref:System.Windows.Forms.ToolStripItem>. Elemente, die ein Bild, Text oder beide fehlen, werden als besondere Fälle behandelt, damit die <xref:System.Windows.Forms.ToolStripItem> einen leeren Bereich für die fehlt ein Element oder Elemente nicht angezeigt.  
  
#### <a name="display-style"></a>Anzeigestil  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> können Sie anzeigen, wie Sie möchten die Werte von Text- und Image-Eigenschaften eines Elements festgelegt. Dies wird normalerweise verwendet, um nur das Anzeigeformat zu ändern, wenn das gleiche Element in einem anderen Kontext angezeigt.  
  
## <a name="accessory-classes"></a>Zusätzliche Klassen  
 Klassen, die verschiedene andere Funktionen zählen:  
  
-   <xref:System.Windows.Forms.ToolStripManager> unterstützt <xref:System.Windows.Forms.ToolStrip>-Aufgaben für die gesamte Anwendungen, z. B. zusammenführen, Einstellungen und die Renderer.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> können Sie einen bestimmten Stil oder eine Design anwenden einer <xref:System.Windows.Forms.ToolStrip> ganz einfach.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> erstellt Stifte und Pinsel auf Grundlage einer austauschbaren Farbtabelle (<xref:System.Windows.Forms.ProfessionalColorTable>).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> Wendet Systemfarben und einem flachen visuellen Stil zu <xref:System.Windows.Forms.ToolStrip> Anwendungen.  
  
-   <xref:System.Windows.Forms.ToolStripContainer> ist vergleichbar mit <xref:System.Windows.Forms.SplitContainer>. Er verwendet die vier Bereiche der angedockten Seite (Instanzen von <xref:System.Windows.Forms.ToolStripPanel>) und einen zentralen Bereich (eine Instanz von <xref:System.Windows.Forms.ToolStripContentPanel>) um eine typische Anordnung zu erstellen. Die Seite Bereiche können nicht entfernt werden, jedoch können Sie sie ausblenden. Sie können weder entfernen noch den zentralen Bereich ausblenden. Sie können eine oder mehrere anordnen <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, oder <xref:System.Windows.Forms.StatusStrip> Steuerelemente in den Seitenbereichen, und Sie können den zentralen Bereich für andere Steuerelemente verwenden. Die <xref:System.Windows.Forms.ToolStripContentPanel> bietet auch eine Möglichkeit, renderunterstützung in den Text des Formulars für ein konsistentes Erscheinungsbild zu erhalten. <xref:System.Windows.Forms.ToolStripContainer> mehrfachen Dokumentschnittstelle (MDI) unterstützt nicht.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> Dient zum Verschieben und Anordnen von <xref:System.Windows.Forms.ToolStrip> Steuerelemente. Sie können nur einen Bereich verwenden, wenn Sie möchten, und <xref:System.Windows.Forms.ToolStripPanel> funktioniert gut in MDI-Szenarien.  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [Zusammenfassung der ToolStrip-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
- [ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
- [MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
- [StatusStrip-Steuerelement](../../../../docs/framework/winforms/controls/statusstrip-control.md)
- [ContextMenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
- [BindingNavigator-Steuerelement](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
