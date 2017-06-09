---
title: "Architektur des ToolStrip-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolStrip-Steuerelement [Windows Forms], Architektur"
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# Architektur des ToolStrip-Steuerelements
Die <xref:System.Windows.Forms.ToolStrip>\-Klasse und die <xref:System.Windows.Forms.ToolStripItem>\-Klasse stellen ein flexibles, erweiterbares System zum Anzeigen von Symbolleisten\-, Status\- und Menüelementen bereit.  Diese Klassen befinden sich im <xref:System.Windows.Forms>\-Namespace und enthalten in ihrem Namen für gewöhnlich das Präfix "ToolStrip" \(z. B. <xref:System.Windows.Forms.ToolStripOverflow>\) oder das Suffix "Strip" \(z. B. <xref:System.Windows.Forms.MenuStrip>\).  
  
## ToolStrip  
 In den folgenden Themen werden <xref:System.Windows.Forms.ToolStrip> und die davon abgeleiteten Steuerelemente beschrieben.  
  
 <xref:System.Windows.Forms.ToolStrip> ist die abstrakte Basisklasse für <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ContextMenuStrip>.  Das folgende Objektmodell veranschaulicht die Vererbungshierarchie von <xref:System.Windows.Forms.ToolStrip>.  
  
 ![ToolStrip&#45;Objektmodell](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.png "ToolStripObjectModel")  
ToolStrip\-Objektmodell  
  
 Sie können auf alle Elemente in einem <xref:System.Windows.Forms.ToolStrip> über die <xref:System.Windows.Forms.ToolStrip.Items%2A>\-Auflistung zugreifen.  Sie können auf alle Elemente in einem <xref:System.Windows.Forms.ToolStripDropDownItem> über die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>\-Auflistung zugreifen.  In einer von <xref:System.Windows.Forms.ToolStrip> abgeleiteten Klasse besteht auch die Möglichkeit, über die <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A>\-Eigenschaft nur auf die derzeit angezeigten Elemente zuzugreifen.  Diese sind die Elemente, die sich derzeit nicht in einem Überlaufmenü befinden.  
  
 Die folgenden Elemente wurden speziell für die problemlose Integration in <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in allen Ausrichtungen entwickelt.  Sie stehen zur Entwurfszeit standardmäßig für das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement zur Verfügung:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> ist der Container der obersten Ebene, der das <xref:System.Windows.Forms.MainMenu> ersetzt.  Hiermit werden auch die Behandlung von Schlüsseln und MDI\-Features \(Multiple Document Interface\) bereitgestellt.  <xref:System.Windows.Forms.ToolStripDropDownItem> und <xref:System.Windows.Forms.ToolStripMenuItem> können neben <xref:System.Windows.Forms.MenuStrip> verwendet werden, obwohl sie von <xref:System.Windows.Forms.ToolStripItem> abgeleitet sind.  
  
 Die folgenden Elemente wurden speziell für die problemlose Integration in <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in allen Ausrichtungen entwickelt.  Sie stehen zur Entwurfszeit standardmäßig für das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement zur Verfügung:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### StatusStrip  
 <xref:System.Windows.Forms.StatusStrip> ersetzt das <xref:System.Windows.Forms.StatusBar>\-Steuerelement.  Zu den besonderen Features von <xref:System.Windows.Forms.StatusStrip> zählen benutzerdefinierte Tabellenlayouts, Unterstützung für Größenanpassung und Verschiebungspunkte für Formulare sowie die `Spring`\-Eigenschaft, mit der verfügbare Bereiche durch ein <xref:System.Windows.Forms.ToolStripStatusLabel> automatisch gefüllt werden können.  
  
 Die folgenden Elemente wurden speziell für die problemlose Integration in <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in allen Ausrichtungen entwickelt.  Sie stehen zur Entwurfszeit standardmäßig für das <xref:System.Windows.Forms.StatusStrip>\-Steuerelement zur Verfügung:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip> ersetzt <xref:System.Windows.Forms.ContextMenu>.  Jedem Steuerelement kann eine <xref:System.Windows.Forms.ContextMenuStrip> zugeordnet werden. Durch Klicken auf die rechte Maustaste wird automatisch das Kontextmenü angezeigt.  Sie können ein <xref:System.Windows.Forms.ContextMenuStrip>\-Element programmgesteuert mit der <xref:System.Windows.Forms.ToolStripDropDown.Show%2A>\-Methode anzeigen.  <xref:System.Windows.Forms.ContextMenuStrip> unterstützt abbrechbare <xref:System.Windows.Forms.ToolStripDropDown.Opening>\- und <xref:System.Windows.Forms.ToolStripDropDown.Closing>\-Ereignisse, mit denen die Szenarien zur dynamischen Population und zum mehrfachen Klicken behandelt werden können.  <xref:System.Windows.Forms.ContextMenuStrip> unterstützt Bilder, den Aktivierungszustand der Menüeinträge, Text, Zugriffstasten, Tastenkombinationen und Untermenüs.  
  
 Die folgenden Elemente wurden speziell für die problemlose Integration in <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in allen Ausrichtungen entwickelt.  Sie stehen zur Entwurfszeit standardmäßig für das <xref:System.Windows.Forms.ContextMenuStrip>\-Steuerelement zur Verfügung:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### ToolStrip – Allgemeine Features  
 In den folgenden Themen werden Features und Verhalten beschrieben, die für <xref:System.Windows.Forms.ToolStrip> und daraus abgeleitete Steuerelemente allgemein gelten.  
  
#### Bild  
 In <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen können benutzerdefinierte Bilder auf verschiedene Arten erstellt werden.  Wie andere Windows Forms\-Steuerelemente haben <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStripItem> überschreibbare `OnPaint`\-Methoden und `Paint`\-Ereignisse.  Wie beim herkömmlichen Zeichnen ist das Koordinatensystem relativ zum Clientbereich des Steuerelements. Das bedeutet, dass die obere linke Ecke des Steuerelements die Koordinaten 0, 0 hat.  Das `Paint`\-Ereignis und die `OnPaint`\-Methode für ein <xref:System.Windows.Forms.ToolStripItem> lassen sich wie andere Steuerelement\-Zeichenereignisse verwenden.  
  
 Die <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente bieten mithilfe der <xref:System.Windows.Forms.ToolStripRenderer>\-Klasse zudem besseren Zugang zum Rendering der Elemente und der Container. Diese Klasse verfügt über überschreibbare Methoden zum Ausfüllen von Hintergrund, Elementhintergrund, Elementbild, Elementpfeil, Elementtext und Rahmen von <xref:System.Windows.Forms.ToolStrip>.  Die Ereignisargumente für diese Methoden machen mehrere Eigenschaften verfügbar, z. B. Rechtecke, Farben, und Textformate, die nach Bedarf angepasst werden können.  
  
 Wenn nur einige Aspekte beim Zeichnen eines Elements angepasst werden sollen, überschreiben Sie i. d. R. den <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Wenn Sie ein neues Element schreiben und sämtliche Zeichnungsaspekte steuern möchten, überschreiben Sie die `OnPaint`\-Methode.  Innerhalb von `OnPaint` können Sie Methoden aus dem <xref:System.Windows.Forms.ToolStripRenderer> verwenden.  
  
 In der Standardeinstellung ist <xref:System.Windows.Forms.ToolStrip> doppelt gepuffert und nutzt somit die Einstellung <xref:System.Windows.Forms.ControlStyles>.  
  
#### Überordnen  
 Das Konzept des Containerbesitzes und des Überordnens ist in <xref:System.Windows.Forms.ToolStrip> komplexer als in anderen Windows Forms\-Containersteuerelementen.  Dies ist notwendig zur Unterstützung dynamischer Szenarien wie Überlauf, Freigabe von Dropdownelementen über mehrere <xref:System.Windows.Forms.ToolStrip>\-Elemente und der Generierung eines <xref:System.Windows.Forms.ContextMenuStrip> aus einem Steuerelement.  
  
 In der folgenden Liste werden Member in Verbindung mit Überordnung beschrieben und deren Verwendung erklärt.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> greift auf das Element zu, das die Quelle des Dropdownelements ist.  Dies ist vergleichbar mit <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>. Statt eines Steuerelements wird jedoch ein <xref:System.Windows.Forms.ToolStripItem> zurückgegeben.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> legt fest, welches Steuerelement die Quelle des <xref:System.Windows.Forms.ContextMenuStrip> ist, wenn mehrere Steuerelemente den gleichen <xref:System.Windows.Forms.ContextMenuStrip> verwenden.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> ist ein schreibgeschützter Accessor für die <xref:System.Windows.Forms.ToolStripItem.Parent%2A>\-Eigenschaft.  Ein übergeordnetes Element unterscheidet sich von einem Besitzer darin, dass es den zurückgegebenen aktuellen <xref:System.Windows.Forms.ToolStrip> darstellt, in dem das Element angezeigt wird, das sich möglicherweise im Überlaufbereich befindet.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A> gibt den <xref:System.Windows.Forms.ToolStrip> zurück, dessen Elementauflistung das aktuelle <xref:System.Windows.Forms.ToolStripItem> enthält.  Dies ist die beste Vorgehensweise, um auf <xref:System.Windows.Forms.ToolStrip.ImageList%2A> oder andere Eigenschaften im <xref:System.Windows.Forms.ToolStrip> der obersten Ebene zu verweisen, ohne speziellen Code zur Behandlung des Überlaufs schreiben zu müssen.  
  
#### Verhalten geerbter Steuerelemente  
 Die folgenden Steuerelemente werden immer dann gesperrt, wenn sie in Vererbungen verwendet werden:  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel> beinhaltet die Bereiche in einem <xref:System.Windows.Forms.ToolStripContainer> und einzelne <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelemente.  
  
 Erstellen Sie beispielsweise eine neue Windows Forms\-Anwendung, indem Sie eines oder mehrere Steuerelemente der vorhergehenden Liste verwenden.  Legen Sie den Zugriffsmodifizierer von einem oder mehreren Steuerelementen auf `public` oder `protected` fest, und erstellen Sie anschließend das Projekt.  Fügen Sie ein Formular hinzu, das vom ersten Formular erbt, und wählen Sie dann ein geerbtes Steuerelement aus.  Das Steuerelement wird gesperrt angezeigt und verhält sich wie bei einem `private`\-Zugriffsmodifizierer.  
  
#### ToolStripContainer – Unterstützung von Vererbung  
 Das <xref:System.Windows.Forms.ToolStripContainer>\-Steuerelement unterstützt beschränkte geerbte Szenarien, ähnlich dem folgenden Beispiel:  
  
1.  Erstellen Sie eine neue Windows Forms\-Anwendung.  
  
2.  Fügen Sie einen <xref:System.Windows.Forms.ToolStripContainer> zum Formular hinzu.  
  
3.  Legen Sie den Zugriffsmodifizierer vom <xref:System.Windows.Forms.ToolStripContainer> auf `public` oder `protected` fest.  
  
4.  Fügen Sie eine beliebige Kombination der Steuerelemente <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> zu den <xref:System.Windows.Forms.ToolStripPanel>\-Bereichen vom <xref:System.Windows.Forms.ToolStripContainer> hinzu.  
  
5.  Erstellen Sie das Projekt.  
  
6.  Fügen Sie ein Formular hinzu, das vom ersten Formular erbt.  
  
7.  Wählen Sie den geerbten <xref:System.Windows.Forms.ToolStripContainer> auf dem Formular aus.  
  
#### Geerbtes Verhalten von untergeordneten Steuerelementen  
 Nachdem Sie die vorherigen Schritte ausgeführt haben, tritt das folgende geerbte Verhalten auf:  
  
-   Im Designer wird das Steuerelement mit dem Symbol Geerbt angezeigt.  
  
-   Die <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelemente sind gesperrt. Sie können nicht ausgewählt und ihr Inhalt kann nicht neu angeordnet werden.  
  
-   Sie können zum <xref:System.Windows.Forms.ToolStripContentPanel> Steuerelemente hinzufügen, die Steuerelemente verschieben und diese als untergeordnete Steuerelemente vom <xref:System.Windows.Forms.ToolStripContentPanel> definieren.  
  
-   Ihre Änderungen bleiben nach dem Erstellen des Formulars erhalten.  
  
    > [!NOTE]
    >  Entfernen Sie die Zugriffsmodifizierer aus allen <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelementen, die zu einem <xref:System.Windows.Forms.ToolStripContainer> gehören.  Der Zugriffsmodifizierer vom <xref:System.Windows.Forms.ToolStripContainer> steuert das gesamte Steuerelement.  
  
#### Teilweise vertrauenswürdig  
 Die Einschränkungen von `ToolStrip` unter teilweiser Vertrauensstellung dienen zum Schutz vor versehentlichen Eingaben persönlicher Daten, die von nicht autorisierten Personen oder Diensten möglicherweise verwendet werden können.  Die folgenden Maßnahmen dienen dem Schutz:  
  
-   `ToolStripDropDown`\-Steuerelemente erfordern <xref:System.Security.Permissions.UIPermissionWindow>, um Elemente in einem <xref:System.Windows.Forms.ToolStripControlHost> anzuzeigen.  Dies gilt sowohl für systeminterne Steuerelemente, wie <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox> und <xref:System.Windows.Forms.ToolStripProgressBar>, als auch für benutzerdefinierte Steuerelemente.  Wenn diese Anforderung nicht erfüllt wird, werden die entsprechenden Elemente nicht angezeigt.  Es wird keine Ausnahme ausgelöst.  
  
-   Das Festlegen der <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A>\-Eigenschaft auf `false` ist nicht zulässig, und der abbrechbare <xref:System.Windows.Forms.ToolStripDropDown.Closing>\-Ereignisparameter wird ignoriert.  Dadurch wird das Dropdownelement nach der ersten Tastatureingabe geschlossen.  Wenn diese Anforderung nicht erfüllt wird, werden solche Elemente nicht angezeigt.  Es wird keine Ausnahme ausgelöst.  
  
-   Viele Ereignisse zur Behandlung von Tastatureingaben werden nicht ausgelöst, wenn sie in Verbindung mit teilweiser Vertrauensstellung auftreten. Eine Ausnahme stellt <xref:System.Security.Permissions.UIPermissionWindow> dar.  
  
-   Zugriffstasten werden ignoriert, wenn <xref:System.Security.Permissions.UIPermissionWindow> nicht gewährt wird.  
  
#### Verwendung  
 Die folgenden Verwendungsmuster wirken sich auf das <xref:System.Windows.Forms.ToolStrip>\-Layout, die Tastaturinteraktion und das Endbenutzerverhalten aus:  
  
-   Verknüpfung in einem <xref:System.Windows.Forms.ToolStripPanel>  
  
     Der <xref:System.Windows.Forms.ToolStrip> kann innerhalb vom <xref:System.Windows.Forms.ToolStripPanel> und über <xref:System.Windows.Forms.ToolStripPanel> neu ausgerichtet werden.  Die `Dock`\-Eigenschaft wird ignoriert, und wenn die <xref:System.Windows.Forms.ToolStrip.Stretch%2A>\-Eigenschaft den Wert `false` aufweist, nimmt die Größe vom <xref:System.Windows.Forms.ToolStrip> beim Hinzufügen von Elementen zum <xref:System.Windows.Forms.ToolStripPanel> zu.  In der Regel ist der <xref:System.Windows.Forms.ToolStrip> nicht Teil der Aktivierreihenfolge.  
  
-   Angedockt  
  
     Der <xref:System.Windows.Forms.ToolStrip> befindet sich auf einer Seite eines Containers in einer festen Position, und seine Größe erstreckt sich über den gesamten Rand, an dem er angedockt ist.  In der Regel ist der <xref:System.Windows.Forms.ToolStrip> nicht Teil der Aktivierreihenfolge.  
  
-   Absolut positioniert  
  
     Der <xref:System.Windows.Forms.ToolStrip> verhält sich wie andere Steuerelemente, indem er von der <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft gesetzt wird, eine feste Größe hat und normalerweise Teil der Aktivierreiheinfolge ist.  
  
#### Tastaturinteraktion  
  
##### Zugriffstasten  
 Zusammen mit oder nach der ALT\-Taste gedrückte Tastenkombinationen bieten die Möglichkeit, ein Steuerelement mithilfe der Tastatur zu aktivieren.  <xref:System.Windows.Forms.ToolStrip> unterstützt sowohl explizite als auch implizite Tastenkombinationen.  Die explizite Definition verwendet ein kaufmännisches Und\-Zeichen \(&\), das dem Buchstaben vorausgeht.  Die implizite Definition verwendet einen Algorithmus, der versucht, ein passendes Element basierend auf der Reihenfolge der Buchstaben einer gegebenen `Text`\-Eigenschaft zu finden.  
  
##### Tastenkombinationen  
 Die vom <xref:System.Windows.Forms.MenuStrip> verwendeten Tastenkombinationen setzen eine Kombination der <xref:System.Windows.Forms.Keys>\-Aufzählung \(diese ist nicht von einer bestimmten Reihenfolge abhängig\) ein, um die Tastenkombination festzulegen.  Zudem kann die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>\-Eigenschaft verwendet werden, um eine Tastenkombination nur als Text anzuzeigen, beispielsweise die Anzeige von "Entf" anstelle von "Entfernen".  
  
##### Navigation  
 Die ALT\-Taste aktiviert den <xref:System.Windows.Forms.Form.MainMenuStrip%2A>, auf den durch <xref:System.Windows.Forms.MenuStrip> gezeigt wird.  Von dort navigiert STRG\+TAB zwischen <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen innerhalb von `ToolStripPanel`s.  Mithilfe der TAB\-Taste und der Pfeiltasten auf der Zehnertastatur wird zwischen <xref:System.Windows.Forms.ToolStrip>\-Elementen navigiert.  Ein spezieller Algorithmus steuert die Navigation im Überlaufbereich.  Mit der LEERTASTE kann <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton> oder <xref:System.Windows.Forms.ToolStripSplitButton> ausgewählt werden.  
  
##### Fokus und Validierung  
 Bei der Aktivierung über die ALT\-Taste übernehmen und entfernen <xref:System.Windows.Forms.MenuStrip> oder <xref:System.Windows.Forms.ToolStrip> den Fokus normalerweise nicht vom Steuerelement, das den Fokus gegenwärtig hat.  Wenn ein Steuerelement im <xref:System.Windows.Forms.MenuStrip> gehostet ist oder der <xref:System.Windows.Forms.MenuStrip> eine Dropdownliste enthält, erhält das Steuerelement den Fokus, wenn die TAB\-TASTE gedrückt wird.  Im Allgemeinen sollten die Ereignisse <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter> und <xref:System.Windows.Forms.Control.Leave> nicht vom <xref:System.Windows.Forms.MenuStrip> ausgelöst werden, wenn sie über die Tastatur aktiviert werden.  Verwenden Sie in solchen Fällen stattdessen die Ereignisse <xref:System.Windows.Forms.MenuStrip.MenuActivate> und <xref:System.Windows.Forms.MenuStrip.MenuDeactivate>.  
  
 Standardmäßig ist <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> auf `false` festgelegt.  Rufen Sie <xref:System.Windows.Forms.ContainerControl.Validate%2A> explizit auf dem Formular auf, um eine Validierung auszuführen.  
  
#### Layout  
 Sie steuern das <xref:System.Windows.Forms.ToolStrip>\-Layout, indem Sie einen der Member von <xref:System.Windows.Forms.ToolStripLayoutStyle> mit der <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>\-Eigenschaft auswählen.  
  
##### Stapellayouts  
 Beim Stapeln werden an beiden Enden des <xref:System.Windows.Forms.ToolStrip> Elemente nebeneinander angeordnet.  In der folgenden Liste werden die Stapellayouts beschrieben.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle> ist die Standardeinstellung.  Bei dieser Einstellung ändert der <xref:System.Windows.Forms.ToolStrip> sein Layout automatisch entsprechend der <xref:System.Windows.Forms.ToolStrip.Orientation%2A>\-Eigenschaft zum Behandeln von Zieh\- und Andockszenarios.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle> gibt die <xref:System.Windows.Forms.ToolStrip>\-Elemente vertikal nebeneinander wieder.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle> gibt die <xref:System.Windows.Forms.ToolStrip>\-Elemente horizontal nebeneinander wieder.  
  
##### Andere Features von Stapellayouts  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> bestimmt das Ende des <xref:System.Windows.Forms.ToolStrip>, an dem das Element ausgerichtet wird.  
  
 Wenn Elemente nicht in den <xref:System.Windows.Forms.ToolStrip> passen, wird automatisch eine Überlaufschaltfläche angezeigt.  Mit der <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>\-Eigenschaft wird festgelegt, ob ein Element im Überlaufbereich stets, bei Bedarf oder nie angezeigt wird.  
  
 Im <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>\-Ereignis können Sie die <xref:System.Windows.Forms.ToolStripItem.Placement%2A>\-Eigenschaft untersuchen und ermitteln, ob ein Element auf dem Haupt\-<xref:System.Windows.Forms.ToolStrip> oder dem Überlauf\-<xref:System.Windows.Forms.ToolStrip> platziert wurde oder derzeit nicht angezeigt wird.  Typische Gründe dafür, dass ein Element nicht angezeigt wird, liegen darin, dass das Element nicht auf den Haupt\-<xref:System.Windows.Forms.ToolStrip> passte und die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>\-Eigenschaft auf <xref:System.Windows.Forms.ToolStripItemOverflow> festgelegt wurde.  
  
 Ein <xref:System.Windows.Forms.ToolStrip> kann durch Platzieren in einem <xref:System.Windows.Forms.ToolStripPanel> und Festlegen des <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> auf <xref:System.Windows.Forms.ToolStripGripStyle> verschiebbar gestaltet werden.  
  
##### Andere Layoutoptionen  
 Weitere Layoutoptionen sind <xref:System.Windows.Forms.ToolStripLayoutStyle> und <xref:System.Windows.Forms.ToolStripLayoutStyle>.  
  
##### Flusslayout  
 Das <xref:System.Windows.Forms.ToolStripLayoutStyle>\-Layout ist die Standardeinstellung für <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> und <xref:System.Windows.Forms.ToolStripOverflow>.  Es ähnelt dem <xref:System.Windows.Forms.FlowLayoutPanel>.  <xref:System.Windows.Forms.ToolStripLayoutStyle>\-Layouts weisen folgende Features auf:  
  
-   Alle Features von <xref:System.Windows.Forms.FlowLayoutPanel> werden von der <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>\-Eigenschaft verfügbar gemacht.  Sie müssen die <xref:System.Windows.Forms.LayoutSettings>\-Klasse in eine <xref:System.Windows.Forms.FlowLayoutSettings>\-Klasse umwandeln.  
  
-   Mit der <xref:System.Windows.Forms.ToolStripItem.Dock%2A>\-Eigenschaft und der <xref:System.Windows.Forms.ToolStripItem.Anchor%2A>\-Eigenschaft können Sie im Code die Elemente innerhalb der Zeile ausrichten.  
  
-   Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>\-Eigenschaft wird ignoriert.  
  
-   Im <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>\-Ereignis können Sie die <xref:System.Windows.Forms.ToolStripItem.Placement%2A>\-Eigenschaft untersuchen und ermitteln, ob ein Element auf dem Haupt\-<xref:System.Windows.Forms.ToolStrip> platziert wurde oder dort nicht eingefügt werden konnte.  
  
-   Der Ziehpunkt wird nicht gerendert, sodass ein <xref:System.Windows.Forms.ToolStrip> im <xref:System.Windows.Forms.ToolStripLayoutStyle>\-Layoutstil in einem <xref:System.Windows.Forms.ToolStripPanel> nicht verschoben werden kann.  
  
-   Die <xref:System.Windows.Forms.ToolStrip>\-Überlaufschaltfläche wird nicht gerendert, und <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> wird ignoriert.  
  
##### Tabellenlayout  
 Das <xref:System.Windows.Forms.ToolStripLayoutStyle>\-Layout ist die Standardeinstellung für <xref:System.Windows.Forms.StatusStrip>.  Es ähnelt dem <xref:System.Windows.Forms.TableLayoutPanel>.  <xref:System.Windows.Forms.ToolStripLayoutStyle>\-Layouts weisen folgende Features auf:  
  
-   Alle Features von <xref:System.Windows.Forms.TableLayoutPanel> werden von der <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>\-Eigenschaft verfügbar gemacht.  Sie müssen die <xref:System.Windows.Forms.LayoutSettings>\-Klasse in eine <xref:System.Windows.Forms.TableLayoutSettings>\-Klasse umwandeln.  
  
-   Mit der <xref:System.Windows.Forms.ToolStripItem.Dock%2A>\-Eigenschaft und der <xref:System.Windows.Forms.ToolStripItem.Anchor%2A>\-Eigenschaft können Sie im Code die Elemente innerhalb der Tabellenzelle ausrichten.  
  
-   Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>\-Eigenschaft wird ignoriert.  
  
-   Im <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>\-Ereignis können Sie die <xref:System.Windows.Forms.ToolStripItem.Placement%2A>\-Eigenschaft untersuchen und ermitteln, ob ein Element auf dem Haupt\-<xref:System.Windows.Forms.ToolStrip> platziert wurde oder dort nicht eingefügt werden konnte.  
  
-   Da der Ziehpunkt nicht gerendert ist, kann <xref:System.Windows.Forms.ToolStrip> im <xref:System.Windows.Forms.ToolStripLayoutStyle>\-Layoutstil in einem <xref:System.Windows.Forms.ToolStripPanel> nicht verschoben werden.  
  
-   Die <xref:System.Windows.Forms.ToolStrip>\-Überlaufschaltfläche wird nicht gerendert, und <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> wird ignoriert.  
  
## ToolStripItem  
 In den folgenden Themen werden <xref:System.Windows.Forms.ToolStripItem> und die davon abgeleiteten Steuerelemente beschrieben.  
  
 <xref:System.Windows.Forms.ToolStripItem> ist die abstrakte Basisklasse für alle Elemente, die in einem <xref:System.Windows.Forms.ToolStrip> verwendet werden.  Das folgende Objektmodell veranschaulicht die Vererbungshierarchie von <xref:System.Windows.Forms.ToolStripItem>.  
  
 ![ToolStripItem&#45;Objektmodell](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.png "ToolStripItemObjectModel")  
ToolStripItem\-Objektmodell  
  
 <xref:System.Windows.Forms.ToolStripItem>\-Klassen erben entweder direkt von <xref:System.Windows.Forms.ToolStripItem>, oder sie erben indirekt von <xref:System.Windows.Forms.ToolStripItem> durch <xref:System.Windows.Forms.ToolStripControlHost> oder <xref:System.Windows.Forms.ToolStripDropDownItem>.  
  
 <xref:System.Windows.Forms.ToolStripItem>\-Steuerelemente müssen in einem <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip> oder <xref:System.Windows.Forms.ContextMenuStrip> enthalten sein und können einem Formular nicht direkt hinzugefügt werden.  Die verschiedenen Containerklassen wurden so entworfen, dass sie eine geeignete Teilmenge von <xref:System.Windows.Forms.ToolStripItem>\-Steuerelementen enthalten.  
  
 In der folgenden Tabelle werden die vordefinierten <xref:System.Windows.Forms.ToolStripItem>\-Steuerelemente und die Container, in denen sie am besten aussehen, aufgelistet.  <xref:System.Windows.Forms.ToolStrip>\-Elemente können zwar in jedem von <xref:System.Windows.Forms.ToolStrip> abgeleiteten Container gehostet werden, sehen jedoch in den folgenden Containern am besten aus:  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown> wird nicht in der Designertoolbox angezeigt.  
  
|Enthaltenes Element|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|-------------------------|---------------|---------------|----------------------|-----------------|-----------------------|  
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
  
### ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton> ist das Schaltflächenelement für <xref:System.Windows.Forms.ToolStrip>.  Es kann mit verschiedenen Rahmenstilen angezeigt werden, und es kann verwendet werden, um einen aktivierten betriebsfähigen Zustand darzustellen.  Sie können damit weiterhin festlegen, dass der Fokus standardmäßig auf dem Element liegt.  
  
### ToolStripLabel  
 <xref:System.Windows.Forms.ToolStripLabel> stellt eine Bezeichnungsfunktionalität in <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen bereit.  <xref:System.Windows.Forms.ToolStripLabel> ist wie <xref:System.Windows.Forms.ToolStripButton> jedoch ohne Standardfokus und wird nicht als aktiviert oder hervorgehoben gerendert.  
  
 <xref:System.Windows.Forms.ToolStripLabel> als unterstützt gehostetes Element Zugriffstasten.  
  
 Verwenden Sie die Eigenschaften <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> und <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> auf einem <xref:System.Windows.Forms.ToolStripLabel>, um die Linksteuerung in <xref:System.Windows.Forms.ToolStrip> zu unterstützen.  
  
### ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel> ist eine Version von <xref:System.Windows.Forms.ToolStripLabel>, die eigens zur Verwendung in <xref:System.Windows.Forms.StatusStrip> vorgesehen ist.  Die speziellen Features beinhalten <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A> und <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
### ToolStripSeparator  
 <xref:System.Windows.Forms.ToolStripSeparator> fügt eine vertikale oder eine horizontale Linie zu einer Symbolleiste oder einem Menü hinzu, je nach Ausrichtung.  Dieses Element bietet eine Gruppierung von Elementen oder Unterscheidung zwischen Elementen, wie z. B. in einem Menü.  
  
 Sie können einen <xref:System.Windows.Forms.ToolStripSeparator> zur Entwurfszeit hinzufügen, indem Sie diesen aus einer Dropdownliste auswählen.  Sie können auch automatisch einen <xref:System.Windows.Forms.ToolStripSeparator> erstellen, indem Sie entweder in die Designervorlageknoten oder in die <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>\-Methode einen Bindestrich \(\-\) eingeben.  
  
### ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost> ist die abstrakte Basisklasse für <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox> und <xref:System.Windows.Forms.ToolStripProgressBar>.  <xref:System.Windows.Forms.ToolStripControlHost> kann andere Steuerelemente, einschließlich benutzerdefinierter Steuerelemente, auf die folgenden zwei Arten hosten:  
  
-   Erstellen Sie einen <xref:System.Windows.Forms.ToolStripControlHost> mit einer Klasse, die von <xref:System.Windows.Forms.Control> abgeleitet ist.  Um auf das gehostete Steuerelement und die Eigenschaften vollständig zugreifen zu können, müssen Sie die <xref:System.Windows.Forms.ToolStripControlHost.Control%2A>\-Eigenschaft auf die eigentliche Klasse zurücksetzen, die sie darstellt.  
  
-   Erweitern Sie <xref:System.Windows.Forms.ToolStripControlHost>, und rufen Sie im Standardkonstruktor der geerbten Klasse den Basisklassenkonstruktor auf, der eine von <xref:System.Windows.Forms.Control> abgeleitete Klasse übergibt.  Diese Option ermöglicht es Ihnen, gängige Steuerelementmethoden und \-eigenschaften für leichten Zugriff mit einem <xref:System.Windows.Forms.ToolStrip> zu umschließen.  
  
### ToolStripComboBox  
 Bei <xref:System.Windows.Forms.ToolStripComboBox> handelt es sich um die zum Hosten in <xref:System.Windows.Forms.ToolStrip> optimierte Version von <xref:System.Windows.Forms.ComboBox>.  Eine Teilmenge der gehosteten Steuerelementeigenschaften und \-ereignisse wird auf der <xref:System.Windows.Forms.ToolStripComboBox>\-Ebene bereitgestellt. Auf die zugrunde liegenden <xref:System.Windows.Forms.ComboBox>\-Steuerelemente kann jedoch über die <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A>\-Eigenschaft vollständig zugegriffen werden.  
  
### ToolStripTextBox  
 Bei <xref:System.Windows.Forms.ToolStripTextBox> handelt es sich um die zum Hosten in <xref:System.Windows.Forms.ToolStrip> optimierte Version von <xref:System.Windows.Forms.TextBox>.  Eine Teilmenge der gehosteten Steuerelementeigenschaften und \-ereignisse wird auf der <xref:System.Windows.Forms.ToolStripTextBox>\-Ebene bereitgestellt. Auf die zugrunde liegenden <xref:System.Windows.Forms.TextBox>\-Steuerelemente kann jedoch über die <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A>\-Eigenschaft vollständig zugegriffen werden.  
  
### ToolStripProgressBar  
 Bei <xref:System.Windows.Forms.ToolStripProgressBar> handelt es sich um die zum Hosten in <xref:System.Windows.Forms.ToolStrip> optimierte Version von <xref:System.Windows.Forms.ProgressBar>.  Eine Teilmenge der gehosteten Steuerelementeigenschaften und \-ereignisse wird auf der <xref:System.Windows.Forms.ToolStripProgressBar>\-Ebene bereitgestellt. Auf die zugrunde liegenden <xref:System.Windows.Forms.ProgressBar>\-Steuerelemente kann jedoch über die <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A>\-Eigenschaft vollständig zugegriffen werden.  
  
### ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem> ist die abstrakte Basisklasse für <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton> und <xref:System.Windows.Forms.ToolStripSplitButton>, die Elemente direkt hosten oder zusätzliche Elemente in einem Dropdowncontainer hosten kann.  Hierzu wird die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A>\-Eigenschaft auf <xref:System.Windows.Forms.ToolStripDropDown> und die <xref:System.Windows.Forms.ToolStrip.Items%2A>\-Eigenschaft von <xref:System.Windows.Forms.ToolStripDropDown> festgelegt.  Auf diese Dropdownelemente kann direkt über die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>\-Eigenschaft zugegriffen werden.  
  
### ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem> ist ein <xref:System.Windows.Forms.ToolStripDropDownItem>, das mit <xref:System.Windows.Forms.ToolStripDropDownMenu> und <xref:System.Windows.Forms.ContextMenuStrip> verwendet wird, um die speziellen Hervorhebungs\-, Layout\- und Spaltenanordnungsereignisse für Menüs zu behandeln.  
  
### ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton> ähnelt im Erscheinungsbild <xref:System.Windows.Forms.ToolStripButton>. Beim Klicken wird jedoch ein Dropdownbereich angezeigt.  Ein\- oder Ausblenden des Dropdownpfeils mithilfe der <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A>\-Eigenschaft.  <xref:System.Windows.Forms.ToolStripDropDownButton> stellt den Host für eine <xref:System.Windows.Forms.ToolStripOverflowButton> dar, die Elemente anzeigt, die <xref:System.Windows.Forms.ToolStrip> überschreiten.  
  
### ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton> kombiniert die Funktionalität einer Schaltfläche und einer Dropdownschaltfläche.  
  
 Verwenden Sie die <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A>\-Eigenschaft, um das <xref:System.Windows.Forms.Control.Click>\-Ereignis aus den ausgewählten Dropdownelementen mit dem in der Schaltfläche angezeigten Element zu synchronisieren.  
  
### ToolStripItem – Allgemeine Features  
 <xref:System.Windows.Forms.ToolStripItem> stellt die folgenden allgemeinen Features und Optionen für erbende Steuerelemente zur Verfügung:  
  
-   Hauptereignisse  
  
-   Bildbehandlung  
  
-   Ausrichtung  
  
-   Text\- und Bildbeziehungen  
  
-   Anzeigeformat  
  
#### Hauptereignisse  
 <xref:System.Windows.Forms.ToolStripItem>\-Steuerelemente erhalten eigene Klick\-, Maus\- und Zeichnenereignisse und können auch in einem gewissen Umfang eine Tastaturvorverarbeitung ausführen.  
  
#### Bildbehandlung  
 Die Eigenschaften <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A> und <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> beeinflussen verschiedene Aspekte der Bildbehandlung.  Verwenden Sie Bilder in <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen durch direktes Festlegen dieser Eigenschaften oder durch Festlegen <xref:System.Windows.Forms.ToolStrip.ImageList%2A>\-Eigenschaft nur zur Laufzeit.  
  
 Die Bildskalierung wird durch die Interaktion der Eigenschaften in <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStripItem> folgendermaßen bestimmt:  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> ist die Skalierung des endgültigen Bilds entsprechend der Kombination aus der <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A>\-Einstellung des Bilds und der <xref:System.Windows.Forms.ToolStrip.AutoSize%2A>\-Einstellung des Containers.  
  
    -   Wenn <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> auf `true` gesetzt ist \(dies ist die Standardeinstellung\) und <xref:System.Windows.Forms.ToolStripItemImageScaling> auf <xref:System.Windows.Forms.ToolStripItemImageScaling>, wird keine Bildskalierung ausgeführt, und die <xref:System.Windows.Forms.ToolStrip>\-Größe entspricht der des größten Elements oder einer festgelegten Mindestgröße.  
  
    -   Wenn <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> auf `false` festgelegt ist und <xref:System.Windows.Forms.ToolStripItemImageScaling> auf <xref:System.Windows.Forms.ToolStripItemImageScaling>, wird weder das Bild skaliert noch die <xref:System.Windows.Forms.ToolStrip>\-Skalierung ausgeführt.  
  
#### Ausrichtung  
 Der Wert der <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>\-Eigenschaft ermittelt das Ende von <xref:System.Windows.Forms.ToolStrip>, bei dem ein Element angezeigt wird.  Die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>\-Eigenschaft funktioniert nur, wenn der Layoutstil von <xref:System.Windows.Forms.ToolStrip> auf einen der Stapelüberlaufwerte festgelegt ist.  
  
 Elemente werden in <xref:System.Windows.Forms.ToolStrip> in der Reihenfolge platziert, in der sie in der Elementauflistung eingeblendet werden.  Zum programmgesteuerten Ändern der Position eines Elements verwenden Sie die <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A>\-Methode, um das Element in die Auflistung zu verschieben.  Mit dieser Methode wird das Element verschoben, jedoch nicht verdoppelt.  
  
#### Text\- und Bildbeziehung  
 Die <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>\-Eigenschaft legt die relative Position des Bilds unter Berücksichtigung des Texts auf einem <xref:System.Windows.Forms.ToolStripItem> fest.  Elemente ohne Bild, Text oder beides werden als besondere Fälle behandelt, sodass das <xref:System.Windows.Forms.ToolStripItem> keinen leeren Bereich für die fehlenden Bild\- oder Textelemente anzeigt.  
  
#### Anzeigestil  
 Mit <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> können die Werte der Text\- und Bildeigenschaften eines Elements festgelegt werden, um nur die gewünschten Elemente anzuzeigen.  Normalerweise wird diese Option verwendet, wenn nur der Anzeigestil geändert werden soll, während das gleiche Element in einem anderen Zusammenhang angezeigt wird.  
  
## Zusätzliche Klassen  
 Im Folgenden sind Klassen für verschiedene andere Funktionen aufgeführt:  
  
-   <xref:System.Windows.Forms.ToolStripManager> unterstützt <xref:System.Windows.Forms.ToolStrip>\-bezogene Aufgaben für ganze Anwendungen, z. B. Zusammenführungs\-, Einstellungs\- und Renderoptionen.  
  
-   Mit <xref:System.Windows.Forms.ToolStripRenderer> kann auf einfache Weise ein bestimmter Stil oder ein Design für einen <xref:System.Windows.Forms.ToolStrip> übernommen werden.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> erstellt Stifte und Pinsel auf Grundlage einer ersetzbaren Farbtabelle \(<xref:System.Windows.Forms.ProfessionalColorTable>\).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> wendet Systemfarben und eine zweidimensionale Ansicht auf <xref:System.Windows.Forms.ToolStrip>\-Anwendungen an.  
  
-   <xref:System.Windows.Forms.ToolStripContainer> ist <xref:System.Windows.Forms.SplitContainer> ähnlich.  Hierbei werden vier angedockte Seitenbereiche \(Instanzen von <xref:System.Windows.Forms.ToolStripPanel>\) und ein zentraler Bereich \(eine Instanz von <xref:System.Windows.Forms.ToolStripContentPanel>\) verwendet, um eine typische Anordnung zu erstellen.  Die Seitenbereiche können nicht entfernt jedoch ausgeblendet werden.  Der zentrale Bereich kann weder entfernt noch ausgeblendet werden.  Eines oder mehrere der Steuerelemente <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> oder <xref:System.Windows.Forms.StatusStrip> können in den Seitenbereichen angeordnet werden, und der zentrale Bereich lässt sich auch für andere Steuerelemente verwenden.  Das <xref:System.Windows.Forms.ToolStripContentPanel> enthält außerdem eine Möglichkeit, durch die Unterstützung des Renderings im Text des Formulars eine einheitliche Darstellung zu erreichen.  Der <xref:System.Windows.Forms.ToolStripContainer> unterstützt MDI \(Multiple Document Interface\)\-Anwendungen nicht.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> bietet einen Bereich, um <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente zu verschieben und anzuordnen.  Wenn Sie diese Auswahl treffen, können Sie nur einen Bereich verwenden, wobei <xref:System.Windows.Forms.ToolStripPanel> gut in MDI\-Szenarien funktioniert.  
  
## Siehe auch  
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Zusammenfassung der ToolStrip\-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [StatusStrip\-Steuerelement](../../../../docs/framework/winforms/controls/statusstrip-control.md)   
 [ContextMenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)   
 [BindingNavigator\-Steuerelement](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)