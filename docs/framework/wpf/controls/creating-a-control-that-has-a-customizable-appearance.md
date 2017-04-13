---
title: "Erstellen eines Steuerelements mit einer anpassbaren Darstellung | Microsoft Docs"
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
  - "Steuerelemente [WPF], Anpassen"
  - "Steuerelemente [WPF], Definieren der visuellen Struktur und des Verhaltens von"
  - "ControlTemplate [WPF], Anpassen der Darstellung"
  - "Anpassen der Darstellung [WPF], ControlTemplate"
  - "Verwalten der Steuerelementzustände [WPF], VisualStateManager"
  - "VisualStateManager [WPF], Empfohlene Vorgehensweise"
  - "VisualStateManager [WPF], Verwalten eines Steuerelementzustands"
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Erstellen eines Steuerelements mit einer anpassbaren Darstellung
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ermöglicht es Ihnen, ein Steuerelement zu erstellen, dessen Darstellung angepasst werden kann.  Beispielsweise können Sie die Darstellung einer <xref:System.Windows.Controls.CheckBox> weitgehender ändern, als es durch das Festlegen von Eigenschaften möglich ist, indem Sie eine neue <xref:System.Windows.Controls.ControlTemplate> erstellen.  Die folgende Abbildung zeigt ein <xref:System.Windows.Controls.CheckBox> an, das eine Standard\-<xref:System.Windows.Controls.ControlTemplate> verwendet, und ein <xref:System.Windows.Controls.CheckBox>, das eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> verwenden.  
  
 ![Kontrollkästchen mit der Standardsteuerelementvorlage.](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP\_CheckBoxDefault")  
Ein Kontrollkästchen, das die Standardsteuerelementvorlage verwendet  
  
 ![Kontrollkästchen mit einer benutzerdefinierten Steuerelementvorlage.](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP\_CheckBoxCustom")  
Ein Kontrollkästchen, das eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 Wenn Sie beim Erstellen eines Steuerelements das Modell für Teile und Zustände berücksichtigen, kann die Darstellung des Steuerelements angepasst werden.  Designertools wie Microsoft Expression Blend unterstützen das Modell für Teile und Zustände. Wenn Sie also diesem Modell folgen, ist das Steuerelement in den entsprechenden Anwendungstypen vom Benutzer anpassbar.  In diesem Thema wird das Modell für Teile und Zustände erläutert und wie Sie dieses beim Erstellen eines eigenen Steuerelements berücksichtigen.  Die Philosophie dieses Modells wird in diesem Thema anhand des Beispiels eines benutzerdefinierten Steuerelements, `NumericUpDown`, veranschaulicht.  Das `NumericUpDown`\-Steuerelement zeigt einen numerischen Wert an, den ein Benutzer erhöhen oder verringern kann, indem er auf die Schaltflächen des Steuerelements klickt.  Die folgende Abbildung zeigt das `NumericUpDown`\-Steuerelement, das in diesem Thema erläutert wird.  
  
 ![Benutzerdefiniertes NumericUpDown&#45;Steuerelement.](../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP\_NumericUPDown")  
Ein benutzerdefiniertes NumericUpDown\-Steuerelement.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Vorbereitungsmaßnahmen](#prerequisites)  
  
-   [Modell für Teile und Zustände](#parts_and_states_model)  
  
-   [Definieren der visuellen Struktur und des visuellen Verhaltens eines Steuerelements in einer ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [Verwenden von Teilen der ControlTemplate in Code](#using_parts_of_the_controltemplate_in_code)  
  
-   [Bereitstellen des Steuerelementvertrags](#providing_the_control_contract)  
  
-   [Vollständiges Beispiel](#complete_example)  
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird davon ausgegangen, dass Sie wissen, wie eine neue <xref:System.Windows.Controls.ControlTemplate> für ein vorhandenes Steuerelement erstellt wird, und mit den Elementen eines Steuerelementvertrags und den in [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) erläuterten Begriffen vertraut sind.  
  
> [!NOTE]
>  Um ein Steuerelement zu erstellen, dessen Darstellung angepasst werden kann, müssen Sie ein Steuerelement erstellen, das von der <xref:System.Windows.Controls.Control>\-Klasse oder einer ihrer Unterklassen \(außer <xref:System.Windows.Controls.UserControl>\) erbt.  Ein Steuerelement, das von <xref:System.Windows.Controls.UserControl> erbt, kann zwar schnell erstellt werden, verwendet aber keine <xref:System.Windows.Controls.ControlTemplate>, und Sie können seine Darstellung nicht anpassen.  
  
<a name="parts_and_states_model"></a>   
## Modell für Teile und Zustände  
 Das Modell für Teile und Zustände gibt an, wie die visuelle Struktur und das visuelle Verhalten eines Steuerelements definiert werden.  Um dem Modell für Teile und Zustände zu folgen, gehen Sie wie folgt vor:  
  
-   Definieren Sie die visuelle Struktur und das visuelle Verhalten in der <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements.  
  
-   Verwenden Sie bestimmte bewährte Methoden, um zu steuern, wie die Logik des Steuerelements mit Teilen der Steuerelementvorlage interagiert.  
  
-   Stellen Sie einen Steuerelementvertrag bereit, um anzugeben, was die <xref:System.Windows.Controls.ControlTemplate> enthalten soll.  
  
 Wenn Sie die visuelle Struktur und das visuelle Verhalten in der <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements definieren, können Anwendungsentwickler die visuelle Struktur und das visuelle Verhalten des Steuerelements ändern, indem sie eine neue <xref:System.Windows.Controls.ControlTemplate> erstellen, statt Code zu schreiben.  Sie müssen einen Steuerelementvertrag bereitstellen, um die Anwendungsentwickler darüber zu informieren, welche <xref:System.Windows.FrameworkElement>\-Objekte und Zustände in der <xref:System.Windows.Controls.ControlTemplate> definiert werden sollen.  Verwenden Sie für die Interaktion mit den Teilen in der <xref:System.Windows.Controls.ControlTemplate> einige bewährte Methoden, sodass das Steuerelement eine unvollständige <xref:System.Windows.Controls.ControlTemplate> ordnungsgemäß behandelt.  Wenn Sie sich an diese drei Prinzipien halten, können Anwendungsentwickler eine <xref:System.Windows.Controls.ControlTemplate> für Ihr Steuerelement ebenso leicht wie für die in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthaltenen Steuerelemente erstellen.  Im folgenden Abschnitt werden diese Empfehlungen ausführlich erläutert.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## Definieren der visuellen Struktur und des visuellen Verhaltens eines Steuerelements in einer ControlTemplate  
 Wenn Sie das benutzerdefinierte Steuerelement anhand des Modells für Teile und Zustände erstellen, definieren Sie die visuelle Struktur und das visuelle Verhalten des Steuerelements nicht in der zugehörigen Logik, sondern in der <xref:System.Windows.Controls.ControlTemplate>.  Die visuelle Struktur eines Steuerelements ist die Zusammensetzung der <xref:System.Windows.FrameworkElement>\-Objekte, aus denen das Steuerelement besteht.  Das visuelle Verhalten ist die Art, wie das Steuerelement in bestimmten Zuständen dargestellt wird.  Weitere Informationen über das Erstellen einer <xref:System.Windows.Controls.ControlTemplate>, die die visuelle Struktur und das visuelle Verhalten eines Steuerelements angibt, finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
 Im Beispiel für das `NumericUpDown`\-Steuerelement schließt die visuelle Struktur zwei <xref:System.Windows.Controls.Primitives.RepeatButton>\-Steuerelemente und einen <xref:System.Windows.Controls.TextBlock> ein.  Wenn Sie diese Steuerelemente im Code des `NumericUpDown`\-Steuerelements hinzufügen, z. B. im Konstruktor, sind die Positionen der betreffenden Steuerelemente unveränderlich.  Sie sollten die visuelle Struktur und das visuelle Verhalten des Steuerelements nicht im Code, sondern in der <xref:System.Windows.Controls.ControlTemplate> definieren.  Dann kann ein Anwendungsentwickler die Position der Schaltflächen und von <xref:System.Windows.Controls.TextBlock> anpassen sowie das Verhalten für den Fall angeben, dass `Value` negativ ist, weil die <xref:System.Windows.Controls.ControlTemplate> ersetzt werden kann.  
  
 Im folgenden Beispiel wird die visuelle Struktur des `NumericUpDown`\-Steuerelements veranschaulicht, die einen <xref:System.Windows.Controls.Primitives.RepeatButton> zum Erhöhen von `Value`, einen <xref:System.Windows.Controls.Primitives.RepeatButton> zum Verringern von `Value` und einen <xref:System.Windows.Controls.TextBlock> zum Anzeigen von `Value` enthält.  
  
 [!code-xml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 Ein visuelles Verhalten des `NumericUpDown`\-Steuerelements besteht darin, dass ein negativer Wert in roter Schrift angezeigt wird.  Wenn Sie den <xref:System.Windows.Controls.TextBlock.Foreground%2A> des <xref:System.Windows.Controls.TextBlock> im Code ändern, wenn der `Value` negativ ist, zeigt `NumericUpDown` immer einen roten negativen Wert an.  Sie geben das visuelle Verhalten des Steuerelements in der <xref:System.Windows.Controls.ControlTemplate> an, indem Sie der <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.VisualState>\-Objekte hinzufügen.  Das folgende Beispiel zeigt die <xref:System.Windows.VisualState>\-Objekte für die Zustände  `Positive` und `Negative`.  `Positive` und `Negative` schließen sich gegenseitig aus \(das Steuerelement weist immer nur einen der beiden Zustände auf\). Daher befinden sich die <xref:System.Windows.VisualState>\-Objekte im Beispiel in einer einzelnen <xref:System.Windows.VisualStateGroup>.  Wenn das Steuerelement in den `Negative`\-Zustand wechselt, wird der <xref:System.Windows.Controls.TextBlock.Foreground%2A> des <xref:System.Windows.Controls.TextBlock> rot.  Wenn das Steuerelement den `Positive`\-Zustand aufweist, wechselt der <xref:System.Windows.Controls.TextBlock.Foreground%2A> wieder zum ursprünglichen Wert zurück.  Das Definieren von <xref:System.Windows.VisualState>\-Objekten in einer <xref:System.Windows.Controls.ControlTemplate> wird in [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) weiter erläutert.  
  
> [!NOTE]
>  Die angefügte <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName>\-Eigenschaft muss für das Stamm\-<xref:System.Windows.FrameworkElement> der <xref:System.Windows.Controls.ControlTemplate> festgelegt werden.  
  
 [!code-xml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## Verwenden von Teilen der ControlTemplate in Code  
 Ein Entwickler einer <xref:System.Windows.Controls.ControlTemplate> lässt u. U. <xref:System.Windows.FrameworkElement>\-Objekte oder <xref:System.Windows.VisualState>\-Objekte absichtlich oder irrtümlich weg. Möglicherweise benötigt die Logik Ihres Steuerelements diese Teile aber, um ordnungsgemäß zu funktionieren.  Das Modell für Teile und Zustände gibt an, dass das Steuerelement flexibel auf eine <xref:System.Windows.Controls.ControlTemplate> reagiert, in der <xref:System.Windows.FrameworkElement>\-Objekte oder <xref:System.Windows.VisualState>\-Objekte fehlen.  Das Steuerelement sollte keine Ausnahme auslösen oder einen Fehler melden, wenn ein <xref:System.Windows.FrameworkElement>, ein <xref:System.Windows.VisualState> oder eine <xref:System.Windows.VisualStateGroup> in der <xref:System.Windows.Controls.ControlTemplate> fehlt.  In diesem Abschnitt werden die empfohlenen Vorgehensweisen zum Interagieren mit <xref:System.Windows.FrameworkElement>\-Objekten und zum Verwalten von Zuständen beschrieben.  
  
### Vorhersehen von fehlenden FrameworkElement\-Objekten  
 Wenn Sie <xref:System.Windows.FrameworkElement>\-Objekte in der <xref:System.Windows.Controls.ControlTemplate> definieren, muss die Logik Ihres Steuerelements möglicherweise mit einigen dieser Objekte interagieren.  Beispielsweise abonniert das `NumericUpDown`\-Steuerelement das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis der Schaltflächen zum Erhöhen oder Verringern von `Value` und legt die <xref:System.Windows.Controls.TextBlock.Text%2A>\-Eigenschaft des <xref:System.Windows.Controls.TextBlock> auf `Value` fest.  Wenn in einer benutzerdefinierten <xref:System.Windows.Controls.ControlTemplate> der <xref:System.Windows.Controls.TextBlock> oder die Schaltflächen fehlen, ist ein gewisser Funktionsverlust beim Steuerelement akzeptabel. Sie sollten sich aber vergewissern, dass das Steuerelement keine Fehler auslöst.  Wenn eine <xref:System.Windows.Controls.ControlTemplate> z. B. nicht die Schaltflächen zum Ändern von `Value` enthält, geht diese Funktion bei `NumericUpDown` verloren. Dennoch wird eine Anwendung, die die <xref:System.Windows.Controls.ControlTemplate> verwendet, weiterhin ausgeführt.  
  
 Mit den folgenden Methoden wird sichergestellt, dass das Steuerelement angemessen auf das Fehlen von <xref:System.Windows.FrameworkElement>\-Objekten reagiert:  
  
1.  Legen Sie das `x:Name`\-Attribut für jedes <xref:System.Windows.FrameworkElement> fest, auf das Sie im Code verweisen müssen.  
  
2.  Definieren Sie private Eigenschaften für jedes <xref:System.Windows.FrameworkElement>, mit dem interagiert werden muss.  
  
3.  Abonnieren und kündigen Sie alle Ereignisse, die das Steuerelement im set\-Accessor der <xref:System.Windows.FrameworkElement>\-Eigenschaft behandelt.  
  
4.  Legen Sie die <xref:System.Windows.FrameworkElement>\-Eigenschaften fest, die Sie in Schritt 2 der <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>\-Methode definiert haben.  Dies ist der früheste Zeitpunkt, zu dem das <xref:System.Windows.FrameworkElement> in der <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement verfügbar ist.  Verwenden Sie den `x:Name` des <xref:System.Windows.FrameworkElement>, um es von der <xref:System.Windows.Controls.ControlTemplate> abzurufen.  
  
5.  Stellen Sie sicher, dass das <xref:System.Windows.FrameworkElement> nicht `null` ist, bevor auf die entsprechenden Member zugegriffen wird.  Wenn der Wert `null` ist, melden Sie keinen Fehler.  
  
 In den folgenden Beispielen wird gezeigt, wie das `NumericUpDown`\-Steuerelement in Übereinstimmung mit den Empfehlungen in der vorangehenden Liste mit <xref:System.Windows.FrameworkElement>\-Objekten interagiert.  
  
 In dem Beispiel, in dem die visuelle Struktur des `NumericUpDown`\-Steuerelements in der <xref:System.Windows.Controls.ControlTemplate> definiert ist, ist das `x:Name`\-Attribut des <xref:System.Windows.Controls.Primitives.RepeatButton>, mit dem `Value` erhöht wird, auf `UpButton` festgelegt.  Im folgenden Beispiel wird eine Eigenschaft mit dem Namen `UpButtonElement` deklariert, die den <xref:System.Windows.Controls.Primitives.RepeatButton> darstellt, der in der <xref:System.Windows.Controls.ControlTemplate> deklariert wird.  Der `set`\-Accessor kündig zunächst das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis der Schaltfläche, wenn `UpDownElement` nicht `null` ist, legt dann die Eigenschaft fest und abonniert anschließend das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis.  Auch für die andere <xref:System.Windows.Controls.Primitives.RepeatButton> mit der Bezeichnung `DownButtonElement` wird eine Eigenschaft definiert, die aber nicht hier gezeigt wird.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> für das `NumericUpDown`\-Steuerelement.  Im Beispiel wird die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>\-Methode verwendet, um die <xref:System.Windows.FrameworkElement>\-Objekte aus der <xref:System.Windows.Controls.ControlTemplate> abzurufen.  Beachten Sie, dass das Beispiel Vorkehrungen für den Fall aufweist, dass <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> ein <xref:System.Windows.FrameworkElement> mit dem angegebenen Namen findet, das nicht vom erwarteten Typ ist.  Es ist auch eine bewährte Methode, Elemente zu ignorieren, die zwar den angegebenen `x:Name` haben, aber vom falschen Typ sind.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Wenn Sie sich an die in den vorangegangenen Beispielen gezeigten Methoden halten, stellen Sie sicher, dass das Steuerelement weiterhin ausgeführt wird, wenn in der <xref:System.Windows.Controls.ControlTemplate> ein <xref:System.Windows.FrameworkElement> fehlt.  
  
### Verwenden von VisualStateManager zum Verwalten von Zuständen  
 Der <xref:System.Windows.VisualStateManager> verfolgt die Zustände eines Steuerelements und führt die zum Wechseln zwischen Zuständen erforderliche Logik aus.  Beim Hinzufügen von <xref:System.Windows.VisualState>\-Objekten zur <xref:System.Windows.Controls.ControlTemplate> fügen Sie die Objekte einer <xref:System.Windows.VisualStateGroup> hinzu und fügen der angefügten <xref:System.Windows.VisualStateManager.VisualStateGroups%2A>\-Eigenschaft die <xref:System.Windows.VisualStateGroup?displayProperty=fullName>\-Eigenschaft hinzu, sodass der <xref:System.Windows.VisualStateManager> auf diese zugreifen kann.  
  
 Das folgende Beispiel ist eine Wiederholung des vorherigen Beispiels, in dem die <xref:System.Windows.VisualState>\-Objekte veranschaulicht werden, die dem `Positive`\-Zustand und dem `Negative`\-Zustand des Steuerelements entsprechen.  Das <xref:System.Windows.Media.Animation.Storyboard> im `Negative` <xref:System.Windows.VisualState> zeigt den <xref:System.Windows.Controls.TextBlock.Foreground%2A> des <xref:System.Windows.Controls.TextBlock> rot an.  Wenn das `NumericUpDown`\-Steuerelement den Zustand `Negative` aufweist, beginnt das Storyboard im Zustand `Negative`.  Das <xref:System.Windows.Media.Animation.Storyboard> im Zustand `Negative` wird beendet, wenn das Steuerelement wieder in den Zustand `Positive` wechselt.  Der <xref:System.Windows.VisualState> `Positive` muss kein <xref:System.Windows.Media.Animation.Storyboard> enthalten. Wenn das <xref:System.Windows.Media.Animation.Storyboard> für `Negative` beendet wird, wird der <xref:System.Windows.Controls.TextBlock.Foreground%2A> wieder in der ursprünglichen Farbe angezeigt.  
  
 [!code-xml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 Beachten Sie, dass dem <xref:System.Windows.Controls.TextBlock> ein Name gegeben wird, sich der <xref:System.Windows.Controls.TextBlock> aber nicht im Steuerelementvertrag für  `NumericUpDown` befindet, da die Logik des Steuerelements nie auf den <xref:System.Windows.Controls.TextBlock> verweist.  Elemente, auf die in der <xref:System.Windows.Controls.ControlTemplate> verwiesen wird, verfügen über Namen, müssen aber nicht Bestandteil des Steuerelementvertrags sein, da eine neue <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement unter Umständen nicht auf dieses Element verweisen muss.  Jemand, der eine neue <xref:System.Windows.Controls.ControlTemplate> für `NumericUpDown` erstellt, könnte z. B. entscheiden nicht anzugeben, dass `Value` negativ ist, indem er den <xref:System.Windows.Controls.Control.Foreground%2A> ändert.  In diesem Fall verweist weder der Code noch die <xref:System.Windows.Controls.ControlTemplate> mit Namen auf den <xref:System.Windows.Controls.TextBlock>.  
  
 Die Logik des Steuerelements ist verantwortlich dafür, den Zustand des Steuerelements zu ändern.  Das folgende Beispiel zeigt, dass das `NumericUpDown`\-Steuerelement die <xref:System.Windows.VisualStateManager.GoToState%2A>\-Methode aufruft, um in den Zustand `Positive` zu wechseln, wenn `Value` gleich oder größer 0 ist, und in den Zustand `Negative`, wenn `Value` kleiner 0 ist.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 Die <xref:System.Windows.VisualStateManager.GoToState%2A>\-Methode führt die Logik aus, die jeweils zum Starten bzw. Beenden des Storyboards erforderlich ist.  Wenn ein Steuerelement <xref:System.Windows.VisualStateManager.GoToState%2A> aufruft, um seinen Zustand zu ändern, geht der <xref:System.Windows.VisualStateManager> wie folgt vor:  
  
-   Wenn der <xref:System.Windows.VisualState>, in den das Steuerelement wechselt, ein <xref:System.Windows.Media.Animation.Storyboard> aufweist, beginnt das Storyboard.  Wenn dann der <xref:System.Windows.VisualState>, aus dem das Steuerelement stammt, über ein <xref:System.Windows.Media.Animation.Storyboard> verfügt, wird das Storyboard beendet.  
  
-   Wenn das Steuerelement bereits im angegebenen Zustand ist, führt <xref:System.Windows.VisualStateManager.GoToState%2A> keine Aktion aus und gibt `true` zurück.  
  
-   Wenn der angegebene Zustand in der <xref:System.Windows.Controls.ControlTemplate> von `control` nicht vorhanden ist, führt <xref:System.Windows.VisualStateManager.GoToState%2A> keine Aktion aus und gibt `false` zurück.  
  
#### Empfohlene Vorgehensweise für die Verwendung von VisualStateManager  
 Es wird empfohlen, dass Sie zum Verwalten der Zustände des Steuerelements wie folgt vorgehen:  
  
-   Verwenden Sie Eigenschaften, um den Zustand nachzuverfolgen.  
  
-   Erstellen Sie eine Hilfsmethode für das Wechseln zwischen Zuständen.  
  
 Das `NumericUpDown`\-Steuerelement verwendet seine `Value`\-Eigenschaft, um zu ermitteln, ob es im Zustand `Positive` oder im Zustand `Negative` ist.  Das `NumericUpDown`\-Steuerelement definiert auch die Zustände `Focused` und `UnFocused`, die die <xref:System.Windows.UIElement.IsFocused%2A>\-Eigenschaft nachverfolgen.  Wenn Sie Zustände verwenden, die nicht der Eigenschaft eines Steuerelements entsprechen, können Sie eine private Eigenschaft definieren, um den Zustand zu verfolgen.  
  
 Eine einzelne Methode, die alle Zustände aktualisiert, zentralisiert Aufrufe zum <xref:System.Windows.VisualStateManager> und hält den Code überschaubar.  Das folgende Beispiel zeigt die Hilfsmethode des `NumericUpDown`\-Steuerelements, `UpdateStates`.  Wenn `Value` größer oder gleich 0 ist, befindet sich das <xref:System.Windows.Controls.Control> im Zustand `Positive`.  Wenn `Value` kleiner als 0 ist, weist das Steuerelement den Zustand `Negative` auf.  Wenn <xref:System.Windows.UIElement.IsFocused%2A> `true` ist, weist das Steuerelement den Zustand `Focused` auf. Andernfalls befindet es sich im Zustand  `Unfocused`.  Das Steuerelement kann `UpdateStates` unabhängig davon, welcher Zustand sich ändert, immer dann aufrufen, wenn es seinen Zustand ändern muss.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 Übergeben Sie einen Zustandsnamen an <xref:System.Windows.VisualStateManager.GoToState%2A>, wenn das Steuerelement bereits in diesem Zustand ist, hat <xref:System.Windows.VisualStateManager.GoToState%2A> keine Auswirkungen. Daher müssen Sie den aktuellen Zustand des Steuerelements nicht überprüfen.  Wenn z. B. `Value` aus einer negativen Zahl in eine andere negative Zahl geändert wird, wird das Storyboard für den Zustand `Negative` nicht unterbrochen, und für den Benutzer sind keine Änderungen im Steuerelement sichtbar.  
  
 Der <xref:System.Windows.VisualStateManager> verwendet <xref:System.Windows.VisualStateGroup>\-Objekte, um zu bestimmen, welcher Zustand beendet werden soll, wenn Sie <xref:System.Windows.VisualStateManager.GoToState%2A> aufrufen.  Das Steuerelement befindet sich für jede <xref:System.Windows.VisualStateGroup>, die in der zugehörigen <xref:System.Windows.Controls.ControlTemplate> definiert ist, immer in einem Zustand und verlässt einen Zustand nur dann, wenn es in einen anderen Zustand aus derselben <xref:System.Windows.VisualStateGroup> wechselt.  Beispielsweise definiert die <xref:System.Windows.Controls.ControlTemplate> des `NumericUpDown`\-Steuerelements die <xref:System.Windows.VisualState>\-Objekte `Positive` und `Negative` in einer <xref:System.Windows.VisualStateGroup> und die <xref:System.Windows.VisualState>\-Objekte `Focused` und `Unfocused` in einer anderen.  \(Sie können den im Abschnitt [Vollständiges Beispiel](#complete_example) in diesem Beispiel definierten <xref:System.Windows.VisualState> `Focused` und `Unfocused` sehen. Wenn das Steuerelement aus dem Zustand `Positive` in den Zustand `Negative` wechselt oder umgekehrt, verbleibt das Steuerelement im Zustand `Focused` oder `Unfocused`.  
  
 Es gibt drei typische Situationen, in denen sich der Zustand eines Steuerelements ändern kann:  
  
-   Wenn die <xref:System.Windows.Controls.ControlTemplate> auf das <xref:System.Windows.Controls.Control> angewendet wird.  
  
-   Wenn sich eine Eigenschaft ändert.  
  
-   Wenn ein Ereignis eintritt.  
  
 In den folgenden Beispielen wird das Aktualisieren des Zustands des `NumericUpDown`\-Steuerelements in diesen Fällen veranschaulicht.  
  
 Sie sollten den Zustand des Steuerelements in der <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>\-Methode aktualisieren, sodass das Steuerelement im richtigen Zustand angezeigt wird, wenn die <xref:System.Windows.Controls.ControlTemplate> angewendet wird.  Im folgenden Beispiel wird `UpdateStates` in <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> aufgerufen, um sicherzustellen, dass sich das Steuerelement im entsprechenden Zustand befindet.  Angenommen, Sie erstellen ein `NumericUpDown`\-Steuerelement und legen den <xref:System.Windows.Controls.Control.Foreground%2A> auf Grün und `Value` auf \-5 fest.  Wenn Sie `UpdateStates` beim Anwenden der <xref:System.Windows.Controls.ControlTemplate> auf das `NumericUpDown`\-Steuerelement nicht aufrufen, weist das Steuerelement nicht den Zustand `Negative` auf, und der Wert ist Grün statt Rot.  Sie müssen `UpdateStates` aufrufen, um das Steuerelement in den Zustand `Negative` zu versetzen.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Oft muss der Zustand eines Steuerelements aktualisiert werden, wenn sich eine Eigenschaft ändert.  Im folgenden Beispiel wird die gesamte `ValueChangedCallback`\-Methode gezeigt.  Da `ValueChangedCallback` aufgerufen wird, wenn sich `Value` ändert, ruft die Methode `UpdateStates` auf, falls `Value` aus einer positiven Zahl in eine negative geändert wurde oder umgekehrt.  Es ist akzeptabel, `UpdateStates` aufzurufen, wenn sich `Value` zwar ändert, aber positiv bzw. negativ bleibt, da sich in diesem Fall der Zustand des Steuerelements nicht verändert.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 Möglicherweise müssen Sie den Zustand auch aktualisieren, wenn ein Ereignis eintritt.  Das folgende Beispiel zeigt, dass `NumericUpDown` `UpdateStates` für das <xref:System.Windows.Controls.Control> aufruft, um das <xref:System.Windows.UIElement.GotFocus>\-Ereignis zu behandeln.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 Der <xref:System.Windows.VisualStateManager> unterstützt Sie bei der Verwaltung der Zustände Ihres Steuerelements.  Durch Verwendung von <xref:System.Windows.VisualStateManager> stellen Sie sicher, dass das Steuerelement ordnungsgemäß zwischen Zuständen wechselt.  Wenn Sie den in diesem Abschnitt beschriebenen Empfehlungen zur Verwendung von <xref:System.Windows.VisualStateManager> folgen, bleibt der Code Ihres Steuerelements lesbar und verwaltbar.  
  
<a name="providing_the_control_contract"></a>   
## Bereitstellen des Steuerelementvertrags  
 Sie stellen einen Steuerelementvertrag bereit, damit Entwickler von <xref:System.Windows.Controls.ControlTemplate> wissen, was in die Vorlage eingefügt werden soll.  Ein Steuerelementvertrag besteht aus drei Elementen:  
  
-   Den von der Logik des Steuerelements verwendeten visuellen Elementen  
  
-   Den Zuständen des Steuerelements und den Gruppen, zu denen die einzelnen Zustände gehören  
  
-   Die öffentlichen Eigenschaften, die sich auf das Steuerelement visuell auswirken  
  
 Ein Entwickler, der eine neue <xref:System.Windows.Controls.ControlTemplate> erstellt, muss wissen, welche <xref:System.Windows.FrameworkElement>\-Objekte die Logik des Steuerelements verwendet und von welchem Typ die einzelnen Objekte sind. Außerdem muss der Name bekannt sein.  Ein Entwickler von <xref:System.Windows.Controls.ControlTemplate> muss darüber hinaus die Namen aller möglichen Zustände kennen, die das Steuerelement annehmen kann, und wissen, in welcher <xref:System.Windows.VisualStateGroup> sich der Zustand befindet.  
  
 Hinsichtlich des Beispiels von `NumericUpDown`, erwartet das Steuerelement, dass die <xref:System.Windows.Controls.ControlTemplate> über die folgenden <xref:System.Windows.FrameworkElement>\-Objekte verfügt:  
  
-   Eine <xref:System.Windows.Controls.Primitives.RepeatButton> mit dem Namen `UpButton`.  
  
-   Ein <xref:System.Windows.Controls.Primitives.RepeatButton> namens `DownButton.`.  
  
 Das Steuerelement kann sich in den folgenden Zuständen befinden:  
  
-   In der <xref:System.Windows.VisualStateGroup> `ValueStates`  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   In der <xref:System.Windows.VisualStateGroup> `FocusStates`  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 Um anzugeben, welche <xref:System.Windows.FrameworkElement>\-Objekte das Steuerelement erwartet, verwenden Sie das <xref:System.Windows.TemplatePartAttribute>, das den Namen und den Typ der erwarteten Elemente angibt.  Um die möglichen Zustände eines Steuerelements anzugeben, verwenden Sie das <xref:System.Windows.TemplateVisualStateAttribute>, das den Namen des Zustands sowie die <xref:System.Windows.VisualStateGroup> angibt, zu der er gehört.  Fügen Sie das <xref:System.Windows.TemplatePartAttribute> und das <xref:System.Windows.TemplateVisualStateAttribute> in die Klassendefinition des Steuerelements ein.  
  
 Jede öffentliche Eigenschaft, die sich auf die Darstellung des Steuerelements auswirkt, ist auch Teil des Steuerelementvertrags.  
  
 Im folgenden Beispiel werden das <xref:System.Windows.FrameworkElement>\-Objekt und die Zustände für das `NumericUpDown`\-Steuerelement angegeben.  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## Vollständiges Beispiel  
 Das folgende Beispiels ist die vollständige <xref:System.Windows.Controls.ControlTemplate> für das `NumericUpDown`\-Steuerelement.  
  
 [!code-xml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 Im folgenden Beispiel ist die Logik für das `NumericUpDown`\-Steuerelement dargestellt.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## Siehe auch  
 [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)   
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)