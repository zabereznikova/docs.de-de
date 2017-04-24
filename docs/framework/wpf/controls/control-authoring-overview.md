---
title: "&#220;bersicht &#252;ber das Erstellen von Steuerelementen | Microsoft Docs"
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
  - "Authoringübersicht für Steuerelemente"
  - "Steuerelemente, Authoringübersicht"
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# &#220;bersicht &#252;ber das Erstellen von Steuerelementen
Dank der Erweiterbarkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Steuerelementmodells ist es nur selten erforderlich, ein neues Steuerelement zu erstellen.  In bestimmten Fällen kann es jedoch auch weiterhin erforderlich sein, ein benutzerdefiniertes Steuerelement zu erstellen.  In diesem Thema werden die Features erläutert, dank denen ein benutzerdefiniertes Steuerelement nur noch selten erstellt werden muss, und es werden die verschiedenen Modelle für das Erstellen von Steuerelementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] beschrieben.  Dieses Thema veranschaulicht auch, wie ein neues Steuerelement erstellt wird.  
  
   
  
<a name="when_to_write_a_new_control"></a>   
## Alternativen zum Schreiben eines neuen Steuerelements  
 Wenn Sie in der Vergangenheit ein vorhandenes Steuerelement an eigene Zwecke anpassen wollten, waren Sie darauf beschränkt, die Standardeigenschaften des Steuerelements zu ändern, also Hintergrundfarbe, Rahmenbreite und Schriftgröße.  Wenn Sie das Aussehen oder Verhalten eines Steuerelements über diese vordefinierten Parameter hinaus erweitern möchten, müssen Sie ein neues Steuerelement erstellen. Normalerweise verwenden Sie dazu die Vererbung von einem vorhandenen Steuerelement und das Überschreiben der Methode, die für das Zeichnen des Steuerelements zuständig ist.  Dies ist auch weiterhin möglich, aber Sie können vorhandene Steuerelemente mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anpassen, indem Sie das umfangreiche Inhaltsmodell sowie die Stile, Vorlagen und Trigger verwenden.  Die folgende Liste enthält Beispiele dazu, wie Sie mit diesen Features benutzerdefinierte und einheitliche Abläufe erzielen, ohne ein neues Steuerelement erstellen zu müssen.  
  
-   **Umfangreicher Inhalt** Viele der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Standardsteuerelemente unterstützen umfangreichen Inhalt.  Die Inhaltseigenschaft eines <xref:System.Windows.Controls.Button>\-Elements hat z. B. den Typ <xref:System.Object>, sodass auf einem <xref:System.Windows.Controls.Button>\-Element theoretisch alles angezeigt werden kann.  Damit eine Schaltfläche ein Bild und Text anzeigt, können Sie ein Bild und einen <xref:System.Windows.Controls.TextBlock> einem <xref:System.Windows.Controls.StackPanel> hinzufügen und das <xref:System.Windows.Controls.StackPanel> der <xref:System.Windows.Controls.ContentControl.Content%2A>\-Eigenschaft zuweisen.  Da diese Steuerelemente visuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elemente und beliebige Daten anzeigen können, ist das Erstellen neuer Steuerelemente oder das Ändern vorhandener Steuerelemente zur Unterstützung einer komplexen visuellen Darstellung nur noch selten notwendig.  Weitere Informationen zum Inhaltsmodell für <xref:System.Windows.Controls.Button> sowie anderen Inhaltsmodellen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [WPF\-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
-   **Stile** Ein <xref:System.Windows.Style> ist eine Auflistung von Werten, die Eigenschaften für ein Steuerelement darstellen.  Durch die Verwendung von Stilen können Sie eine wiederverwendbare Darstellung des gewünschten Aussehens und Verhaltens eines Steuerelements ohne Schreiben eines neuen Steuerelements erstellen.  Beispiel: Sie möchten alle <xref:System.Windows.Controls.TextBlock>\-Steuerelemente rot mit der Schriftart Arial und einem Schriftgrad von 14 formatieren.  Sie können ein Format als Ressource erstellen und die jeweiligen Eigenschaften entsprechend festlegen.  So verfügt jeder <xref:System.Windows.Controls.TextBlock>, den Sie der Anwendung hinzufügen, über die gleiche Darstellung.  
  
-   **Datenvorlagen** Mithilfe einer <xref:System.Windows.DataTemplate> können Sie anpassen, wie Daten auf einem Steuerelement angezeigt werden.  Zum Beispiel können Sie eine <xref:System.Windows.DataTemplate> verwenden, um anzugeben, wie Daten in einem <xref:System.Windows.Controls.ListBox> angezeigt werden.  Ein Beispiel hierfür finden Sie unter [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md).  Zusätzlich zum Anpassen der Datendarstellung kann eine <xref:System.Windows.DataTemplate> Benutzeroberflächenelemente enthalten. Auf diese Weise können Sie beim Erstellen benutzerdefinierter Oberflächen flexibel vorgehen.  Mithilfe einer <xref:System.Windows.DataTemplate> können Sie z. B. ein <xref:System.Windows.Controls.ComboBox>\-Element erstellen, in dem jedes Element ein Kontrollkästchen enthält.  
  
-   **Steuerelementvorlagen.** Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwenden eine <xref:System.Windows.Controls.ControlTemplate>, um die Struktur und Darstellung eines Steuerelements zu definieren, wodurch die Darstellung eines Steuerelements von seiner Funktionalität getrennt wird. Sie können die Darstellung eines Steuerelements stark verändern, indem Sie seine <xref:System.Windows.Controls.ControlTemplate> neu definieren.  Angenommen, Sie möchten ein Steuerelement erstellen, das wie eine Ampel aussieht.  Dieses Steuerelement verfügt über eine einfache Benutzeroberfläche und Funktion.  Das Steuerelement besteht aus drei Kreisen, von denen nur jeweils einer leuchten kann.  Nach einiger Überlegung stellen Sie fest, dass ein <xref:System.Windows.Controls.RadioButton>\-Element über die Funktion verfügt, bei der jeweils eine Komponente ausgewählt ist. Das standardmäßige Aussehen des <xref:System.Windows.Controls.RadioButton>\-Elements entspricht jedoch überhaupt nicht einer Ampel.  Da das <xref:System.Windows.Controls.RadioButton>\-Element zum Definieren seines Aussehens eine Steuerelementvorlage verwendet, können Sie die <xref:System.Windows.Controls.ControlTemplate> auf einfache Weise neu definieren, um die Anforderungen des Steuerelements zu erfüllen und die Ampel mithilfe von Optionsfeldern zu erstellen.  
  
    > [!NOTE]
    >  Obwohl ein <xref:System.Windows.Controls.RadioButton>\-Element eine <xref:System.Windows.DataTemplate> verwenden kann, ist eine <xref:System.Windows.DataTemplate> in diesem Beispiel nicht ausreichend.  Die <xref:System.Windows.DataTemplate> definiert die Darstellung des Inhalts eines Steuerelements.  Bei einem <xref:System.Windows.Controls.RadioButton>\-Element ist der Inhalt das, was rechts von dem Kreis angezeigt wird, der angibt, ob das <xref:System.Windows.Controls.RadioButton>\-Element aktiviert ist.  Für das Beispiel mit der Ampel muss das Optionsfeld nur ein Kreis sein, der leuchten kann. Da die Darstellungsanforderung für die Ampel sich so stark von der Standarddarstellung des <xref:System.Windows.Controls.RadioButton>\-Elements unterscheidet, müssen Sie die <xref:System.Windows.Controls.ControlTemplate> neu definieren.  Normalerweise wird eine <xref:System.Windows.DataTemplate> verwendet, um den Inhalt \(bzw. die Daten\) eines Steuerelements zu definieren, und eine <xref:System.Windows.Controls.ControlTemplate> wird verwendet, um die Strukturierung eines Steuerelements zu definieren.  
  
-   **Trigger** Mit einem <xref:System.Windows.Trigger> können Sie das Aussehen und Verhalten eines Steuerelements dynamisch ändern, ohne ein neues Steuerelement erstellen zu müssen.  Angenommen, Sie verwenden in der Anwendung mehrere <xref:System.Windows.Controls.ListBox>\-Steuerelemente und möchten, dass die Elemente in allen <xref:System.Windows.Controls.ListBox>\-Objekten fett und rot angezeigt werden, wenn sie markiert werden.  Sie neigen ggf. zuerst dazu, eine Klasse zu erstellen, die von <xref:System.Windows.Controls.ListBox> erbt, und die <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A>\-Methode zu überschreiben, um das Aussehen des markierten Elements zu ändern. Es ist jedoch besser, einem Stil eines <xref:System.Windows.Controls.ListBoxItem>\-Objekts einen Trigger hinzuzufügen, der das Aussehen des markierten Elements ändert.  Mit einem Trigger können Sie Eigenschaftswerte ändern oder basierend auf dem Wert einer Eigenschaft Aktionen ausführen.  Mit einem <xref:System.Windows.EventTrigger> können Sie Aktionen ausführen, wenn ein Ereignis eintritt.  
  
 Weitere Informationen zu Stilen, Vorlagen und Triggern finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Wenn ein Steuerelement über die Funktionalität eines vorhandenen Steuerelements verfügt, Sie jedoch ein anderes Aussehen benötigen, sollten Sie zuerst die Verwendung der Methoden erwägen, die in diesem Abschnitt erläutert werden, um das Aussehen eines vorhandenen Steuerelements zu ändern.  
  
<a name="models_for_control_authoring"></a>   
## Modelle für das Erstellen von Steuerelementen  
 Das umfangreiche Inhaltsmodell sowie die Stile, Vorlagen und Trigger sorgen dafür, dass Sie in vielen Fällen kein neues Steuerelement erstellen müssen.  Wenn Sie jedoch ein neues Steuerelement erstellen müssen, sollten Sie mit den verschiedenen Modellen zum Erstellen von Steuerelementen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vertraut sein. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt drei allgemeine Modelle zum Erstellen eines Steuerelements bereit, die jeweils verschiedene Features und Flexibilitätsgrade bieten.  Die Basisklassen für die drei Modelle sind <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control> und <xref:System.Windows.FrameworkElement>.  
  
### Ableiten von UserControl  
 Die einfachste Möglichkeit zum Erstellen eines Steuerelements in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist die Ableitung von <xref:System.Windows.Controls.UserControl>.  Wenn Sie ein Steuerelement erstellen, das von <xref:System.Windows.Controls.UserControl> erbt, fügen Sie dem <xref:System.Windows.Controls.UserControl>\-Element vorhandene Komponenten hinzu und verweisen mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] auf Ereignishandler.  Sie können dann auf die benannten Elemente verweisen und die Ereignishandler im Code definieren.  Dieses Entwicklungsmodell ähnelt dem Modell, das in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für die Anwendungsentwicklung verwendet wird.  
  
 Ein <xref:System.Windows.Controls.UserControl> kann, wenn es ordnungsgemäß erstellt wurde, die Vorteile von umfangreichem Inhalt, Stilen und Triggern nutzen.  Wenn das Steuerelement jedoch von <xref:System.Windows.Controls.UserControl> erbt, können Personen, die das Steuerelement verwenden, keine <xref:System.Windows.DataTemplate> oder <xref:System.Windows.Controls.ControlTemplate> verwenden, um dessen Aussehen anzupassen.  Es ist eine Ableitung von der <xref:System.Windows.Controls.Control>\-Klasse oder einer ihrer abgeleiteten Klassen \(mit Ausnahme von <xref:System.Windows.Controls.UserControl>\) erforderlich, um ein benutzerdefiniertes Steuerelement zu erstellen, das Vorlagen unterstützt.  
  
#### Vorteile der Ableitung von UserControl  
 Erwägen Sie die Ableitung von <xref:System.Windows.Controls.UserControl>, wenn alle folgenden Bedingungen gelten:  
  
-   Sie möchten das Steuerelement in ähnlicher Weise wie eine Anwendung erstellen.  
  
-   Das Steuerelement besteht nur aus bereits vorhandenen Komponenten.  
  
-   Sie müssen keine komplexe Anpassung unterstützen.  
  
### Ableiten von Control  
 Eine Ableitung von der <xref:System.Windows.Controls.Control>\-Klasse ist das Modell, das die meisten der vorhandenen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente verwenden.  Wenn Sie ein Steuerelement erstellen, das von der <xref:System.Windows.Controls.Control>\-Klasse erbt, definieren Sie das Aussehen mithilfe von Vorlagen.  Dabei trennen Sie die Funktionslogik von der visuellen Darstellung.  Sie können die Entkopplung der Benutzeroberfläche und der Logik auch sicherstellen, indem Sie anstelle von Ereignissen Befehle und Bindungen verwenden und Verweise auf Elemente in der <xref:System.Windows.Controls.ControlTemplate> nach Möglichkeit vermeiden. Wenn die Benutzeroberfläche und die Logik des Steuerelements korrekt entkoppelt sind, können die Benutzer des Steuerelements die <xref:System.Windows.Controls.ControlTemplate> des Steuerelements neu definieren, um seine Darstellung anzupassen. Auch wenn das Erstellen eines benutzerdefinierten <xref:System.Windows.Controls.Control> nicht so einfach ist wie das Erstellen eines <xref:System.Windows.Controls.UserControl>, bietet ein benutzerdefiniertes <xref:System.Windows.Controls.Control> doch die größte Flexibilität.  
  
#### Vorteile der Ableitung von Control  
 Wenn einer oder mehrere der folgenden Umstände zutreffen, sollten Sie die Ableitung von <xref:System.Windows.Controls.Control> statt der Verwendung der <xref:System.Windows.Controls.UserControl>\-Klasse in Betracht ziehen:  
  
-   Sie möchten, dass die Darstellung des Steuerelements über die <xref:System.Windows.Controls.ControlTemplate> anpassbar ist.  
  
-   Sie möchten, dass das Steuerelement verschiedene Designs unterstützt.  
  
### Ableiten von FrameworkElement  
 Steuerelemente, die von <xref:System.Windows.Controls.UserControl> oder <xref:System.Windows.Controls.Control> abgeleitet werden, basieren auf dem Zusammensetzen vorhandener Elemente.  In vielen Fällen ist dies akzeptabel, da sich Objekte, die von <xref:System.Windows.FrameworkElement> erben, in einer <xref:System.Windows.Controls.ControlTemplate> befinden können.  Es kann jedoch vorkommen, dass die Darstellung eines Steuerelements mehr als die Funktionalität einer einfachen Elementzusammensetzung erfordert.  Für solche Szenarien sollte eine Komponente auf der Basis von <xref:System.Windows.FrameworkElement> erstellt werden.  
  
 Es gibt zwei Standardmethoden zum Erstellen von auf <xref:System.Windows.FrameworkElement> basierenden Komponenten: direktes Rendering und benutzerdefinierte Elementzusammensetzung.  Das direkte Rendering beinhaltet das Überschreiben der <xref:System.Windows.UIElement.OnRender%2A>\-Methode von <xref:System.Windows.FrameworkElement> und das Bereitstellen von <xref:System.Windows.Media.DrawingContext>\-Operationen, die die visuelle Struktur der Komponente explizit definieren.  Diese Methode wird von <xref:System.Windows.Controls.Image> und <xref:System.Windows.Controls.Border> verwendet.  Die benutzerdefinierte Elementzusammensetzung beinhaltet das Verwenden von Objekten des Typs <xref:System.Windows.Media.Visual>, um die Darstellung der Komponente zusammenzusetzen.  Ein Beispiel finden Sie unter [Verwenden von DrawingVisual\-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  <xref:System.Windows.Controls.Primitives.Track> ist ein Beispiel für ein Steuerelement in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], das die benutzerdefinierte Elementzusammensetzung verwendet.  Es ist auch möglich, direktes Rendering und benutzerdefinierte Elementzusammensetzung im gleichen Steuerelement zu kombinieren.  
  
#### Vorteile der Ableitung von FrameworkElement  
 Erwägen Sie die Ableitung von <xref:System.Windows.FrameworkElement>, wenn eine oder mehrere der folgenden Bedingungen gelten:  
  
-   Sie benötigen eine genaue Steuerung der Darstellung des Steuerelements, die über das hinausgeht, was die einfache Elementzusammensetzung bietet.  
  
-   Sie möchten die Darstellung des Steuerelements definieren, indem Sie eine eigene Renderinglogik definieren.  
  
-   Sie möchten vorhandene Elemente in einer Weise neu zusammensetzen, die über das hinausgeht, was mit <xref:System.Windows.Controls.UserControl> und <xref:System.Windows.Controls.Control> möglich ist.  
  
<a name="control_authoring_basics"></a>   
## Grundlagen des Erstellens von Steuerelementen  
 Wie bereits erwähnt, ist eine der leistungsfähigsten Funktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Möglichkeit, über die Festlegung der grundlegenden Eigenschaften eines Steuerelements zum Ändern der Darstellung und des Verhaltens hinausgehen zu können, ohne ein benutzerdefiniertes Steuerelement erstellen zu müssen. Die Funktionen für Stil, Datenbindung und Trigger werden durch das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem und das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignissystem ermöglicht. In den folgenden Abschnitten werden einige Verfahren beschrieben, die Sie unabhängig von dem zum Erstellen des benutzerdefinierten Steuerelements verwendeten Modell befolgen sollten, damit Benutzer des benutzerdefinierten Steuerelements diese Funktionen wie bei einem in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthaltenen Steuerelement verwenden können.  
  
### Verwenden von Abhängigkeitseigenschaften  
 Wenn es sich bei einer Eigenschaft um eine Abhängigkeitseigenschaft handelt, können Sie wie folgt vorgehen:  
  
-   Legen Sie die Eigenschaft in einem Stil fest.  
  
-   Binden Sie die Eigenschaft an eine Datenquelle.  
  
-   Verwenden Sie eine dynamische Ressource als Wert der Eigenschaft.  
  
-   Animieren Sie die Eigenschaft.  
  
 Wenn Sie möchten, dass eine Eigenschaft des Steuerelements diese Funktionalität unterstützt, sollten Sie sie als Abhängigkeitseigenschaft implementieren.  Im folgenden Beispiel wird eine Abhängigkeitseigenschaft mit dem Namen `Value` definiert, indem wie folgt vorgegangen wird:  
  
-   Ein <xref:System.Windows.DependencyProperty>\-Bezeichner mit dem Namen `ValueProperty` wird als `public` `static` `readonly`\-Feld definiert.  
  
-   Der Eigenschaftenname wird beim Eigenschaftensystem registriert, indem <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=fullName> aufgerufen wird, um Folgendes anzugeben:  
  
    -   Name der Eigenschaft.  
  
    -   Der Typ der Eigenschaft.  
  
    -   Typ, der die Eigenschaft besitzt.  
  
    -   Die Metadaten für die Eigenschaft.  Die Metadaten enthalten den Standardwert der Eigenschaft, einen <xref:System.Windows.CoerceValueCallback> und einen <xref:System.Windows.PropertyChangedCallback>.  
  
-   Eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Wrappereigenschaft mit dem Namen `Value` wird definiert. Dies ist derselbe Name, der zum Registrieren der Abhängigkeitseigenschaft verwendet wird, indem die Accessoren `get` und `set` der Eigenschaft implementiert werden.  Beachten Sie, dass die Accessoren `get` und `set` nur <xref:System.Windows.DependencyObject.GetValue%2A> bzw. <xref:System.Windows.DependencyObject.SetValue%2A> aufrufen.  Es ist zu empfehlen, dass die Accessoren von Abhängigkeitseigenschaften keine zusätzliche Logik enthalten, da Clients und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Accessoren umgehen und <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> direkt aufrufen können.  Wenn eine Eigenschaft z. B. an eine Datenquelle gebunden ist, wird der `set`\-Accessor der Eigenschaft nicht aufgerufen.  Anstatt den Accessoren get und set zusätzliche Logik hinzuzufügen, sollten Sie die Delegaten <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.CoerceValueCallback> und <xref:System.Windows.PropertyChangedCallback> verwenden, um auf den Wert zu reagieren bzw. den Wert zu prüfen, wenn dieser sich ändert.  Weitere Informationen zu diesen Rückrufen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
-   Definieren Sie eine Methode für den <xref:System.Windows.CoerceValueCallback> mit dem Namen `CoerceValue`.  `CoerceValue` stellt sicher, dass `Value` größer oder gleich `MinValue` und kleiner oder gleich `MaxValue` ist.  
  
-   Definieren Sie eine Methode für den <xref:System.Windows.PropertyChangedCallback> mit dem Namen `OnValueChanged`.  `OnValueChanged` erstellt ein <xref:System.Windows.RoutedPropertyChangedEventArgs%601>\-Objekt und bereitet das Auslösen des `ValueChanged`\-Routingereignisses vor.  Routingereignisse werden im nächsten Abschnitt erläutert.  
  
 [!code-csharp[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
 [!code-vb[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]  
  
 Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
### Verwenden von Routingereignissen  
 Ähnlich wie [Abhängigkeitseigenschaften](GTMT), die das Konzept der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaften um zusätzliche Funktionen erweitern, erweitern [Routingereignisse](GTMT) das Konzept der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Standardereignisse.  Beim Erstellen eines neuen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelements ist es außerdem ratsam, das Ereignis als Routingereignis zu implementieren, da ein Routingereignis das folgende Verhalten unterstützt:  
  
-   Ereignisse können über ein übergeordnetes Element mehrerer Steuerelemente behandelt werden.  Wenn es sich bei einem Ereignis um ein Bubbling\-Ereignis handelt, kann ein einzelnes übergeordnetes Element in der Elementstruktur das Ereignis abonnieren.  Dann können Anwendungsentwickler einen Handler verwenden, um auf das Ereignis mehrerer Steuerelemente zu reagieren.  Wenn das Steuerelement z. B. jeweils Teil der Elemente in einem <xref:System.Windows.Controls.ListBox>\-Objekt ist \(weil es in einer <xref:System.Windows.DataTemplate> enthalten ist\), kann der Anwendungsentwickler den Ereignishandler für das Ereignis des betreffenden Steuerelements unter <xref:System.Windows.Controls.ListBox> definieren.  Der Ereignishandler wird jeweils aufgerufen, wenn das Ereignis für eines der Steuerelemente auftritt.  
  
-   Sie können Routingereignisse in einem <xref:System.Windows.EventSetter> verwenden, damit Anwendungsentwickler den Handler eines Ereignisses innerhalb eines Stils angeben können.  
  
-   Sie können Routingereignisse in einem <xref:System.Windows.EventTrigger> verwenden. Dies ist hilfreich beim Animieren von Eigenschaften mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Im folgenden Beispiel wird ein Routingereignis definiert, indem wie folgt vorgegangen wird:  
  
-   Definieren Sie einen <xref:System.Windows.RoutedEvent>\-Bezeichner mit dem Namen `ValueChangedEvent` als `public` `static` `readonly`\-Feld.  
  
-   Das Routingereignis wird registriert, indem die <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=fullName>\-Methode aufgerufen wird.  Im Beispiel werden beim Aufrufen von <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> die folgenden Informationen angegeben:  
  
    -   Der Name des Ereignisses lautet `ValueChanged`.  
  
    -   Die Routingstrategie ist <xref:System.Windows.RoutingStrategy>. Dies bedeutet, dass zuerst ein Ereignishandler auf der Quelle \(Objekt, das das Ereignis auslöst\) aufgerufen wird. Danach werden nacheinander die Ereignishandler der übergeordneten Elemente der Quelle aufgerufen, wobei mit dem Ereignishandler des jeweils nächsten übergeordneten Elements begonnen wird.  
  
    -   Der Typ des Ereignishandlers ist <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, der mit einem <xref:System.Decimal>\-Typ erstellt wird.  
  
    -   Der besitzende Typ des Ereignisses ist `NumericUpDown`.  
  
-   Ein öffentliches Ereignis mit dem Namen `ValueChanged` wird deklariert, wobei Ereignisaccessordeklarationen eingeschlossen werden.  Im Beispiel wird <xref:System.Windows.UIElement.AddHandler%2A> in der `add`\-Accessordeklaration und <xref:System.Windows.UIElement.RemoveHandler%2A> in der `remove`\-Accessordeklaration aufgerufen, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignisdienste zu verwenden.  
  
-   Eine geschützte virtuelle Methode mit dem Namen `OnValueChanged` wird erstellt, die das `ValueChanged`\-Ereignis auslöst.  
  
 [!code-csharp[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
 [!code-vb[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]  
  
 Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md) und unter [Erstellen eines benutzerdefinierten Routingereignisses](../../../../docs/framework/wpf/advanced/how-to-create-a-custom-routed-event.md).  
  
### Verwenden der Bindung  
 Um die Benutzeroberfläche des Steuerelements von seiner Logik zu entkoppeln, können Sie erwägen, die Datenbindung zu verwenden.  Dies ist besonders wichtig, wenn Sie die Darstellung des Steuerelements mithilfe einer <xref:System.Windows.Controls.ControlTemplate> definieren.  Wenn Sie die Datenbindung verwenden, ist es ggf. nicht mehr erforderlich, auf bestimmte Teile der Benutzeroberfläche zu verweisen.  Vermeiden Sie Verweise auf Elemente in der <xref:System.Windows.Controls.ControlTemplate>. Wenn der Code auf Elemente in der <xref:System.Windows.Controls.ControlTemplate> verweist und die <xref:System.Windows.Controls.ControlTemplate> geändert wird, muss das Element, auf das verwiesen wird, in die neue <xref:System.Windows.Controls.ControlTemplate> aufgenommen werden.  
  
 Im folgenden Beispiel wird der <xref:System.Windows.Controls.TextBlock> des `NumericUpDown`\-Steuerelements aktualisiert, indem ein Name zugewiesen und im Code auf das Textfeld verwiesen wird.  
  
 [!code-xml[UserControlNumericUpDownSimple#UIRefMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]  
  
 [!code-csharp[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
 [!code-vb[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]  
  
 Im folgenden Beispiel wird die Bindung verwendet, um dasselbe Ziel zu erreichen.  
  
 [!code-xml[UserControlNumericUpDown#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]  
  
 Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
### Entwerfen für Designer  
 Führen Sie die folgenden Schritte aus, um eine Unterstützung für benutzerdefinierte WPF\-Steuerelemente in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] zu erhalten \(beispielsweise das Bearbeiten von Eigenschaften mit dem Eigenschaftenfenster\).  Weitere Informationen zur [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]\-Entwicklung finden Sie unter [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26).  
  
#### Abhängigkeitseigenschaften  
 Stellen Sie sicher, dass Sie die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Accessoren `get` und `set` implementieren. Dies ist weiter oben unter "Verwenden von Abhängigkeitseigenschaften" beschrieben. Designer können den Wrapper verwenden, um das Vorhandensein einer Abhängigkeitseigenschaft zu erkennen. Genau wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Clients des Steuerelements auch, müssen diese beim Abrufen oder Festlegen der Eigenschaft jedoch nicht die Accessoren aufrufen.  
  
#### Angefügte Eigenschaften  
 Sie sollten angefügte Eigenschaften für benutzerdefinierte Steuerelemente anhand der folgenden Richtlinien implementieren:  
  
-   Verwenden Sie eine `public` `static` `readonly`\-<xref:System.Windows.DependencyProperty> der Form *Eigenschaftenname*`Property`, die mithilfe der <xref:System.Windows.DependencyProperty.RegisterAttached%2A>\-Methode erstellt wurde.  Der Eigenschaftenname, der an <xref:System.Windows.DependencyProperty.RegisterAttached%2A> übergeben wird, muss mit dem *PropertyName* übereinstimmen.  
  
-   Implementieren Sie ein `public``static`\-CLR\-Methodenpaar mit den Namen `Set`*PropertyName* und `Get`*PropertyName*.  Beide Methoden sollten eine von <xref:System.Windows.DependencyProperty> abgeleitete Klasse als erstes Argument akzeptieren.  Die `Set`*PropertyName*\-Methode akzeptiert auch ein Argument, dessen Typ zum registrierten Datentyp für die Eigenschaft passt.  Die `Get`*PropertyName*\-Methode sollte einen Wert des gleichen Typs zurückgeben.  Wenn die `Set`*Eigenschaftenname*\-Methode fehlt, wird die Eigenschaft als schreibgeschützt gekennzeichnet.  
  
-   `Set` *Eigenschaftsname* und `Get`*Eigenschaftsname* müssen direkt an die <xref:System.Windows.DependencyObject.GetValue%2A>\-Methode bzw. die <xref:System.Windows.DependencyObject.SetValue%2A>\-Methode im Zielabhängigkeitsobjekt weiterleiten.  Designer können auf die angefügte Eigenschaft zugreifen, indem sie einen Aufruf über den Methodenwrapper durchführen oder indem sie einen direkten Aufruf an das Zielabhängigkeitsobjekt ausführen.  
  
 Weitere Informationen zu angefügten Eigenschaften finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
### Definieren und Verwenden von freigegebenen Ressourcen  
 Sie können das Steuerelement in die Assembly der Anwendung oder in eine separate Assembly einbinden, die in mehreren Anwendungen verwendet werden kann.  Der Großteil der in diesem Thema erläuterten Informationen gelten unabhängig von der Methode, die Sie verwenden.  Sie müssen jedoch einen Unterschied beachten.  Wenn Sie ein Steuerelement in die Assembly einer Anwendung einbinden, können Sie der Datei App.xaml globale Ressourcen hinzufügen.  Einer Assembly, die nur Steuerelemente enthält, ist jedoch kein <xref:System.Windows.Application>\-Objekt zugeordnet, sodass keine App.xaml\-Datei verfügbar ist.  
  
 Wenn eine Anwendung nach einer Ressource sucht, erfolgt die Suche auf drei Ebenen in der folgenden Reihenfolge:  
  
1.  Die Elementebene.  
  
     Das System beginnt mit dem Element, das auf die Ressource verweist, darauf folgen die Ressourcen des logischen übergeordneten Elements usw., bis das Stammelement erreicht ist.  
  
2.  Die Anwendungsebene.  
  
     Mit dem <xref:System.Windows.Application>\-Objekt definierte Ressourcen.  
  
3.  Die Designebene.  
  
     Wörterbücher auf Designebene werden im Unterordner Themes gespeichert.  Die Dateien im Ordner Themes entsprechen den Designs.  Beispiel: Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml usw.  Der Ordner kann auch die Datei generic.xaml enthalten.  Die Suche nach einer Ressource auf Designebene erfolgt zunächst in der designspezifischen Datei und dann in der Datei generic.xaml.  
  
 Wenn sich das Steuerelement in einer separaten Assembly befindet, speichern Sie globale Ressourcen auf Element\- oder Designebene.  Beide Methoden haben ihre Vorteile.  
  
#### Definieren von Ressourcen auf Elementebene  
 Sie können freigegebene Ressourcen auf Elementebene definieren, indem Sie ein benutzerdefiniertes Ressourcenwörterbuch erstellen und mit dem Ressourcenwörterbuch des Steuerelements zusammenführen.  Bei dieser Methode können Sie der Ressourcendatei einen beliebigen Namen zuweisen und sie im gleichen Ordner speichern wie die Steuerelemente.  Für Ressourcen auf Elementebene können auch einfache Zeichenfolgen als Schlüssel verwendet werden.  Im folgenden Beispiel wird eine <xref:System.Windows.Media.LinearGradientBrush>\-Ressourcendatei mit dem Namen Dictionary1.xaml erstellt.  
  
 [!code-xml[SharedResources#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]  
  
 Nachdem Sie das Wörterbuch definiert haben, müssen Sie es mit dem Ressourcenwörterbuch des Steuerelements zusammenführen.  Hierzu können Sie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden.  
  
 Im folgenden Beispiel wird ein Ressourcenwörterbuch mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zusammengeführt.  
  
 [!code-xml[SharedResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]  
  
 Der Nachteil bei dieser Vorgehensweise besteht darin, dass jedes Mal, wenn Sie darauf verweisen, ein <xref:System.Windows.ResourceDictionary>\-Objekt erstellt wird.  Beispiel: Wenn Ihre Bibliothek zehn benutzerdefinierte Steuerelemente enthält und Sie die freigegebenen Ressourcenwörterbücher für jedes Steuerelement mit XAML zusammenführen, werden zehn identische <xref:System.Windows.ResourceDictionary>\-Objekte erstellt.  Sie können dies verhindern, indem Sie eine statische Klasse erstellen, die die Ressourcen in Code zusammenführt und das <xref:System.Windows.ResourceDictionary> ausgibt.  
  
 Im folgenden Beispiel wird eine Klasse erstellt, die ein freigegebenes <xref:System.Windows.ResourceDictionary> zurückgibt.  
  
 [!code-csharp[SharedResources#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]  
  
 Im folgenden Beispiel wird die freigegebene Ressource mit den Ressourcen eines benutzerdefinierten Steuerelements im Konstruktur des Steuerelements zusammengeführt, bevor `InitilizeComponent` aufgerufen wird.  Da das `SharedDictionaryManager.SharedDictionary` eine statische Eigenschaft ist, wird das <xref:System.Windows.ResourceDictionary> nur einmal erstellt.  Da das Ressourcenwörterbuch vor dem Aufruf von `InitializeComponent` zusammengeführt wurde, sind die Ressourcen für das Steuerelement in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei zugänglich.  
  
 [!code-csharp[SharedResources#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]  
  
#### Definieren von Ressourcen auf Designebene  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht Ihnen, Ressourcen für andere Windows\-Designs zu erstellen.  Als Steuerelementautor können Sie eine Ressource für ein bestimmtes Design definieren, um die Darstellung des Steuerelements an das jeweils verwendete Design anzupassen.  Beispiel: Die <xref:System.Windows.Controls.Button>\-Darstellung im Design Windows \- klassisch \(das Standardesign in Windows 2000\) unterscheidet sich von der <xref:System.Windows.Controls.Button>\-Darstellung im Windows XP\-Design, da für <xref:System.Windows.Controls.Button> für jedes Design eine andere <xref:System.Windows.Controls.ControlTemplate> verwendet wird.  
  
 Designspezifische Ressourcen werden in einem Ressourcenwörterbuch mit einem entsprechenden Dateinamen gespeichert.  Diese Dateien müssen sich im Verzeichnis `Themes` befinden, einem Unterverzeichnis des Ordners, der das Steuerelement enthält.  In der folgenden Tabelle werden die Ressourcenwörterbuchdateien und die den einzelnen Dateien zugeordneten Designs aufgeführt:  
  
|Name der Ressourcenwörterbuchdatei|Windows\-Design|  
|----------------------------------------|---------------------|  
|`Classic.xaml`|Klassische Windows 9x\/2000\-Darstellung unter Windows XP|  
|`Luna.NormalColor.xaml`|Blaues Design unter Windows XP \(Standard\)|  
|`Luna.Homestead.xaml`|Olivgrünes Design unter Windows XP|  
|`Luna.Metallic.xaml`|Silberdesign unter Windows XP|  
|`Royale.NormalColor.xaml`|Standarddesign von Windows XP Media Center Edition|  
|`Aero.NormalColor.xaml`|Standarddesign unter Windows Vista|  
  
 Sie müssen nicht für jedes Design eine Ressource definieren.  Wenn eine Ressource nicht für ein bestimmtes Design definiert ist, sucht das Steuerelement in `Classic.xaml` nach der Ressource.  Ist die Ressource nicht in der Datei für das aktuelle Design oder `Classic.xaml` definiert, verwendet das Steuerelement die generische Ressource, die in einer Ressourcenwörterbuchdatei mit dem Namen `generic.xaml` enthalten ist.  Die Datei `generic.xaml` befindet sich im gleichen Ordner wie die designspezifischen Ressourcenwörterbuchdateien.  Obwohl `generic.xaml` keinem bestimmten Windows\-Design entspricht, handelt es sich doch um ein Wörterbuch auf Designebene.  
  
 [Beispiel für benutzerdefiniertes NumericUpDown\-Steuerelement mit Unterstützung von Designs und Benutzeroberflächenautomatisierung](http://go.microsoft.com/fwlink/?LinkID=160025) enthält zwei Ressourcenwörterbücher für das `NumericUpDown`\-Steuerelement: eines in der Datei "generic.xaml" und eines in der Datei "Luna.NormalColor.xaml".  Führen Sie die Anwendung aus, und wechseln Sie zwischen dem Silberdesign für Windows XP und einem anderen Design, um den Unterschied zwischen den beiden Steuerelementvorlagen zu sehen.  \(Unter Windows Vista können Sie die Datei Luna.NormalColor.xaml in Aero.NormalColor.xaml umbenennen und zwischen zwei Designs wechseln, z. B. zwischen Windows \- klassisch und dem Standarddesign für Windows Vista.\)  
  
 Wenn Sie eine <xref:System.Windows.Controls.ControlTemplate> in eine der designspezifischen Ressourcenwörterbuchdateien einfügen, müssen Sie einen statischen Konstruktor für das Steuerelement erstellen und die <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29>\-Methode für den <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> aufrufen, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
 [!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]  
  
##### Definieren und Angeben von Schlüsseln für Designressourcen  
 Wenn Sie eine Ressource auf Elementebene definieren, können Sie ihr eine Zeichenfolge als Schlüssel zuweisen und über diese Zeichenfolge auf die Ressource zugreifen.  Wenn Sie auf Designebene eine Ressource definieren, müssen Sie einen <xref:System.Windows.ComponentResourceKey> als Schlüssel verwenden.  Im folgenden Beispiel wird eine Ressource in generic.xaml definiert.  
  
  
  
 Das folgende Beispiel verweist auf die Ressource, indem <xref:System.Windows.ComponentResourceKey> als Schlüssel angegeben wird.  
  
  
  
##### Angeben des Speicherorts von Designressourcen  
 Um die Ressourcen für ein Steuerelement finden zu können, muss die Hostanwendung über die Information verfügen, dass die Assembly steuerelementspezifische Ressourcen enthält.  Fügen Sie hierzu der Assembly, die das Steuerelement enthält, das <xref:System.Windows.ThemeInfoAttribute> hinzu.  Das <xref:System.Windows.ThemeInfoAttribute> weist eine <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A>\-Eigenschaft zur Angabe des Speicherorts allgemeiner Ressourcen sowie eine <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A>\-Eigenschaft zur Angabe des Speicherorts designspezifischer Ressourcen.  
  
 Im folgenden Beispiel werden die <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A>\-Eigenschaft und die <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A>\-Eigenschaft auf <xref:System.Windows.ResourceDictionaryLocation> gesetzt, um anzugeben, dass sich die allgemeinen und die designspezifischen Ressourcen in derselben Assembly befinden wie das Steuerelement.  
  
 [!code-csharp[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
 [!code-vb[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]  
  
## Siehe auch  
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Paket\-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)