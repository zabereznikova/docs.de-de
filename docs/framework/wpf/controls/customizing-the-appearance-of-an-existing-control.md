---
title: "Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate | Microsoft Docs"
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
  - "Steuerelementvertrag [WPF]"
  - "Steuerelemente [WPF], Nach Zustand angegebene Darstellung"
  - "Steuerelemente [WPF], Änderungen der visuellen Struktur"
  - "ControlTemplate [WPF], Anpassen an vorhandene Steuerelemente"
  - "Skins für Steuerelemente [WPF]"
  - "Vorlagen [WPF], Anpassen an vorhandene Steuerelemente"
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate
<a name="introduction"></a> Eine <xref:System.Windows.Controls.ControlTemplate> gibt die visuelle Struktur und das visuelle Verhalten eines Steuerelements an.  Sie können die Darstellung eines Steuerelements anpassen, indem Sie diesem eine neue <xref:System.Windows.Controls.ControlTemplate> zuweisen.  Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate> ersetzen Sie die Darstellung eines vorhandenen Steuerelements, ohne dessen Funktionalität zu ändern.  Beispielsweise können Sie festlegen, dass die Schaltflächen rund und nicht in der quadratischen Standardform angezeigt werden, mit den Schaltflächen wird jedoch trotzdem das jeweilige <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis ausgelöst.  
  
 In diesem Thema werden die verschiedenen Teile einer <xref:System.Windows.Controls.ControlTemplate> erklärt, das Erstellen einer einfachen <xref:System.Windows.Controls.ControlTemplate> für einen <xref:System.Windows.Controls.Button> wird veranschaulicht, und zudem wird erläutert, wie der Steuerelementvertrag eines Steuerelements interpretiert wird, sodass Sie dessen Darstellung anpassen können.  Da Sie eine <xref:System.Windows.Controls.ControlTemplate> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellen, können Sie die Darstellung eines Steuerelements ändern, ohne Code schreiben zu müssen.  Sie können einen Designer, z. B. Microsoft Expression Blend verwenden, um benutzerdefinierte Steuerelementvorlagen zu erstellen.  Dieses Thema zeigt Beispiele in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] an, die die Darstellung einer <xref:System.Windows.Controls.Button> anpassen. Am Ende des Themas wird das vollständige Beispiel aufgeführt.  Weitere Informationen zum Verwenden von Expression Blend finden Sie unter [Formatieren eines Steuerelements, das Vorlagen unterstützt](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
 Die folgenden Abbildungen zeigen eine <xref:System.Windows.Controls.Button>, die die <xref:System.Windows.Controls.ControlTemplate> verwendet, die in diesem Thema erstellt wird.  
  
 ![Schaltfläche mit einer benutzerdefinierten Steuerelementvorlage.](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP\_ButtonNormal")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 ![Schaltfläche mit einem roten Rahmen.](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP\_ButtonMouseOver")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet und auf der sich der Mauszeiger befindet  
  
   
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird davon ausgegangen, dass Sie wissen, wie Steuerelemente und Formate erstellt und verwendet werden, wie unter [Steuerelemente](../../../../docs/framework/wpf/controls/index.md) erläutert.  Die in diesem Thema erläuterten Begriffe gelten für Elemente, die von der <xref:System.Windows.Controls.UserControl>\-Klasse ergeben, mit Ausnahme von <xref:System.Windows.Controls.Control>.  Eine <xref:System.Windows.Controls.ControlTemplate> kann auf ein <xref:System.Windows.Controls.UserControl> nicht angewendet werden.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## Zeitpunkt zum Erstellen einer ControlTemplate  
 Steuerelemente besitzen zahlreiche Eigenschaften, z. B. <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, und <xref:System.Windows.Controls.Control.FontFamily%2A>, die Sie festlegen können, um andere Aspekte der Steuerelementdarstellung anzugeben, jedoch sind die Änderungen, die Sie durch Festlegen dieser Eigenschaften vornehmen können, beschränkt.  Zum Beispiel können Sie für eine <xref:System.Windows.Controls.CheckBox> die <xref:System.Windows.Controls.Control.Foreground%2A>\-Eigenschaft auf blau und <xref:System.Windows.Controls.Control.FontStyle%2A> auf kursiv festlegen.  
  
 Ohne die Möglichkeit, für Steuerelemente eine neue <xref:System.Windows.Controls.ControlTemplate> zu erstellen, würden alle Steuerelemente in jeder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierten Anwendung die gleiche allgemeine Darstellung aufweisen. Dies würde das Erstellen von Anwendungen mit benutzerdefiniertem Aussehen und Verhalten stark einschränken.  Standardmäßig besitzt jede <xref:System.Windows.Controls.CheckBox> ähnliche Merkmale.  Beispielsweise befindet sich der Inhalt der <xref:System.Windows.Controls.CheckBox> stets rechts vom Auswahlindikator, und das Häkchen wird immer für die Angabe verwendet, dass die <xref:System.Windows.Controls.CheckBox> aktiviert ist.  
  
 Eine <xref:System.Windows.Controls.ControlTemplate> erstellen Sie, wenn Sie die Darstellung des Steuerelements in einem Grad anpassen möchten, der über das Festlegen der anderen Steuerelementeigenschaften hinaus geht.  Im Beispiel mit der <xref:System.Windows.Controls.CheckBox> wird angenommen, dass der Inhalt des Kontrollkästchens über dem Auswahlindikator angezeigt werden soll, und mit einem X angegeben werden soll, dass die <xref:System.Windows.Controls.CheckBox> aktiviert ist.  Sie geben diese Änderungen in der <xref:System.Windows.Controls.ControlTemplate> des <xref:System.Windows.Controls.CheckBox> an.  
  
 Die folgende Abbildung zeigt ein <xref:System.Windows.Controls.CheckBox>, das eine Standard\- <xref:System.Windows.Controls.ControlTemplate> verwendet.  
  
 ![Kontrollkästchen mit der Standardsteuerelementvorlage.](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP\_CheckBoxDefault")  
Ein Kontrollkästchen, das die Standardsteuerelementvorlage verwendet  
  
 Die folgende Abbildung zeigt ein <xref:System.Windows.Controls.CheckBox>, das eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> verwendet, um den Inhalt des  <xref:System.Windows.Controls.CheckBox> über dem Auswahlindikator zu platzieren, und ein X anzeigt, wenn die <xref:System.Windows.Controls.CheckBox> ausgewählt wird.  
  
 ![Kontrollkästchen mit einer benutzerdefinierten Steuerelementvorlage.](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP\_CheckBoxCustom")  
Ein Kontrollkästchen, das eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 Die <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.CheckBox> in diesem Beispiel ist relativ komplex, deshalb wird in diesem Thema ein einfacheres Beispiel zum Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für einen <xref:System.Windows.Controls.Button> verwendet.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## Ändern der visuellen Struktur eines Steuerelements  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besteht ein Steuerelement häufig aus zusammengesetzten <xref:System.Windows.FrameworkElement>\-Objekten.  Wenn Sie eine <xref:System.Windows.Controls.ControlTemplate> erstellen, kombinieren Sie <xref:System.Windows.FrameworkElement>\-Objekte, um ein einzelnes Steuerelement zu erstellen.  Eine <xref:System.Windows.Controls.ControlTemplate> darf nur ein <xref:System.Windows.FrameworkElement> als Stammelement besitzen.  Das Stammelement enthält normalerweise weitere <xref:System.Windows.FrameworkElement>\-Objekte.  Die Kombination der Objekte bestimmt die visuelle Struktur des Steuerelements.  
  
 Im folgenden Beispiel wird eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> für den <xref:System.Windows.Controls.Button> erstellt.  Die <xref:System.Windows.Controls.ControlTemplate> bestimmt die visuelle Struktur des <xref:System.Windows.Controls.Button>.  In diesem Beispiel wird die Darstellung der Schaltfläche nicht geändert, wenn Sie den Mauszeiger darüber platzieren oder darauf klicken.  Das Ändern der Schaltflächendarstellung, wenn sich diese in einem anderen Zustand befindet, wird weiter unten in diesem Thema erläutert.  
  
 In diesem Beispiel besteht die visuelle Struktur aus den folgenden Teilen:  
  
-   Eine <xref:System.Windows.Controls.Border> mit dem Namen `RootElement`, die als Stamm\-<xref:System.Windows.FrameworkElement> der Vorlage verwendet wird.  
  
-   Ein <xref:System.Windows.Controls.Grid>, das dem `RootElement` untergeordnet ist.  
  
-   Ein <xref:System.Windows.Controls.ContentPresenter> für die Anzeige des Schaltflächeninhalts.  Der <xref:System.Windows.Controls.ContentPresenter> aktiviert einen beliebigen Objekttyp für die Anzeige.  
  
 [!code-xml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### Beibehalten der Funktionalität von Steuerelementeigenschaften mit TemplateBinding  
 Beim Erstellen einer neuen <xref:System.Windows.Controls.ControlTemplate> können Sie weiterhin die öffentlichen Eigenschaften verwenden, um die Darstellung des Steuerelements zu ändern.  Die [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)\-Markuperweiterung bindet eine Eigenschaft eines Elements in der <xref:System.Windows.Controls.ControlTemplate> an eine vom Steuerelement definierte öffentliche Eigenschaft.  Bei Verwendung von [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) können Eigenschaften des Steuerelements als Parameter der Vorlage fungieren.  Wenn eine Eigenschaft für ein Steuerelement festgelegt wird, wird dieser Wert somit an das Element übergeben, für das [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) angegeben ist.  
  
 Im folgenden  Beispiel wird der Teil des vorherigen Beispiels wiederholt, der die [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)\-Markuperweiterung verwendet, um Eigenschaften von Elementen in der <xref:System.Windows.Controls.ControlTemplate> an von der Schaltfläche definierte öffentliche Eigenschaften zu binden.  
  
 [!code-xml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 In diesem Beispiel ist die <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=fullName>\-Eigenschaftenvorlage für das <xref:System.Windows.Controls.Grid> an <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> gebunden.  Da <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=fullName> vorlagengebunden ist, können Sie mehrere Schaltflächen erstellen, die dieselbe <xref:System.Windows.Controls.ControlTemplate> verwenden, und den <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> für jede Schaltfläche auf einen anderen Wert festlegen.  Wenn <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> in der <xref:System.Windows.Controls.ControlTemplate> nicht an die Eigenschaft  eines Elements vorlagengebunden ist, hat das Festlegen des <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> einer Schaltfläche keine Auswirkungen auf die Darstellung der Schaltfläche.  
  
 Beachten Sie, dass die Namen der zwei Eigenschaften nicht identisch sein müssen.  Im vorherigen Beispiel ist die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=fullName>\-Eigenschaft der <xref:System.Windows.Controls.Button> an die  <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=fullName>\-Eigenschaft des  <xref:System.Windows.Controls.ContentPresenter> vorlagengebunden.  Dadurch kann der Inhalt der Schaltfläche horizontal positioniert werden.  <xref:System.Windows.Controls.ContentPresenter> verfügt nicht über eine Eigenschaft mit dem Namen `HorizontalContentAlignment`, aber <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=fullName> kann an <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=fullName> gebunden werden.  Wenn Sie eine Eigenschaft an eine Vorlage binden, stellen Sie sicher, dass die Ziel und Quelleigenschaften denselben Typ aufweisen.  
  
 Die <xref:System.Windows.Controls.Control>\-Klasse definiert eine Reihe von Eigenschaften, die von der Steuerelementvorlage verwendet werden müssen und Auswirkungen auf das Steuerelement haben, wenn sie festgelegt werden.  Die Verwendung der Eigenschaft durch die <xref:System.Windows.Controls.ControlTemplate> ist von der Eigenschaft abhängig.  Die <xref:System.Windows.Controls.ControlTemplate> muss die Eigenschaft auf eine der folgenden Weisen verwenden:  
  
-   Ein Element in der <xref:System.Windows.Controls.ControlTemplate>\-Vorlage ist an die Eigenschaft gebunden.  
  
-   Ein Element in der <xref:System.Windows.Controls.ControlTemplate> erbt die Eigenschaft von einem übergeordneten <xref:System.Windows.FrameworkElement>.  
  
 In der folgenden Tabelle sind die visuellen Eigenschaften aufgelistet, die ein Steuerelement von der <xref:System.Windows.Controls.Control>\-Klasse geerbt hat.  Sie gibt auch an, ob die standardmäßige Steuerelementvorlage eines Steuerelements den geerbten Eigenschaftswert verwendet oder ob es vorlagengebunden sein muss.  
  
|Eigenschaft|Verwendungsart|  
|-----------------|--------------------|  
|<xref:System.Windows.Controls.Control.Background%2A>|Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.FontFamily%2A>|Eigenschaftenvererbung oder Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.FontSize%2A>|Eigenschaftenvererbung oder Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.FontStretch%2A>|Eigenschaftenvererbung oder Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|Eigenschaftenvererbung oder Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.Foreground%2A>|Eigenschaftenvererbung oder Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.Padding%2A>|Vorlagenbindung|  
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|Vorlagenbindung|  
  
 In der Tabelle werden nur die von der <xref:System.Windows.Controls.Control>\-Klasse geerbten visuellen Eigenschaften aufgelistet.  Abgesehen von den in der Tabelle aufgelisteten Eigenschaften kann ein Steuerelement möglicherweise auch die Eigenschaften <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A> und <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> vom übergeordneten Frameworkelement erben.  
  
 Wenn sich zudem der <xref:System.Windows.Controls.ContentPresenter> in der <xref:System.Windows.Controls.ControlTemplate> eines <xref:System.Windows.Controls.ContentControl> befindet, wird der <xref:System.Windows.Controls.ContentPresenter> automatisch an die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>\-Eigenschaft und die <xref:System.Windows.Controls.ContentControl.Content%2A>\-Eigenschaft gebunden.  Entsprechend wird ein <xref:System.Windows.Controls.ItemsPresenter>, der sich in der <xref:System.Windows.Controls.ControlTemplate> eines <xref:System.Windows.Controls.ItemsControl> befindet, automatisch an die <xref:System.Windows.Controls.ItemsControl.Items%2A>\-Eigenschaft und die <xref:System.Windows.Controls.ItemsPresenter>\-Eigenschaft gebunden.  
  
 Im folgenden Beispiel werden zwei Schaltflächen erstellt, für die die im vorherigen Beispiel definierte <xref:System.Windows.Controls.ControlTemplate> verwendet wird.  Im folgenden Beispiel werden die Eigenschaften <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.FontSize%2A> für die einzelnen Schaltflächen festgelegt.  Das Festlegen der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft wirkt sich aus, da diese in der <xref:System.Windows.Controls.ControlTemplate> vorlagengebunden ist.  Obwohl die <xref:System.Windows.Controls.Control.Foreground%2A>\-Eigenschaft und die <xref:System.Windows.Controls.Control.FontSize%2A>\-Eigenschaft nicht vorlagengebunden sind, wirkt sich das Festlegen aus, da deren Werte geerbt werden.  
  
 [!code-xml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 Die Ausgabe im vorhergehenden Beispiel ähnelt der folgenden Abbildung.  
  
 ![Zwei Schaltflächen, eine blaue und eine violette.](../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP\_ButtonTwo")  
Zwei Schaltflächen mit unterschiedlichen Hintergrundfarben  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## Ändern der Darstellung eines Steuerelements in Abhängigkeit von dessen Zustand  
 Der Unterschied zwischen einer Schaltfläche in der Standarddarstellung und der Schaltfläche im vorherigen Beispiel besteht darin, dass die Standardschaltfläche je nach Zustand leicht geändert wird.  Zum Beispiel wird die Darstellung der Standardschaltfläche geändert, wenn auf die Schaltfläche geklickt wird oder sich der Mauszeiger über der Schaltfläche befindet.  Zwar wird mit der <xref:System.Windows.Controls.ControlTemplate> nicht die Funktionalität eines Steuerelements, aber das visuelle Verhalten des Steuerelements geändert.  Das visuelle Verhalten beschreibt die Darstellung eines Steuerelements in bestimmten Zuständen.  Zur Verdeutlichung des Unterschieds zwischen Funktionalität und visuellem Verhalten eines Steuerelements betrachten Sie das Schaltflächenbeispiel.  Die Funktionalität der Schaltfläche besteht im Auslösen des <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignisses, wenn auf sie geklickt wird. Das visuelle Verhalten der Schaltfläche hingegen besteht in der Änderung der Darstellung, wenn auf sie gezeigt oder geklickt wird.  
  
 Sie verwenden <xref:System.Windows.VisualState>\-Objekte, um die Darstellung eines Steuerelements anzugeben, wenn sich dieses in einem bestimmten Zustand befindet.  Ein <xref:System.Windows.VisualState> enthält ein <xref:System.Windows.Media.Animation.Storyboard>, das die Darstellung der Elemente in der <xref:System.Windows.Controls.ControlTemplate> ändert.  Sie müssen zu diesem Zweck keinen Code schreiben, da aufgrund der Logik des Steuerelements der Zustand über den <xref:System.Windows.VisualStateManager> geändert wird.  Wenn das Steuerelement in den von der <xref:System.Windows.VisualState.Name%2A?displayProperty=fullName>\-Eigenschaft angegebenen Zustand eintritt, wird das <xref:System.Windows.Media.Animation.Storyboard> gestartet.  Wenn das Steuerelement den Zustand verlässt, wird das <xref:System.Windows.Media.Animation.Storyboard> beendet.  
  
 Im folgenden Beispiel wird der <xref:System.Windows.VisualState> veranschaulicht, der die Darstellung einer <xref:System.Windows.Controls.Button> ändert, wenn sich die Mauszeiger darüber befindet.  Das <xref:System.Windows.Media.Animation.Storyboard> ändert die Rahmenfarbe der Schaltfläche durch Änderung der Farbe des `BorderBrush`.  Erinnern Sie sich an das Beispiel mit der <xref:System.Windows.Controls.ControlTemplate> am Anfang dieses Themas. `BorderBrush` ist der Name des <xref:System.Windows.Media.SolidColorBrush>, der dem <xref:System.Windows.Controls.Border.Background%2A> der <xref:System.Windows.Controls.Border> zugewiesen wurde.  
  
 [!code-xml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 Das Steuerelement ist für die Definition der Zustände als Teil des Steuerelementvertrags verantwortlich. Dies wird weiter unten in diesem Thema detailliert unter [Anpassen anderer Steuerelemente durch Kenntnisse des Steuerelementvertrags](#customizing_other_controls_by_understanding_the_control_contract) besprochen.  In der folgenden Tabelle werden die für <xref:System.Windows.Controls.Button> angegebenen Zustände aufgelistet.  
  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|-----------------------|----------------------------|------------------|  
|Normal|CommonStates|Der Standardzustand.|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Pressed|CommonStates|Das Steuerelement wird gedrückt.|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|Focused|FocusStates|Das Steuerelement besitzt den Fokus.|  
|Unfocused|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
  
 Die <xref:System.Windows.Controls.Button> definiert zwei Zustandsgruppen: die Gruppe `CommonStates` enthält die Zustände `Normal`, `MouseOver`, `Pressed` und `Disabled`.  Die Gruppe `FocusStates` enthält die Zustände `Focused` und `Unfocused`.  Zustände in derselben Zustandsgruppe schließen sich gegenseitig aus.  Das Steuerelement befindet sich immer in genau einem Zustand aus jeder Gruppe.  Zum Beispiel kann ein <xref:System.Windows.Controls.Button> den Fokus selbst dann besitzen, wenn sich der Mauszeiger nicht darüber befindet. Daher kann sich ein <xref:System.Windows.Controls.Button> im Zustand `Focused` im Zustand `MouseOver`, `Pressed` oder `Normal` befinden.  
  
 Sie fügen <xref:System.Windows.VisualState>\-Objekte <xref:System.Windows.VisualStateGroup>\-Objekten hinzu.  Sie fügen der angefügten <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName>\-Eigenschaft <xref:System.Windows.VisualStateGroup>\-Objekte hinzu.  Im folgenden Beispiel werden die <xref:System.Windows.VisualState>\-Objekte für die Zustände `Normal`, `MouseOver` und `Pressed` definiert, die jeweils der `CommonStates`\-Gruppe angehören.  Der <xref:System.Windows.VisualState.Name%2A> von jedem <xref:System.Windows.VisualState> stimmt mit dem Namen in der vorangehenden Tabelle überein.  Der Zustand `Disabled` sowie die Zustände in der `FocusStates`\-Gruppe werden ausgelassen, um das Beispiel kurz zu halten, im vollständigen Beispiel am Ende dieses Themas sind diese jedoch enthalten.  
  
> [!NOTE]
>  Die angefügte <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName>\-Eigenschaft muss für das Stamm\-<xref:System.Windows.FrameworkElement> der <xref:System.Windows.Controls.ControlTemplate> festgelegt werden.  
  
 [!code-xml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 Die Ausgabe im vorhergehenden Beispiel ähnelt den folgenden Abbildungen.  
  
 ![Schaltfläche mit einer benutzerdefinierten Steuerelementvorlage.](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP\_ButtonNormal")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage im normalen Zustand verwendet  
  
 ![Schaltfläche mit einem roten Rahmen.](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP\_ButtonMouseOver")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage im MouseOver\-Zustand verwendet  
  
 ![Der Rahmen ist bei Klicken auf Schaltfläche transparent.](../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP\_ButtonPressed")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage im gedrückten Zustand verwendet  
  
 Die visuellen Zustände für Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Steuerelementformate und \-vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## Angeben des Steuerelementverhaltens beim Wechsel zwischen Zuständen  
 Im vorausgehenden Beispiel ändert sich die Darstellung der Schaltfläche auch, wenn der Benutzer darauf klickt, jedoch sieht der Benutzer den Effekt nur, wenn die Schaltfläche eine volle Sekunde lang gedrückt wird.  Standardmäßig benötigt die Animation eine Sekunde, bevor sie sichtbar wird.  Da Benutzer wahrscheinlich in einer wesentlich kürzeren Zeit auf eine Schaltfläche klicken und diese wieder loslassen, wird das visuelle Feedback nicht sichtbar, wenn Sie die <xref:System.Windows.Controls.ControlTemplate> im Standardzustand belassen.  
  
 Sie können den Zeitraum angeben, den eine Animation für den Übergang eines Steuerelements von einem Zustand in einen anderen benötigt, indem Sie der <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.VisualTransition>\-Objekte hinzufügen.  Beim Erstellen einer <xref:System.Windows.VisualTransition> können Sie eines oder mehrere der folgenden Elemente angeben:  
  
-   Die Zeit für einen Wechsel zwischen Zuständen  
  
-   Zusätzliche Änderungen in der Darstellung des Steuerelements zur Zeit des Übergangs  
  
-   Die Zustände, auf die der <xref:System.Windows.VisualTransition> angewendet wird  
  
### Angeben der Dauer eines Übergangs  
 Sie können die Dauer eines Übergangs angeben, indem Sie die <xref:System.Windows.VisualTransition.GeneratedDuration%2A>\-Eigenschaft festlegen.  Das vorherige Beispiel hat einen <xref:System.Windows.VisualState>, der angibt, dass der Rahmen der Schaltfläche beim Klicken auf die Schaltfläche transparent wird. Die Animation dauert jedoch zu lang, um bemerkt zu werden, wenn schnell auf die Schaltfläche geklickt und wieder losgelassen wird.  Mit einer <xref:System.Windows.VisualTransition> können Sie die Zeitdauer angeben, die das Steuerelement für den Übergang in den gedrückten Zustand benötigt.  Im folgenden Beispiel wird angegeben, dass das Steuerelement für den Übergang in den gedrückten Zustand eine Hundertstelsekunde benötigt.  
  
 [!code-xml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### Angeben von Änderungen an der Steuerelementdarstellung während eines Übergangs  
 Der <xref:System.Windows.VisualTransition> enthält ein <xref:System.Windows.Media.Animation.Storyboard>, das gestartet wird, wenn das Steuerelement den Zustand wechselt.  Zum Beispiel können Sie angeben, dass eine bestimmte Animation ausgeführt wird, wenn das Steuerelement aus dem Zustand `MouseOver` in den Zustand `Normal` übergeht.  Im folgenden Beispiel wird ein <xref:System.Windows.VisualTransition> erstellt, der angibt, dass der Rahmen der Schaltfläche in 1,5 Sekunden von blau über gelb nach schwarz wechselt, wenn der Benutzer den Mauszeiger von der Schaltfläche weg bewegt.  
  
 [!code-xml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### Angeben, wann ein visueller Übergang angewendet wird  
 Die Anwendung eines <xref:System.Windows.VisualTransition> kann auf bestimmte Zustände beschränkt werden oder auch bei jedem Wechsel des Steuerelements zwischen Zuständen ausgeführt werden.  Im vorherigen Beispiel wird der <xref:System.Windows.VisualTransition> angewendet, wenn das Steuerelement aus dem Zustand `MouseOver` in den Zustand `Normal` wechselt. Im Beispiel davor wird der <xref:System.Windows.VisualTransition> angewendet, wenn das Steuerelement in den Zustand `Pressed` wechselt.  Die Anwendung eines <xref:System.Windows.VisualTransition> schränken Sie ein, indem Sie die <xref:System.Windows.VisualTransition.To%2A>\-Eigenschaft und die <xref:System.Windows.VisualTransition.From%2A>\-Eigenschaft festlegen.  In der folgenden Tabelle werden die Beschränkungsebenen von der restriktivsten bis zur am wenigsten restriktiven beschrieben.  
  
|Beschränkungstyp|From\-Wert|To\-Wert|  
|----------------------|----------------|--------------|  
|Aus einem angegebenen Zustand in einen anderen angegebenen Zustand|Der Name eines <xref:System.Windows.VisualState>.|Der Name eines <xref:System.Windows.VisualState>.|  
|Aus einem beliebigen Zustand in einen angegebenen Zustand|Nicht festgelegt|Der Name eines <xref:System.Windows.VisualState>.|  
|Aus einem angegebenen Zustand in einen beliebigen Zustand|Der Name eines <xref:System.Windows.VisualState>.|Nicht festgelegt|  
|Aus einem beliebigen Zustand in einen beliebigen anderen Zustand|Nicht festgelegt|Nicht festgelegt|  
  
 Mehrere <xref:System.Windows.VisualTransition>\-Objekte in einer <xref:System.Windows.VisualStateGroup> können auf denselben Zustand verweisen, doch werden diese in der Reihenfolge verwendet, die in der vorherigen Tabelle angegeben ist.  Im folgenden Beispiel sind zwei <xref:System.Windows.VisualTransition>\-Objekte vorhanden.  Wenn das Steuerelement aus dem Zustand `Pressed` in den Zustand `MouseOver` übergeht, wird die <xref:System.Windows.VisualTransition> verwendet, für die <xref:System.Windows.VisualTransition.From%2A> und <xref:System.Windows.VisualTransition.To%2A> festgelegt sind.  Wenn das Steuerelement aus einem anderen Zustand als `Pressed` in den Zustand `MouseOver` übergeht, wird der andere Zustand verwendet.  
  
 [!code-xml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 Die <xref:System.Windows.VisualStateGroup> besitzt eine <xref:System.Windows.VisualStateGroup.Transitions%2A>\-Eigenschaft, die die <xref:System.Windows.VisualTransition>\-Objekte enthält, die auf die <xref:System.Windows.VisualState>\-Objekte in der <xref:System.Windows.VisualStateGroup> angewendet werden.  Als Autor der <xref:System.Windows.Controls.ControlTemplate> können Sie eine beliebige <xref:System.Windows.VisualTransition> einfügen.  Wenn die <xref:System.Windows.VisualTransition.To%2A>\-Eigenschaft und die <xref:System.Windows.VisualTransition.From%2A>\-Eigenschaft jedoch auf Zustandsnamen festgelegt sind, die in der <xref:System.Windows.VisualStateGroup> nicht enthalten sind, wird die <xref:System.Windows.VisualTransition> ignoriert.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.VisualStateGroup> für die `CommonStates` veranschaulicht.  Im Beispiel wird eine <xref:System.Windows.VisualTransition> für jeden der folgenden Übergänge der Schaltfläche definiert.  
  
-   In den Zustand `Pressed`.  
  
-   In den Zustand `MouseOver`.  
  
-   Aus dem Zustand `Pressed` in den Zustand `MouseOver`.  
  
-   Aus dem Zustand `MouseOver` in den Zustand `Normal`.  
  
 [!code-xml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## Anpassen anderer Steuerelemente durch Kenntnisse des Steuerelementvertrags  
 Für ein Steuerelement, dessen visuelle Struktur \(über <xref:System.Windows.FrameworkElement>\-Objekte\) und visuelles Verhalten \(über <xref:System.Windows.VisualState>\-Objekte\) in einer <xref:System.Windows.Controls.ControlTemplate> angegeben werden, wird das Parts\-Steuerelementmodell verwendet.  Viele der Steuerelemente, die in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 enthalten sind, verwenden dieses Modell.  Die Teile, auf die <xref:System.Windows.Controls.ControlTemplate>\-Autoren achten müssen, sind im Steuerelementvertrag aufgeführt.  Wenn Sie mit den Teilen eines Steuerelementvertrags vertraut sind, können Sie die Darstellung jedes Steuerelements anpassen, für das das Parts\-Steuerelementmodell verwendet wird.  
  
 Ein Steuerelementvertrag besteht aus drei Elementen:  
  
-   Den von der Logik des Steuerelements verwendeten visuellen Elementen  
  
-   Den Zuständen des Steuerelements und den Gruppen, zu denen die einzelnen Zustände gehören  
  
-   Die öffentlichen Eigenschaften, die sich auf das Steuerelement visuell auswirken  
  
### Visuelle Elemente im Steuerelementvertrag  
 In manchen Fällen interagiert die Logik eines Steuerelements mit einem <xref:System.Windows.FrameworkElement> in der <xref:System.Windows.Controls.ControlTemplate>.  Zum Beispiel kann das Steuerelement ein Ereignis für eines der zugehörigen Elemente behandeln.  Wenn ein Steuerelement in der <xref:System.Windows.Controls.ControlTemplate> ein bestimmtes <xref:System.Windows.FrameworkElement> erwartet, muss es diese Informationen an den <xref:System.Windows.Controls.ControlTemplate>\-Autor leiten.  Das Steuerelement übermittelt den erwarteten Elementtyp und den geforderten Elementnamen über das <xref:System.Windows.TemplatePartAttribute>.  Im Steuerelementvertrag sind für den <xref:System.Windows.Controls.Button> keine <xref:System.Windows.FrameworkElement>\-Teile vorhanden, jedoch für andere Steuerelemente, beispielsweise die <xref:System.Windows.Controls.ComboBox>.  
  
 Im folgenden Beispiel werden die für die <xref:System.Windows.Controls.ComboBox>\-Klasse angegebenen <xref:System.Windows.TemplatePartAttribute>\-Objekte veranschaulicht.  Die Logik von <xref:System.Windows.Controls.ComboBox> erwartet in der <xref:System.Windows.Controls.ControlTemplate> das <xref:System.Windows.Controls.TextBox> mit dem Namen `PART_EditableTextBox` und den <xref:System.Windows.Controls.Primitives.Popup> mit dem Namen `PART_Popup`.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 Im folgenden Beispiel wird eine vereinfachte <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ComboBox> veranschaulicht, die die von den <xref:System.Windows.TemplatePartAttribute>\-Objekten für die <xref:System.Windows.Controls.ComboBox>\-Klasse angegebenen Elemente enthält.  
  
 [!code-xml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### Zustände im Steuerelementvertrag  
 Die Zustände eines Steuerelements sind ebenfalls Teil des Steuerelementvertrags.  Im Beispiel zum Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für einen <xref:System.Windows.Controls.Button> wird gezeigt, wie die Darstellung eines <xref:System.Windows.Controls.Button> in Abhängigkeit von dessen Zuständen angegeben wird.  Sie erstellen einen <xref:System.Windows.VisualState> für jeden angegebenen Zustand und haben alle <xref:System.Windows.VisualState>\-Objekte gesetzt, für die ein <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> in einem <xref:System.Windows.VisualStateGroup> freigegeben ist, wie unter [Ändern der Darstellung eines Steuerelements in Abhängigkeit von dessen Zustand](#changing_the_appearance_of_a_control_depending_on_its_state) weiter oben in diesem Thema beschrieben.  Steuerelemente von Drittanbietern sollten Zustände festlegen, indem sie <xref:System.Windows.TemplateVisualStateAttribute>verwenden, die Designertools, z. B. Expression Blend die Zustände des Steuerelements zum Erstellen von Steuerelementvorlagen verfügbar zu machen.  
  
 Den Steuerelementvertrag für Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Steuerelementformate und \-vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
### Eigenschaften im Steuerelementvertrag  
 Die öffentlichen Eigenschaften, die sich auf das Steuerelement visuell auswirken, sind ebenfalls im Steuerelementvertrag enthalten.  Diese Eigenschaften können Sie festlegen, um die Darstellung des Steuerelements zu ändern, ohne eine neue <xref:System.Windows.Controls.ControlTemplate> erstellen zu müssen.  Sie können auch die [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)\-Markuperweiterung verwenden, um Eigenschaften von Elementen in der <xref:System.Windows.Controls.ControlTemplate> an öffentliche Eigenschaften zu binden, die vom <xref:System.Windows.Controls.Button> definiert werden.  
  
 Das folgende Beispiel zeigt den Steuerelementvertrag für die Schaltfläche.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate> ist es oft am einfachsten, mit einer vorhandenen <xref:System.Windows.Controls.ControlTemplate> zu beginnen und an dieser Änderungen vorzunehmen.  Zum Ändern einer vorhandenen <xref:System.Windows.Controls.ControlTemplate> können Sie wie folgt vorgehen:  
  
-   Verwenden Sie einen Designer, z. B. Expression Blend, der eine grafische Benutzeroberfläche zum Erstellen von Steuerelementvorlagen bereitstellt.  Weitere Informationen finden Sie unter [Formatieren eines Steuerelements, das Vorlagen unterstützt](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
-   Rufen Sie die Standard\-<xref:System.Windows.Controls.ControlTemplate> ab, und bearbeiten Sie diese.  Die standardmäßigen Steuerelementvorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Standard\-WPF\-Designs](http://go.microsoft.com/fwlink/?LinkID=158252) \(möglicherweise in englischer Sprache\).  
  
<a name="complete_example"></a>   
## Vollständiges Beispiel  
 Im folgenden Beispiel wird die vollständige <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.ControlTemplate> dargestellt, die in diesem Thema erläutert wird.  
  
 [!code-xml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)