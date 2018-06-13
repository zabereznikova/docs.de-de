---
title: Architektur des ToolStrip-Steuerelements
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: fd00fff6c745f5f7991c038dec305b5d45761656
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542157"
---
# <a name="toolstrip-control-architecture"></a>Architektur des ToolStrip-Steuerelements
Die <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStripItem> Klassen bieten eine flexible, erweiterbare System für die Anzeige von Symbolleisten-, Status- und im Menü-Elemente. Diese Klassen sind in enthalten die <xref:System.Windows.Forms> Namespace, und sie werden alle in der Regel mit dem Präfix "ToolStrip" benannt (z. B. <xref:System.Windows.Forms.ToolStripOverflow>) oder mit dem Suffix "Streifen" (z. B. <xref:System.Windows.Forms.MenuStrip>).  
  
## <a name="toolstrip"></a>ToolStrip  
 Die folgenden Themen beschreiben <xref:System.Windows.Forms.ToolStrip> und die Steuerelemente, die sich davon herleiten.  
  
 <xref:System.Windows.Forms.ToolStrip> ist die abstrakte Basisklasse für <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, und <xref:System.Windows.Forms.ContextMenuStrip>. Das folgende Objekt Modell zeigt das <xref:System.Windows.Forms.ToolStrip> Vererbungshierarchie.  
  
 ![ToolStrip-Objektmodell](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.gif "ToolStripObjectModel")  
ToolStrip-Objektmodell  
  
 Sie erreichen die Elemente in einer <xref:System.Windows.Forms.ToolStrip> über die <xref:System.Windows.Forms.ToolStrip.Items%2A> Auflistung. Sie erreichen die Elemente in einer <xref:System.Windows.Forms.ToolStripDropDownItem> über die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> Auflistung. In einer abgeleiteten Klasse <xref:System.Windows.Forms.ToolStrip>, können Sie auch die <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> Eigenschaft, um nur diese Elemente zugreifen, die gerade angezeigt werden. Dies sind die Elemente, die derzeit nicht in ein Überlaufmenü enthalten sind.  
  
 Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit sowohl <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in alle Ausrichtungen. Sie stehen standardmäßig zur Entwurfszeit für die <xref:System.Windows.Forms.ToolStrip> Steuerelement:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="menustrip"></a>MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> ist der Container der obersten Ebene, die ersetzt <xref:System.Windows.Forms.MainMenu>. Darüber hinaus schlüsselverarbeitung und mehrere Document Interface (MDI)-Funktionen. Funktionell <xref:System.Windows.Forms.ToolStripDropDownItem> und <xref:System.Windows.Forms.ToolStripMenuItem> zusammen mit Geschäfts- <xref:System.Windows.Forms.MenuStrip>, obwohl sie abgeleitet sind <xref:System.Windows.Forms.ToolStripItem>.  
  
 Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit sowohl <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in alle Ausrichtungen. Sie stehen standardmäßig zur Entwurfszeit für die <xref:System.Windows.Forms.MenuStrip> Steuerelement:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="statusstrip"></a>StatusStrip  
 <xref:System.Windows.Forms.StatusStrip> ersetzt die <xref:System.Windows.Forms.StatusBar> Steuerelement. Besondere Features von <xref:System.Windows.Forms.StatusStrip> ein benutzerdefiniertes Layout enthalten, die Unterstützung für die Form der größenanpassung und verschieben Umgang, und die `Spring` -Eigenschaft, wodurch eine <xref:System.Windows.Forms.ToolStripStatusLabel> zu den verfügbaren Platz auszufüllen, automatisch.  
  
 Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit sowohl <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in alle Ausrichtungen. Sie stehen standardmäßig zur Entwurfszeit für die <xref:System.Windows.Forms.StatusStrip> Steuerelement:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### <a name="contextmenustrip"></a>ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip> ersetzt <xref:System.Windows.Forms.ContextMenu>. Die Zuordnung kann eine <xref:System.Windows.Forms.ContextMenuStrip> mit jedes Steuerelement, und der rechten Maustaste auf zeigt automatisch an den Kontext (oder Kontextmenü). Sie können anzeigen, eine <xref:System.Windows.Forms.ContextMenuStrip> programmgesteuert durch die Verwendung der <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> Methode. <xref:System.Windows.Forms.ContextMenuStrip> unterstützt abbrechbare <xref:System.Windows.Forms.ToolStripDropDown.Opening> und <xref:System.Windows.Forms.ToolStripDropDown.Closing> Ereignisse dynamische Auffüllung und auf mehrere Szenarien behandelt. <xref:System.Windows.Forms.ContextMenuStrip> Bilder, Menüelement Aktivierungszustand, Text, Zugriffstasten, Tastenkombinationen und hierarchische Menüs unterstützt.  
  
 Die folgenden Elemente sind speziell für die nahtlose Zusammenarbeit mit sowohl <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in alle Ausrichtungen. Sie stehen standardmäßig zur Entwurfszeit für die <xref:System.Windows.Forms.ContextMenuStrip> Steuerelement:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="toolstrip-generic-features"></a>ToolStrip-generische Funktionen  
 Die folgenden Themen beschreiben die Funktionen und das Verhalten, die generisch ist, sind die <xref:System.Windows.Forms.ToolStrip> und abgeleitete Steuerelemente.  
  
#### <a name="painting"></a>Paint-Ereignisse  
 Benutzerdefiniertes Zeichnen erfolgt, in <xref:System.Windows.Forms.ToolStrip> Steuerelemente auf verschiedene Weise. Wie bei anderen Windows Forms-Steuerelemente, die <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStripItem> verfügen beide über überschreibbare `OnPaint` Methoden und `Paint` Ereignisse. Wie bei regulären zeichnen, das Koordinatensystem relativ zum Clientbereich des Steuerelements ist; d. h. der linken oberen Ecke des Steuerelements ist 0, 0. Die `Paint` Ereignis und `OnPaint` Methode für eine <xref:System.Windows.Forms.ToolStripItem> Verhalten sich wie andere Steuerelement Paint-Ereignissen.  
  
 Die <xref:System.Windows.Forms.ToolStrip> -Steuerelemente bieten auch eine genauere Zugriff auf das Rendern der Elemente und der Container über die <xref:System.Windows.Forms.ToolStripRenderer> -Klasse, die zum Zeichnen der Hintergrundfarbe, Elementhintergrund, Elementbild, Element Pfeil, Elementtext überschreibbare Methoden verfügt, und den Rahmen der <xref:System.Windows.Forms.ToolStrip>. Die Ereignisargumente für diese Methoden verfügbar machen, mehrere Eigenschaften, z. B. Rechtecke, Farben und Textformate, die nach Bedarf angepasst werden können.  
  
 Um nur einige Aspekte wie ein Element gezeichnet wird angepasst, überschreiben Sie in der Regel die <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Wenn Sie ein neues Element schreiben und alle Aspekte der der Zeichnung steuern möchten, überschreiben die `OnPaint` Methode. Innerhalb von `OnPaint`, können Sie Methoden aus der <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Wird standardmäßig die <xref:System.Windows.Forms.ToolStrip> doppelte wird gepuffert, nutzen die <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> Einstellung.  
  
#### <a name="parenting"></a>Überordnung  
 Das Konzept der des Containerbesitzes und Überordnung ist komplexer in <xref:System.Windows.Forms.ToolStrip> als in anderen Containersteuerelementen Windows Forms steuert. Dies ist erforderlich, z. B. Überlauf, Freigabe Dropdownelementen für mehrere dynamische Szenarien zu unterstützen <xref:System.Windows.Forms.ToolStrip> Elemente, und unterstützt die Generierung von einem <xref:System.Windows.Forms.ContextMenuStrip> aus einem Steuerelement.  
  
 In der folgenden Liste werden Member, die im Zusammenhang mit Überordnung beschrieben und erläutert deren Verwendung.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> greift auf das Element, das die Quelle des Dropdown-Elements ist. Dies ist vergleichbar mit <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, anstatt ein Steuerelement, es gibt jedoch eine <xref:System.Windows.Forms.ToolStripItem>.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> Bestimmt, welches Steuerelement die Quelle ist von der <xref:System.Windows.Forms.ContextMenuStrip> mehrere Steuerelemente, die bei der Freigabe für die gleiche <xref:System.Windows.Forms.ContextMenuStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> ist ein nur-Lese Accessor für die <xref:System.Windows.Forms.ToolStripItem.Parent%2A> Eigenschaft. Ein übergeordnetes Element unterscheidet sich von einem Besitzer, da ein übergeordnetes Element zurückgegebenen aktuellen kennzeichnet <xref:System.Windows.Forms.ToolStrip> in dem das Element angezeigt wird, die möglicherweise in den Überlaufbereich,.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A> Gibt die <xref:System.Windows.Forms.ToolStrip> , deren Items-Auflistung enthält die aktuelle <xref:System.Windows.Forms.ToolStripItem>. Dies ist die beste Methode zum Verweisen auf <xref:System.Windows.Forms.ToolStrip.ImageList%2A> oder andere Eigenschaften in der obersten Ebene <xref:System.Windows.Forms.ToolStrip> ohne speziellen Code zur Behandlung des Überlaufs schreiben.  
  
#### <a name="behavior-of-inherited-controls"></a>Verhalten des geerbten Steuerelemente  
 Die folgenden Steuerelemente werden gesperrt, wenn sie bei der Vererbung verwendet werden:  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel> beinhaltet die Bereiche in einer <xref:System.Windows.Forms.ToolStripContainer> und einzelne <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.  
  
 Beispielsweise erstellen Sie eine neue Windows Forms-Anwendung mithilfe eines oder mehrere der Steuerelemente aus der vorangehenden Liste. Legen Sie den Zugriffsmodifizierer, der ein oder mehrere Steuerelemente, `public` oder `protected`, und erstellen Sie das Projekt. Fügen Sie ein Formular, das aus dem ersten Formular erbt, und wählen Sie dann ein geerbtes Steuerelement aus. Das Steuerelement wird gesperrt angezeigt und verhält, als wäre der Zugriffsmodifizierer `private`.  
  
#### <a name="toolstripcontainer-support-of-inheritance"></a>ToolStripContainer-Unterstützung von Vererbung  
 Die <xref:System.Windows.Forms.ToolStripContainer> Steuerelement unterstützt beschränkte geerbte Szenarien, wie im folgenden Beispiel:  
  
1.  Erstellen Sie eine neue Windows Forms-Anwendung.  
  
2.  Fügen Sie dem Formular eine <xref:System.Windows.Forms.ToolStripContainer> hinzu.  
  
3.  Legen Sie den Zugriffsmodifizierer für die <xref:System.Windows.Forms.ToolStripContainer> auf `public` oder `protected`.  
  
4.  Fügen Sie eine beliebige Kombination von <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, und <xref:System.Windows.Forms.ContextMenuStrip> -Steuerelementen an die <xref:System.Windows.Forms.ToolStripPanel> Bereiche der <xref:System.Windows.Forms.ToolStripContainer>.  
  
5.  Erstellen Sie das Projekt.  
  
6.  Fügen Sie ein Formular, das aus dem ersten Formular erbt.  
  
7.  Wählen Sie die geerbte <xref:System.Windows.Forms.ToolStripContainer> auf dem Formular.  
  
#### <a name="inherited-behavior-of-child-controls"></a>Geerbte Verhalten von untergeordneten Steuerelementen  
 Nachdem Sie die vorherigen Schritte abgeschlossen haben, tritt das folgende Verhalten des geerbte:  
  
-   Im Designer wird das Steuerelement mit einem geerbten Symbol angezeigt.  
  
-   Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente sind gesperrt, sodass Sie nicht auswählen oder neu anordnen deren Inhalt.  
  
-   Sie können Steuerelemente zum Hinzufügen der <xref:System.Windows.Forms.ToolStripContentPanel>, verschieben Sie die Steuerelemente, und stellen sie untergeordnete Steuerelemente von der <xref:System.Windows.Forms.ToolStripContentPanel>.  
  
-   Die Änderungen beibehalten, nach dem Erstellen des Formulars.  
  
    > [!NOTE]
    >  Entfernen Sie den Zugriffsmodifizierer aus allen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente, die Teil einer <xref:System.Windows.Forms.ToolStripContainer>. Der Zugriffsmodifizierer der <xref:System.Windows.Forms.ToolStripContainer> steuert das gesamte Steuerelement.  
  
#### <a name="partial-trust"></a>Teilweise Vertrauenswürdigkeit  
 Die Einschränkungen des `ToolStrip`s unter teilweiser Vertrauenswürdigkeit dienen zur unbeabsichtigten Eingabe von persönlichen Informationen zu verhindern, die durch nicht autorisierte Personen oder Dienste verwendet werden kann. Die Schutzmaßnahmen lauten wie folgt:  
  
-   `ToolStripDropDown` Steuerelemente erfordern <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> zum Anzeigen von Elementen in einem <xref:System.Windows.Forms.ToolStripControlHost>. Dies gilt sowohl für systeminterne Steuerelemente wie z. B. <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>, und <xref:System.Windows.Forms.ToolStripProgressBar> als auch auf benutzerdefinierte Steuerelemente. Wenn diese Anforderung nicht erfüllt wird, werden diese Elemente nicht angezeigt. Es werden keine Ausnahmen ausgelöst.  
  
-   Festlegen der <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> Eigenschaft `false` ist nicht zulässig, und der abbrechbare <xref:System.Windows.Forms.ToolStripDropDown.Closing> Ereignisparameter wird ignoriert. Dadurch nicht möglich, mehr als eine Tastenkombination eingeben, ohne das Dropdown-Element verworfen. Wenn diese Anforderung nicht erfüllt wird, werden diese Elemente nicht angezeigt. Es werden keine Ausnahmen ausgelöst.  
  
-   Viele Tastatureingabe Behandlung von Ereignissen werden nicht ausgelöst, wenn sie nicht in teilweise vertrauenswürdigen Kontexten auftreten <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>.  
  
-   Zugriffstasten werden nicht verarbeitet, wenn <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> nicht gewährt wird.  
  
#### <a name="usage"></a>Verwendung  
 Die folgenden Verwendungsmuster haben einen Einfluss auf <xref:System.Windows.Forms.ToolStrip> Layout, Tastaturinteraktion und Endbenutzerverhalten:  
  
-   Eingebunden eine <xref:System.Windows.Forms.ToolStripPanel>  
  
     Die <xref:System.Windows.Forms.ToolStrip> neu angeordnet werden können, innerhalb der <xref:System.Windows.Forms.ToolStripPanel> und über <xref:System.Windows.Forms.ToolStripPanel>s. Die `Dock` Eigenschaft wird ignoriert, und, wenn die <xref:System.Windows.Forms.ToolStrip.Stretch%2A> Eigenschaft ist `false`, die Größe der <xref:System.Windows.Forms.ToolStrip> wächst, wenn Elemente hinzugefügt werden die <xref:System.Windows.Forms.ToolStripPanel>. In der Regel die <xref:System.Windows.Forms.ToolStrip> nicht Teil der Aktivierreihenfolge.  
  
-   Angedockt  
  
     Die <xref:System.Windows.Forms.ToolStrip> befindet sich auf einer Seite eines Containers in einer bestimmten Position fixiert, und seine Größe erstreckt sich über den gesamten Rand, an dem er angedockt ist. In der Regel die <xref:System.Windows.Forms.ToolStrip> nicht Teil der Aktivierreihenfolge.  
  
-   Absolut positioniert.  
  
     Die <xref:System.Windows.Forms.ToolStrip> wird wie bei anderen Steuerelementen, da er von platziert wird die <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft, eine feste Größe aufweist, und in der Regel in der Aktivierreihenfolge beteiligt ist.  
  
#### <a name="keyboard-interaction"></a>Tastaturinteraktion  
  
##### <a name="access-keys"></a>Zugriffstasten  
 In Kombination mit oder dahinter die ALT-Taste sind Zugriffstasten eine Möglichkeit zum Aktivieren eines Steuerelements über die Tastatur. <xref:System.Windows.Forms.ToolStrip> unterstützt sowohl explizite und implizite Zugriffsschlüssel an. Explizite Definition verwendet ein kaufmännisches und-Zeichen (&) vor dem Buchstaben. Implizite Definition verwendet einen Algorithmus, der versucht, finden ein übereinstimmendes Element entsprechend der Reihenfolge der Zeichen in einer bestimmten `Text` Eigenschaft.  
  
##### <a name="shortcut-keys"></a>Tastenkombinationen  
 Die Tastenkombinationen, die verwendet werden, indem eine <xref:System.Windows.Forms.MenuStrip> verwenden eine Kombination der <xref:System.Windows.Forms.Keys> Enumeration (also nicht einen bestimmten Auftrag beziehen) definieren Sie die Tastenkombination. Sie können auch die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> Eigenschaft, um eine Tastenkombination mit nur-Text anzuzeigen, z. B. das Anzeigen von "Del" anstelle von "Delete".  
  
##### <a name="navigation"></a>Navigation  
 Aktiviert die ALT-Taste die <xref:System.Windows.Forms.MenuStrip> verweist <xref:System.Windows.Forms.Form.MainMenuStrip%2A>. Von dort navigiert STRG + TAB zwischen <xref:System.Windows.Forms.ToolStrip> steuert in `ToolStripPanel`s. Die TAB-Taste und der Pfeiltasten auf der Zehnertastatur Navigieren zwischen Elementen in einem <xref:System.Windows.Forms.ToolStrip>. Ein spezieller Algorithmus behandelt die Navigation in der Region Überlauf. LEERTASTE wählt eine <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, oder <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
##### <a name="focus-and-validation"></a>Fokus und Validierung  
 Bei der Aktivierung über die ALT-Taste die <xref:System.Windows.Forms.MenuStrip> oder <xref:System.Windows.Forms.ToolStrip> in der Regel keine übernehmen und entfernen Sie den Fokus aus dem Steuerelement, der gerade den Fokus besitzt. Wenn ein Steuerelement gehostet ist die <xref:System.Windows.Forms.MenuStrip> oder eine Dropdownliste der <xref:System.Windows.Forms.MenuStrip>, das Steuerelement den Fokus erhält, wenn der Benutzer die TAB-Taste drückt. Im Allgemeinen die <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter>, und <xref:System.Windows.Forms.Control.Leave> Ereignisse <xref:System.Windows.Forms.MenuStrip> möglicherweise nicht ausgelöst werden, wenn sie über die Tastatur aktiviert werden. In solchen Fällen verwenden die <xref:System.Windows.Forms.MenuStrip.MenuActivate> und <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> Ereignisse stattdessen.  
  
 Standardmäßig <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> ist `false`. Rufen Sie <xref:System.Windows.Forms.ContainerControl.Validate%2A> explizit auf dem Formular validiert.  
  
#### <a name="layout"></a>Layout  
 Sie steuern, <xref:System.Windows.Forms.ToolStrip> Layout durch Auswahl eines der Elemente der <xref:System.Windows.Forms.ToolStripLayoutStyle> mit der <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> Eigenschaft.  
  
##### <a name="stack-layouts"></a>Stack-Layouts  
 Stapeln wird das Anordnen der Elemente nebeneinander an beiden Enden des der <xref:System.Windows.Forms.ToolStrip>. Die folgende Liste beschreibt die Stack-Layouts an.  
  
-   Standardmäßig ist <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow> festgelegt. Diese Einstellung bewirkt, dass die <xref:System.Windows.Forms.ToolStrip> zum Ändern des Layouts automatisch in Abhängigkeit von der <xref:System.Windows.Forms.ToolStrip.Orientation%2A> Eigenschaft Zieh- und behandeln.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow> Rendert die <xref:System.Windows.Forms.ToolStrip> Elemente nebeneinander vertikal.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow> Rendert die <xref:System.Windows.Forms.ToolStrip> horizontal nebeneinander Elemente.  
  
##### <a name="other-features-of-stack-layouts"></a>Andere Funktionen der Stapellayouts  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Bestimmt das Ende der <xref:System.Windows.Forms.ToolStrip> an dem das Element ausgerichtet ist.  
  
 Wenn Elemente nicht in passen die <xref:System.Windows.Forms.ToolStrip>, eine Überlaufschaltfläche automatisch angezeigt wird. Die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> -eigenschafteneinstellung bestimmt, ob ein Element in den Überlaufbereich stets, bei Bedarf oder nie angezeigt wird.  
  
 In der <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> -Ereignis können Sie überprüfen die <xref:System.Windows.Forms.ToolStripItem.Placement%2A> -Eigenschaft können Sie bestimmen, ob ein Element auf der Hauptseite platziert wurde <xref:System.Windows.Forms.ToolStrip>, der Überlauf <xref:System.Windows.Forms.ToolStrip>, oder wenn derzeit nicht angezeigt werden. Die typische Gründe, warum ein Element wird nicht angezeigt, werden, dass das Element nicht auf der Hauptseite gepasst hat <xref:System.Windows.Forms.ToolStrip> und seine <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> -Eigenschaft wurde festgelegt, um <xref:System.Windows.Forms.ToolStripItemOverflow.Never>.  
  
 Stellen ein <xref:System.Windows.Forms.ToolStrip> verschiebbar verlegen Sie es ein <xref:System.Windows.Forms.ToolStripPanel> verwendet wird und seine <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> auf <xref:System.Windows.Forms.ToolStripGripStyle.Visible>.  
  
##### <a name="other-layout-options"></a>Andere Layoutoptionen  
 Die anderen Layoutoptionen sind <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> und <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>.  
  
##### <a name="flow-layout"></a>Flusslayout  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layout ist die Standardeinstellung für <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, und <xref:System.Windows.Forms.ToolStripOverflow>. Ähnliches gilt für die <xref:System.Windows.Forms.FlowLayoutPanel>. Die Funktionen von <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layout lauten wie folgt:  
  
-   Alle Funktionen der <xref:System.Windows.Forms.FlowLayoutPanel> verfügbar gemacht werden die <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> Eigenschaft. Müssen Sie eine Umwandlung der <xref:System.Windows.Forms.LayoutSettings> Klasse, um eine <xref:System.Windows.Forms.FlowLayoutSettings> Klasse.  
  
-   Sie können die <xref:System.Windows.Forms.ToolStripItem.Dock%2A> und <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> Eigenschaften im Code die Elemente innerhalb der Zeile ausrichten.  
  
-   Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>-Eigenschaft wird ignoriert.  
  
-   In der <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> -Ereignis können Sie überprüfen die <xref:System.Windows.Forms.ToolStripItem.Placement%2A> Eigenschaft, um zu bestimmen, ob ein Element auf der Hauptseite aufgegeben <xref:System.Windows.Forms.ToolStrip> oder nicht zu groß sind.  
  
-   Der Ziehpunkt nicht gerendert, und daher ein <xref:System.Windows.Forms.ToolStrip> in <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layoutstil in eine <xref:System.Windows.Forms.ToolStripPanel> kann nicht verschoben werden.  
  
-   Die <xref:System.Windows.Forms.ToolStrip> dokumentüberlauf-Schaltfläche wird nicht gerendert, und <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> wird ignoriert.  
  
##### <a name="table-layout"></a>Tabellenlayout  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> Layout ist die Standardeinstellung für <xref:System.Windows.Forms.StatusStrip>. Sie ähnelt damit <xref:System.Windows.Forms.TableLayoutPanel>. Die Funktionen von <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> Layout lauten wie folgt:  
  
-   Alle Funktionen der <xref:System.Windows.Forms.TableLayoutPanel> verfügbar gemacht werden die <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> Eigenschaft. Müssen Sie eine Umwandlung der <xref:System.Windows.Forms.LayoutSettings> Klasse, um eine <xref:System.Windows.Forms.TableLayoutSettings> Klasse.  
  
-   Sie können die <xref:System.Windows.Forms.ToolStripItem.Dock%2A> und <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> Eigenschaften im Code die Elemente in der Tabellenzelle ausrichten.  
  
-   Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>-Eigenschaft wird ignoriert.  
  
-   In der <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> -Ereignis können Sie überprüfen die <xref:System.Windows.Forms.ToolStripItem.Placement%2A> Eigenschaft, um zu bestimmen, ob ein Element auf der Hauptseite aufgegeben <xref:System.Windows.Forms.ToolStrip> oder nicht zu groß sind.  
  
-   Der Ziehpunkt nicht gerendert, und daher ein <xref:System.Windows.Forms.ToolStrip> in <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> Layoutstil in eine <xref:System.Windows.Forms.ToolStripPanel> kann nicht verschoben werden.  
  
-   Die <xref:System.Windows.Forms.ToolStrip> dokumentüberlauf-Schaltfläche wird nicht gerendert, und <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> wird ignoriert.  
  
## <a name="toolstripitem"></a>ToolStripItem  
 Die folgenden Themen beschreiben <xref:System.Windows.Forms.ToolStripItem> und die Steuerelemente, die sich davon herleiten.  
  
 <xref:System.Windows.Forms.ToolStripItem> ist die abstrakte Basisklasse für alle Elemente, die in einem <xref:System.Windows.Forms.ToolStrip>. Das folgende Objekt Modell zeigt das <xref:System.Windows.Forms.ToolStripItem> Vererbungshierarchie.  
  
 ![ToolStripItem-Objektmodell](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.gif "ToolStripItemObjectModel")  
ToolStripItem-Objektmodell  
  
 <xref:System.Windows.Forms.ToolStripItem> Klassen, die entweder direkt von erben <xref:System.Windows.Forms.ToolStripItem>, oder sie erben indirekt von <xref:System.Windows.Forms.ToolStripItem> über <xref:System.Windows.Forms.ToolStripControlHost> oder <xref:System.Windows.Forms.ToolStripDropDownItem>.  
  
 <xref:System.Windows.Forms.ToolStripItem> Steuerelemente müssen enthalten sein, einem <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, oder <xref:System.Windows.Forms.ContextMenuStrip> und kann nicht direkt zu einem Formular hinzugefügt werden. Die verschiedenen Containerklassen enthält eine entsprechende Teilmenge von <xref:System.Windows.Forms.ToolStripItem> Steuerelemente.  
  
 Die folgende Tabelle enthält die Stock <xref:System.Windows.Forms.ToolStripItem> Steuerelemente und die Container, in dem sie am besten aussehen. Obwohl alle <xref:System.Windows.Forms.ToolStrip> Element aufgenommen werden kann, in einem <xref:System.Windows.Forms.ToolStrip>-abgeleiteten Container, diese Elemente wurden entwickelt, um die beste, in den folgenden Containern suchen:  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown> in der Toolbox-Designers wird nicht angezeigt werden.  
  
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
 <xref:System.Windows.Forms.ToolStripButton> ist die Schaltflächenelement für <xref:System.Windows.Forms.ToolStrip>. Sie können mit verschiedenen Rahmenarten anzeigen und können Sie sie zum darstellen und Betriebszustände aktivieren. Sie können auch definieren, um den Fokus standardmäßig haben.  
  
### <a name="toolstriplabel"></a>ToolStripLabel  
 Die <xref:System.Windows.Forms.ToolStripLabel> Bezeichnung ist der Funktionsumfang in <xref:System.Windows.Forms.ToolStrip> Steuerelemente. Die <xref:System.Windows.Forms.ToolStripLabel> entspricht einer <xref:System.Windows.Forms.ToolStripButton> ist standardmäßig nicht den Fokus abgerufen und nicht als aktiviert oder hervorgehoben gerendert.  
  
 <xref:System.Windows.Forms.ToolStripLabel> unterstützt als gehostetes Element Zugriffsschlüssel ein.  
  
 Verwenden der <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, und <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> Eigenschaften auf eine <xref:System.Windows.Forms.ToolStripLabel> zur Unterstützung von Link-Steuerelement in einem <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel> ist eine Version von <xref:System.Windows.Forms.ToolStripLabel> entwickelt, die speziell zur Verwendung in <xref:System.Windows.Forms.StatusStrip>. Die speziellen Funktionen umfassen <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>, und <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
### <a name="toolstripseparator"></a>ToolStripSeparator  
 Die <xref:System.Windows.Forms.ToolStripSeparator> Fügt eine vertikale oder horizontale Linie zu einer Symbolleiste oder im Menü, abhängig von der Ausrichtung. Gruppieren von "oder" Unterscheidung zwischen Elementen, z. B. die in einem Menü darüber.  
  
 Sie können Hinzufügen einer <xref:System.Windows.Forms.ToolStripSeparator> zur Entwurfszeit durch Auswahl aus einer Dropdownliste. Sie können jedoch auch automatisch erstellen eine <xref:System.Windows.Forms.ToolStripSeparator> durch Eingabe von einem Bindestrich (-) im Knoten "Vorlage des Designers" oder in der <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Methode.  
  
### <a name="toolstripcontrolhost"></a>ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost> ist die abstrakte Basisklasse für <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>, und <xref:System.Windows.Forms.ToolStripProgressBar>. <xref:System.Windows.Forms.ToolStripControlHost> andere Steuerelemente, einschließlich der benutzerdefinierten Steuerelemente auf zwei Arten können gehostet werden:  
  
-   Erstellen einer <xref:System.Windows.Forms.ToolStripControlHost> mit einer Klasse, die abgeleitet <xref:System.Windows.Forms.Control>. Um das gehostete Steuerelement und die Eigenschaften vollständig zugreifen zu können, müssen Sie eine Umwandlung der <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> Eigenschaft, um die tatsächliche Klasse darstellt.  
  
-   Erweitern <xref:System.Windows.Forms.ToolStripControlHost>, und rufen Sie in der geerbten Klasse trivialen Konstruktor den Basisklassenkonstruktor, übergeben eine Klasse, die abgeleitet <xref:System.Windows.Forms.Control>. Mit dieser Option können Sie allgemeine Steuerelementmethoden und Eigenschaften für den leichteren Zugriff im umschließen einer <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripcombobox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox> ist die <xref:System.Windows.Forms.ComboBox> optimiert für das hosting in einer <xref:System.Windows.Forms.ToolStrip>. Eine Teilmenge der Eigenschaften und Ereignisse des gehosteten Steuerelements werden verfügbar gemacht, an die <xref:System.Windows.Forms.ToolStripComboBox> Ebene, aber die zugrunde liegende <xref:System.Windows.Forms.ComboBox> Steuerelement vollständig Zugriff erfolgt über die <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> Eigenschaft.  
  
### <a name="toolstriptextbox"></a>ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox> ist die <xref:System.Windows.Forms.TextBox> optimiert für das hosting in einer <xref:System.Windows.Forms.ToolStrip>. Eine Teilmenge der Eigenschaften und Ereignisse des gehosteten Steuerelements werden verfügbar gemacht, an die <xref:System.Windows.Forms.ToolStripTextBox> Ebene, aber die zugrunde liegende <xref:System.Windows.Forms.TextBox> Steuerelement vollständig Zugriff erfolgt über die <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> Eigenschaft.  
  
### <a name="toolstripprogressbar"></a>ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar> ist die <xref:System.Windows.Forms.ProgressBar> optimiert für das hosting in einer <xref:System.Windows.Forms.ToolStrip>. Eine Teilmenge der Eigenschaften und Ereignisse des gehosteten Steuerelements werden verfügbar gemacht, an die <xref:System.Windows.Forms.ToolStripProgressBar> Ebene, aber die zugrunde liegende <xref:System.Windows.Forms.ProgressBar> Steuerelement vollständig Zugriff erfolgt über die <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> Eigenschaft.  
  
### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem> ist die abstrakte Basisklasse für <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>, und <xref:System.Windows.Forms.ToolStripSplitButton>, können Elemente direkt hosten oder zusätzliche Elemente in einem Dropdown-Container gehostet. Sie dazu die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> Eigenschaft, um eine <xref:System.Windows.Forms.ToolStripDropDown> verwendet wird und die <xref:System.Windows.Forms.ToolStrip.Items%2A> Eigenschaft von der <xref:System.Windows.Forms.ToolStripDropDown>. Zugriff auf diese Dropdown-Elemente, die direkt über die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> Eigenschaft.  
  
### <a name="toolstripmenuitem"></a>ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem> ist eine <xref:System.Windows.Forms.ToolStripDropDownItem> das funktioniert mit <xref:System.Windows.Forms.ToolStripDropDownMenu> und <xref:System.Windows.Forms.ContextMenuStrip> , die spezielle Hervorhebung, Layout und Spalte Anordnung für Menüs zu behandeln.  
  
### <a name="toolstripdropdownbutton"></a>Der ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton> sieht wie <xref:System.Windows.Forms.ToolStripButton>, aber es zeigt einen Dropdown-Bereich, wenn der Benutzer darauf klickt. Ein- oder Ausblenden der Dropdown-Pfeil durch Festlegen der <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> Eigenschaft. <xref:System.Windows.Forms.ToolStripDropDownButton> Hosts eine <xref:System.Windows.Forms.ToolStripOverflowButton> , die Elemente angezeigt, die "Überlauf", die <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripsplitbutton"></a>ToolStripSplitButton erhalten soll  
 <xref:System.Windows.Forms.ToolStripSplitButton> kombiniert die Dropdown-Schaltfläche-Funktionalität und Schaltfläche.  
  
 Verwenden der <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> Eigenschaft zum Synchronisieren der <xref:System.Windows.Forms.Control.Click> Ereignis des ausgewählten Dropdown-Elements mit dem Element, auf die Schaltfläche angezeigt.  
  
### <a name="toolstripitem-generic-features"></a>ToolStripItem generische Funktionen  
 <xref:System.Windows.Forms.ToolStripItem> bietet die folgenden allgemeinen Funktionen und Optionen für erbende Steuerelemente:  
  
-   Core-Ereignisse  
  
-   Bildbehandlung  
  
-   Ausrichtung  
  
-   Text- und Image-Beziehung  
  
-   Anzeigeformat  
  
#### <a name="core-events"></a>Core-Ereignisse  
 <xref:System.Windows.Forms.ToolStripItem> Steuerelemente erhalten ihre eigenen klicken, Maus und Paint-Ereignissen und einige auch vorverarbeitung Tastatur ausführen können.  
  
#### <a name="image-handling"></a>Bildbehandlung  
 Die <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>, und <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> Eigenschaften beziehen sich auf verschiedene Aspekte der Bildbehandlung. Verwenden von Bildern in <xref:System.Windows.Forms.ToolStrip> Steuerelemente durch Festlegen dieser Eigenschaften direkt oder durch Festlegen der Ausführung nur zur Laufzeit <xref:System.Windows.Forms.ToolStrip.ImageList%2A> Eigenschaft.  
  
 Bildskalierung richtet sich nach der Interaktion von Eigenschaften in beiden <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStripItem>wie folgt:  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> die Dezimalstellen des dem endgültigen Image bestimmt durch die Kombination des Bilds <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> Einstellung und des Containers <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> Einstellung.  
  
    -   Wenn <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> ist `true` (Standard) und <xref:System.Windows.Forms.ToolStripItemImageScaling> ist <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, keine Bildskalierung, und die <xref:System.Windows.Forms.ToolStrip> Größe ist, die das größte Element oder eine vorgegebene Mindestgröße.  
  
    -   Wenn <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> ist `false` und <xref:System.Windows.Forms.ToolStripItemImageScaling> ist <xref:System.Windows.Forms.ToolStripItemImageScaling.None>, weder das Bild noch <xref:System.Windows.Forms.ToolStrip> Skalierung auftritt.  
  
#### <a name="alignment"></a>Ausrichtung  
 Der Wert des der <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> -Eigenschaft bestimmt das Ende der <xref:System.Windows.Forms.ToolStrip> an der ein Element erscheint. Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Eigenschaft funktioniert nur, wenn der Layoutstil von der <xref:System.Windows.Forms.ToolStrip> auf einen der Stack Overflow Werte festgelegt.  
  
 Elemente werden platziert, über die <xref:System.Windows.Forms.ToolStrip> in der Reihenfolge, in der die Elemente angezeigt, in der Items-Auflistung werden. Um programmgesteuert zu ändern, in dem ein Element angeordnet wird, verwenden die <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> Methode, um das Element in der Auflistung verschoben werden. Diese Methode verschiebt das Element jedoch nicht duplizieren.  
  
#### <a name="text-and-image-relationship"></a>Text- und Image-Beziehung  
 Die <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> -Eigenschaft definiert die relative Platzierung des Bilds in Bezug auf den Text auf einer <xref:System.Windows.Forms.ToolStripItem>. Elemente, die ein Image, Text beides oder werden als besondere Fälle behandelt, damit die <xref:System.Windows.Forms.ToolStripItem> einen leeren Bereich für das fehlende Element oder die Elemente nicht angezeigt.  
  
#### <a name="display-style"></a>Anzeigeformat  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> bietet die Möglichkeit, legen Sie die Werte von Text- und Image-Eigenschaften eines Elements, bei der nur die gewünschten Elemente anzuzeigen. Dies wird normalerweise verwendet, um nur das Anzeigeformat zu ändern, wenn dasselbe Element in einem anderen Kontext angezeigt.  
  
## <a name="accessory-classes"></a>Zusätzliche Klassen  
 Klassen, die verschiedene andere Funktionen zählen:  
  
-   <xref:System.Windows.Forms.ToolStripManager> unterstützt <xref:System.Windows.Forms.ToolStrip>-bezogene Aufgaben für die gesamte Anwendungen, z. B. das Zusammenführen, Einstellungen und Renderer Optionen.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> können Sie einen bestimmten nachrichtenstil oder ein Design für Anwenden einer <xref:System.Windows.Forms.ToolStrip> einfach.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> erstellt Stifte und Pinsel auf Grundlage einer ersetzbaren Farbtabelle (<xref:System.Windows.Forms.ProfessionalColorTable>).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> Wendet Systemfarben und einem flachen visuellen Stil in <xref:System.Windows.Forms.ToolStrip> Anwendungen.  
  
-   <xref:System.Windows.Forms.ToolStripContainer> ähnelt dem <xref:System.Windows.Forms.SplitContainer>. Es verwendet vier angedockten Seitenbereichen (Instanzen von <xref:System.Windows.Forms.ToolStripPanel>) und einen zentralen Bereich (eine Instanz von <xref:System.Windows.Forms.ToolStripContentPanel>) zum Erstellen einer typischen Anordnung. Die Seite Elemente können nicht entfernt werden, jedoch können Sie sie ausblenden. Sie können weder entfernen noch mittleren Bereich auszublenden. Sie können eine oder mehrere anordnen <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, oder <xref:System.Windows.Forms.StatusStrip> Steuerelemente in den Seitenbereichen, und Sie können den mittleren Bereich für andere Steuerelemente verwenden. Die <xref:System.Windows.Forms.ToolStripContentPanel> bietet auch eine Möglichkeit, renderunterstützung in den Text des Formulars für ein konsistentes Erscheinungsbild zu erhalten. <xref:System.Windows.Forms.ToolStripContainer> unterstützt keine mehrfachen Dokumentschnittstelle (MDI).  
  
-   <xref:System.Windows.Forms.ToolStripPanel> Dient zum Verschieben und Anordnen von <xref:System.Windows.Forms.ToolStrip> Steuerelemente. Sie können nur einen Bereich auf, wenn Sie möchten, und <xref:System.Windows.Forms.ToolStripPanel> funktioniert gut in MDI-Szenarien.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Zusammenfassung der ToolStrip-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)  
 [ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [StatusStrip-Steuerelement](../../../../docs/framework/winforms/controls/statusstrip-control.md)  
 [ContextMenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)  
 [BindingNavigator-Steuerelement](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
