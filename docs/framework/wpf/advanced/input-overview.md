---
title: "&#220;bersicht &#252;ber die Eingabe | Microsoft Docs"
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
  - "Befehle [WPF]"
  - "Eingabe [WPF], Übersicht"
  - "Tastaturfokus [WPF]"
  - "Tastatureingabe [WPF]"
  - "Berührungsereignisse [WPF]"
  - "Ereignisrouting [WPF]"
  - "Fingereingabe [WPF]"
  - "Bearbeitung [WPF]"
  - "Logischer Fokus [WPF]"
  - "Tablettstifteingabe [WPF]"
  - "Texteingabe [WPF]"
  - "Behandeln von Eingabeereignissen [WPF]"
  - "Übersicht über die Eingabe WPF"
  - "Manipulationsereignisse [WPF]"
  - "Mauseingabe [WPF]"
  - "Mausauswahl [WPF]"
  - "Fokus [WPF]"
  - "Mausposition [WPF]"
ms.assetid: ee5258b7-6567-415a-9b1c-c0cbe46e79ef
caps.latest.revision: 50
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 50
---
# &#220;bersicht &#252;ber die Eingabe
<a name="introduction"></a>Die[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Subsystem bietet eine leistungsfähige [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] zum Abrufen von Eingaben aus einer Vielzahl von Geräten, einschließlich Maus, Tastatur, Fingereingabe und Tablettstift. In diesem Thema wird beschrieben, die von bereitgestellten Dienste [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und die Architektur von Eingabesysteme erläutert.  
  
  
<a name="input_api"></a>   
## <a name="input-api"></a>Eingabe-API  
 Die primäre Eingabe [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] Offenlegung der Basiselementklasse gefunden wird: <xref:System.Windows.UIElement>, <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkElement>, und <xref:System.Windows.FrameworkContentElement>.  Weitere Informationen zu den Basiselementen finden Sie unter [Base Elements Overview](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  Diese Klassen bieten Funktionen für Eingabeereignisse, die im Zusammenhang mit Tastatureingaben, Maustasten, Mausrad, Bewegung der Maus, Fokus Management und Mauseingaben, um nur einige zu nennen. Durch die Platzierung der Eingabe [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] über Basiselemente, anstatt alle Eingabeereignisse als einen Dienst, der ermöglicht es die Eingabeereignisse ein bestimmtes Objekt in der Benutzeroberfläche stammen und ein routing Ereignisschema unterstützen, bei dem hat mehr als ein Element ein Eingabeereignis zu behandeln. Vielen Eingabeereignissen ist ein Paar von Ereignissen zugeordnet.  Zum Beispiel das KeyUp-Ereignis zugeordnet ist die <xref:System.Windows.Input.Keyboard.KeyDown> und <xref:System.Windows.Input.Keyboard.PreviewKeyDown> Ereignisse.  Der Unterschied zwischen diesen Ereignissen wird in wie sie zum Zielelement weitergeleitet werden.  Vorschau von Tunneling in der Elementstruktur vom Stammelement an das Zielelement.  Bubbling-Ereignisse gehen Sie vom Zielelement dem Stammelement.  Das Ereignisrouting in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird ausführlicher unten in dieser Übersicht und unter der [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
### <a name="keyboard-and-mouse-classes"></a>Tastatur und Mausklassen  
 Zusätzlich zu der Eingabe [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] Basiselement-Klassen, die <xref:System.Windows.Input.Keyboard> Klasse und <xref:System.Windows.Input.Mouse> Klassen bieten zusätzliche [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] für die Arbeit mit Tastatur- und Mauseingaben.  
  
 Beispiele für die Eingabe- [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] auf der <xref:System.Windows.Input.Keyboard> -Klasse sind die <xref:System.Windows.Input.Keyboard.Modifiers%2A> ab der <xref:System.Windows.Input.ModifierKeys> gerade gedrückt wird, und die <xref:System.Windows.Input.Keyboard.IsKeyDown%2A> -Methode, die bestimmt, ob eine bestimmte Taste gedrückt wird.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Input.Keyboard.GetKeyStates%2A> -Methode bestimmt, ob ein <xref:System.Windows.Input.Key> im gedrückten Zustand ist.  
  
 [!code-csharp[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyArgsSnippetSample/CSharp/Window1.xaml.cs#keyeventargskeyboardgetkeystates)]
 [!code-vb[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyArgsSnippetSample/visualbasic/window1.xaml.vb#keyeventargskeyboardgetkeystates)]  
  
 Beispiele für die Eingabe- [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] auf der <xref:System.Windows.Input.Mouse> -Klasse sind <xref:System.Windows.Input.Mouse.MiddleButton%2A>, dem der Zustand der mittleren Maustaste abruft und <xref:System.Windows.Input.Mouse.DirectlyOver%2A>, der dem Element den Mauszeiger wird derzeit über.  
  
 Im folgenden Beispiel wird bestimmt, ob die <xref:System.Windows.Input.Mouse.LeftButton%2A> auf die Maus befindet sich in der <xref:System.Windows.Input.MouseButtonState> Zustand.  
  
 [!code-csharp[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MouseRelatedSnippets/CSharp/Window1.xaml.cs#mouserelatedsnippetsgetleftbuttonmouse)]
 [!code-vb[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MouseRelatedSnippets/visualbasic/window1.xaml.vb#mouserelatedsnippetsgetleftbuttonmouse)]  
  
 Die <xref:System.Windows.Input.Mouse> und <xref:System.Windows.Input.Keyboard> Klassen werden im Laufe dieser Übersicht noch ausführlicher behandelt.  
  
### <a name="stylus-input"></a>Tablettstifteingaben  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verfügt über eine integrierte Unterstützung für die <xref:System.Windows.Input.Stylus>.  Die <xref:System.Windows.Input.Stylus> ist ein Eingabegerät gewordenen durch die [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)].  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Clientanwendungen können als Maus des Tablettstifts behandeln, indem mit der Maus [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], aber [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] macht auch eine Abstraktion der Tablettstift-Geräts, mit denen ein Modell mit Tastatur und Maus.  Alle Tablettstift bezogenen [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] enthalten das Wort "Stylus".  
  
 Da der Stift als Maus eingesetzt werden kann, können Clientanwendungen, die nur die Mauseingabe unterstützen gewisse Unterstützung Tablettstift weiterhin automatisch erhalten. Wenn der Tablettstift auf diese Weise verwendet wird, wird die Anwendung erhält die Gelegenheit, das entsprechende Tablettstiftereignis behandeln und dann das entsprechende Mausereignis behandelt. Darüber hinaus sind auf höherer Ebene Dienste wie Freihandeingaben auch verfügbar durch die Abstraktion der Tablettstift-Geräts.  Weitere Informationen zur Freihandeingabe finden Sie unter [erste Schritte mit Freihandeingaben](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).  
  
<a name="event_routing"></a>   
## <a name="event-routing"></a>Ereignisrouting  
 Ein <xref:System.Windows.FrameworkElement> andere Elemente als untergeordnete Elemente im Inhaltsmodell bilden eine Struktur von Elementen enthalten kann.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], das übergeordneten Element Eingaben auf seine untergeordneten Elemente oder andere Nachfolger richten teilnehmen kann. Dies ist besonders nützlich zum Erstellen von Steuerelemente aus kleineren Steuerelementen ein Prozess wird als "steuerelementzusammensetzung" oder "zusammensetzen". Weitere Informationen über Elementstrukturen und wie Elementstrukturen auf Ereignisrouten beziehen, finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 Ereignisrouting versteht man das Weiterleiten von Ereignissen an mehrere Elemente, damit ein bestimmtes Objekt oder Element entlang der Route auswählen kann, um eine signifikante Antwort (durch Behandlung) auf ein Ereignis zu bieten, die möglicherweise von einem anderen Element erstellt wurde.  Routingereignisse verwenden einen von drei Routingmechanismen: direkt, bubbling und Tunneln.  Beim direkten Routing das Quellelement ist als einziges Element benachrichtigt, und das Ereignis wird nicht an andere Elemente weitergeleitet. Das direkte Routingereignis bietet jedoch noch einige zusätzlichen Funktionen, die nur für Routingereignisse im Gegensatz zu Standard sind [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Ereignisse. Die Elementstruktur funktioniert Bubbling, indem Sie zuerst das Element benachrichtigt, das das Ereignis dann Quelle das übergeordnete Element und So weiter.  Tunneling beginnt im Stamm der Elementstruktur und funktioniert, endet der ursprünglichen Quellelement.  Weitere Informationen zu Routingereignissen finden Sie unter [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Eingabeereignisse liegen in der Regel paarweise besteht aus einem Tunneling- und einem bubbling-Ereignis.  Tunneling-Ereignisse unterscheiden sich von bubbling-Ereignissen mit dem Präfix "Vorschau".  Beispielsweise <xref:System.Windows.Input.Mouse.PreviewMouseMove> ist die Tunneling-Version ein MouseMove-Ereignis und <xref:System.Windows.Input.Mouse.MouseMove> ist die bubbling-Version dieses Ereignisses. Dieses Ereignis Kopplung ist eine Konvention, die auf Elementebene implementiert ist und nicht unterstützt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignissystem. Weitere Informationen finden Sie im Abschnitt WPF-Eingabeereignissen in [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="handling_input_events"></a>   
## <a name="handling-input-events"></a>Behandeln von Eingabeereignissen  
 Um Eingaben für ein Element zu erhalten, muss ein Ereignishandler mit diesem speziellen Ereignis verknüpft sein.  In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dies ist einfach: Sie verweisen auf den Namen des Ereignisses als ein Attribut des Elements, das für dieses Ereignis überwacht.  Legen Sie anschließend den Wert des Attributs auf den Namen für den Ereignishandler, den Sie basierend auf einen Delegaten definieren, aus.  Der Ereignishandler muss z. B. in Code geschrieben werden [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] und können in einer Code-Behind-Datei eingeschlossen werden.  
  
 Tastaturereignisse auftreten, wenn das Betriebssystem Tastaturaktionen, die auftreten meldet, während der Tastaturfokus auf einem Element befindet. Maus- und Tablettstift lassen sich in zwei Kategorien: Ereignisse, die Bericht in die Position des Mauszeigers relativ zu dem Element ändert, und Ereignisse, die in den Status des Geräts Schaltflächen Bericht ändert.  
  
### <a name="keyboard-input-event-example"></a>Tastatur Eingabeereignis-Beispiel  
 Im folgende Beispiel überwacht ein Tastendruck Pfeil nach links.  Ein <xref:System.Windows.Controls.StackPanel> wird erstellt, verfügt über eine <xref:System.Windows.Controls.Button>.  Einen Ereignishandler für das Abhören von Drücken der nach-links-Taste zugeordnet ist die <xref:System.Windows.Controls.Button> Instanz.  
  
 Im ersten Abschnitt des Beispiels erstellt die <xref:System.Windows.Controls.StackPanel> und <xref:System.Windows.Controls.Button> und fügt den Ereignishandler für das <xref:System.Windows.UIElement.KeyDown>.  
  
 [!code-xml[InputOvw#Input_OvwKeyboardExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwkeyboardexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexampleuicodebehind)]  
  
 Der zweite Abschnitt ist in Code geschrieben und definiert den Ereignishandler.  Wenn die nach-links-Taste gedrückt wird und die <xref:System.Windows.Controls.Button> Tastaturfokus hat, der Handler ausgeführt und die <xref:System.Windows.Controls.Control.Background%2A> Farbe der <xref:System.Windows.Controls.Button> geändert wird.  Wenn die Taste gedrückt wird, aber es nicht die-links-Taste ist die <xref:System.Windows.Controls.Control.Background%2A> Farbe der <xref:System.Windows.Controls.Button> wieder in die Anfangsfarbe geändert wird.  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexamplehandlercodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexamplehandlercodebehind)]  
  
### <a name="mouse-input-event-example"></a>Beispiel für Mauseingabeereignisse  
 Im folgenden Beispiel die <xref:System.Windows.Controls.Control.Background%2A> Farbe einer <xref:System.Windows.Controls.Button> wird geändert, wenn der Mauszeiger wird die <xref:System.Windows.Controls.Button>.  Die <xref:System.Windows.Controls.Control.Background%2A> Farbe wird wiederhergestellt, wenn der Mauszeiger die <xref:System.Windows.Controls.Button>.  
  
 Im ersten Abschnitt des Beispiels erstellt die <xref:System.Windows.Controls.StackPanel> und <xref:System.Windows.Controls.Button> steuern und fügt die Ereignishandler für die <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave> Ereignisse an die <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[InputOvw#Input_OvwMouseExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwmouseexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleuicodebehind)]  
  
 Der zweite Abschnitt des Beispiels wird in Code geschrieben und definiert die Ereignishandler.  Wenn der Mauszeiger bewegt wird die <xref:System.Windows.Controls.Button>der <xref:System.Windows.Controls.Control.Background%2A> Farbe der <xref:System.Windows.Controls.Button> geändert wird, um <xref:System.Windows.Media.Brushes.SlateGray%2A>.  Wenn der Mauszeiger die <xref:System.Windows.Controls.Button>der <xref:System.Windows.Controls.Control.Background%2A> Farbe der <xref:System.Windows.Controls.Button> geändert wird, an <xref:System.Windows.Media.Brushes.AliceBlue%2A>.  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleeneterhandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleeneterhandler)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleleavehandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleleavehandler)]  
  
<a name="text_input"></a>   
## <a name="text-input"></a>Texteingabe  
 Die <xref:System.Windows.ContentElement.TextInput> -Ereignis können Sie für die Texteingabe auf eine geräteunabhängige Weise zu überwachen. Die Tastatur ist hauptsächlich Text Eingabe, sondern Sprache, Handschrift und andere Eingabegeräte ebenfalls Texteingaben generieren können.  
  
 Für die Tastatureingabe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zuerst sendet die entsprechende <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> Ereignisse. Wenn diese Ereignisse nicht verarbeitet, und der Schlüssel statt (wie z. B. Richtungspfeile eine STRG-Taste) oder Funktionstasten, Text ist ein <xref:System.Windows.ContentElement.TextInput> -Ereignis wird ausgelöst.  Es ist nicht immer eine einfache&1;:&1;-Zuordnung zwischen <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> und <xref:System.Windows.ContentElement.TextInput> Ereignisse, da mehrere Tastatureingaben ein einzelnes Zeichen als Texteingabe und einzelne Tastatureingaben Zeichenfolgen generieren können.  Dies gilt insbesondere für Sprachen wie Chinesisch, Japanisch und Koreanisch verwendet [!INCLUDE[TLA#tla_ime#plural](../../../../includes/tlasharptla-imesharpplural-md.md)] zum Generieren von Tausenden möglicher Zeichen entsprechend ihrem Alphabet.  
  
 Wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sendet ein <xref:System.Windows.ContentElement.KeyUp>/<xref:System.Windows.ContentElement.KeyDown> Ereignis <xref:System.Windows.Input.KeyEventArgs.Key%2A> auf festgelegt ist <xref:System.Windows.Input.Key?displayProperty=fullName> , wenn die Tastatureingaben Teil werden konnte ein <xref:System.Windows.ContentElement.TextInput> Ereignis (Wenn z. B. ALT + S gedrückt wird). Dies ermöglicht es Code in einer <xref:System.Windows.ContentElement.KeyDown> -Ereignishandler, um zu prüfen, ob <xref:System.Windows.Input.Key?displayProperty=fullName> und, falls gefunden, lassen Sie die Verarbeitung für den Handler, der anschließend erhöhten <xref:System.Windows.ContentElement.TextInput> Ereignis. In diesen Fällen die verschiedenen Eigenschaften der <xref:System.Windows.Input.TextCompositionEventArgs> Argument kann verwendet werden, um die ursprünglichen Tastatureingaben zu ermitteln. Auf ähnliche Weise, wenn ein [!INCLUDE[TLA2#tla_ime](../../../../includes/tla2sharptla-ime-md.md)] aktiv ist, <xref:System.Windows.Input.Key> hat den Wert <xref:System.Windows.Input.Key?displayProperty=fullName>, und <xref:System.Windows.Input.KeyEventArgs.ImeProcessedKey%2A> gibt das ursprüngliche Tastatureingabe oder Tastatureingaben.  
  
 Das folgende Beispiel definiert einen Handler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis und einen Ereignishandler für das <xref:System.Windows.UIElement.KeyDown> Ereignis.  
  
 Das erste Segment des Codes oder Markups erstellt die Benutzeroberfläche.  
  
 [!code-xml[InputOvw#Input_OvwTextInputXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwtextinputxaml)]  
  
 [!code-csharp[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputuicodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputuicodebehind)]  
  
 Das zweite Segment des Codes enthält die Ereignishandler.  
  
 [!code-csharp[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputhandlerscodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputhandlerscodebehind)]  
  
 Da die Ereignisroute Eingabeereignisse Bubbling die <xref:System.Windows.Controls.StackPanel> die Eingabe, unabhängig davon, welches Element den Tastaturfokus, erhält. Die <xref:System.Windows.Controls.TextBox> -Steuerelement wird zuerst benachrichtigt und die `OnTextInputKeyDown` Handler wird aufgerufen, wenn nur die <xref:System.Windows.Controls.TextBox> hat nicht die Eingabe verarbeitet. Wenn die <xref:System.Windows.UIElement.PreviewKeyDown> Ereignis wird verwendet, statt die <xref:System.Windows.UIElement.KeyDown> Ereignis der `OnTextInputKeyDown` Handler zuerst aufgerufen wird.  
  
 In diesem Beispiel wird der Verarbeitungslogik zweimal geschrieben: einmal STRG + O, und danach die Schaltfläche click-Ereignis. Dies kann mithilfe von Befehlen, anstatt die Eingabeereignisse direkt verarbeitet vereinfacht werden.  Befehle werden in dieser Übersicht und unter erläutert [Befehle (Übersicht)](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="touch_and_manipulation"></a>   
## <a name="touch-and-manipulation"></a>Touch und-Bearbeitung  
 Neue Hardware und eine API in das Betriebssystem Windows 7 bieten Anwendungen die Möglichkeit zum Empfangen von Eingaben aus mehrere Fingereingaben gleichzeitig. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ermöglicht Anwendungen das Erkennen und ähnlich wie für andere Eingabe, z. B. Maus oder Tastatur, durch das Auslösen von Ereignissen tritt Fingereingabe reagiert Fingereingabe reagieren.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt zwei Arten von Ereignissen tritt Touch: touch-Ereignisse und Manipulation-Ereignisse. Berührungsereignisse stellen Rohdaten zu jedem Finger auf einem Touchscreen und seiner Bewegung bereit. Bearbeitungsereignisse interpretieren die Eingabe als bestimmte Aktionen. Beide Typen von Ereignissen werden in diesem Abschnitt erläutert.  
  
### <a name="prerequisites"></a>Erforderliche Komponenten  
 Sie benötigen die folgenden Komponenten zur Entwicklung einer Anwendung, die auf Fingereingabe reagiert.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Ein Gerät, z. B. ein Touchscreen, der Windows Touch-Unterstützung.  
  
### <a name="terminology"></a>Terminologie  
 Die folgenden Begriffe werden verwendet, wenn die Fingereingabe.  
  
-   **Touch-** ist ein Typ von Benutzereingaben, die von Windows 7 erkannt wird. In der Regel wird die Fingereingabe initiiert, indem Finger auf einen berührungsempfindlichen Bildschirm. Beachten Sie, dass Geräte wie Touchpads das gemeinsame auf Laptops keine Fingereingabe unterstützen, wenn das Gerät lediglich des Fingers Position und Bewegung als Mauseingabe konvertiert.  
  
-   **Mehrfingereingabe** Fingereingabe, die gleichzeitig von mehreren Punkten erfolgt ist. Windows 7 und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Mehrfingereingabe unterstützt. Wenn Fingereingabe in der Dokumentation für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], die Konzepte für die Mehrfingereingabe.  
  
-   Ein **Manipulation** tritt auf, wenn die Berührung als physische Aktion interpretiert wird, der auf ein Objekt angewendet wird. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Bearbeitungsereignisse interpretieren die Eingabe als Übersetzung, Erweiterung oder Drehung Bearbeitung.  
  
-   Ein `touch device` stellt ein Gerät, das Fingereingabe, z. B. ein Finger auf einem Touchscreen erzeugt.  
  
### <a name="controls-that-respond-to-touch"></a>Steuerelemente, die auf Fingereingabe reagieren  
 Die folgenden Steuerelemente können Bildlauf durchgeführt werden, indem ein Finger über das Steuerelement ziehen, wenn sie Inhalt verfügt, die aus der Ansicht ein Bildlauf durchgeführt wird.  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.DataGrid>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
 Die <xref:System.Windows.Controls.ScrollViewer> definiert die <xref:System.Windows.Controls.ScrollViewer.PanningMode%2A?displayProperty=fullName> angefügten Eigenschaft, mit der Sie angeben, ob Touch Schwenken aktiviert ist horizontal, vertikal, beides oder keines von beiden. Die <xref:System.Windows.Controls.ScrollViewer.PanningDeceleration%2A?displayProperty=fullName> -Eigenschaft gibt an, wie schnell sich der Bildlauf verlangsamt, wenn der Benutzer den Finger vom Touchscreen hebt. Die <xref:System.Windows.Controls.ScrollViewer.PanningRatio%2A?displayProperty=fullName> angefügte Eigenschaft gibt das Verhältnis der Bildlauf Manipulation Offset übersetzt.  
  
### <a name="touch-events"></a>Touch-Ereignisse  
 Die Basisklassen <xref:System.Windows.UIElement>, <xref:System.Windows.UIElement3D>, und <xref:System.Windows.ContentElement>, definieren Ereignisse, die Sie abonnieren können, damit die Anwendung auf Fingereingabe reagiert. Berührungsereignisse sind nützlich, wenn die Anwendung Fingereingabe als etwas anderes als ein Objekt bearbeiten interpretiert. Beispielsweise würde eine Anwendung, die ein Benutzer mit einem oder mehreren Fingern zeichnen kann Berührungsereignisse abonnieren.  
  
 Alle drei Klassen definieren die folgenden Ereignisse, die auf ähnliche Weise, unabhängig von der definierenden Klasse Verhalten aufweisen.  
  
-   <xref:System.Windows.UIElement.TouchDown>  
  
-   <xref:System.Windows.UIElement.TouchMove>  
  
-   <xref:System.Windows.UIElement.TouchUp>  
  
-   <xref:System.Windows.UIElement.TouchEnter>  
  
-   <xref:System.Windows.UIElement.TouchLeave>  
  
-   <xref:System.Windows.UIElement.PreviewTouchDown>  
  
-   <xref:System.Windows.UIElement.PreviewTouchMove>  
  
-   <xref:System.Windows.UIElement.PreviewTouchUp>  
  
-   <xref:System.Windows.UIElement.GotTouchCapture>  
  
-   <xref:System.Windows.UIElement.LostTouchCapture>  
  
 Wie die Tastatur und Maus-Ereignisse sind die Berührungsereignisse Routingereignisse. Die Ereignisse, die mit `Preview` sind Tunneling-Ereignisse und die Ereignisse, die mit `Touch` sind bubbling-Ereignisse. Weitere Informationen zu Routingereignissen finden Sie unter [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md). Wenn Sie diese Ereignisse behandeln, können Sie die Position der Eingabe relativ zu einem Element erhalten, durch Aufrufen der <xref:System.Windows.Input.TouchEventArgs.GetTouchPoint%2A> oder <xref:System.Windows.Input.TouchEventArgs.GetIntermediateTouchPoints%2A> Methode.  
  
 Um die Interaktion zwischen der Touch-Ereignissen zu verstehen, betrachten Sie ein Szenario, in dem ein Benutzer legt einen Finger auf ein Element im Element bewegt und dann den Finger vom Element hebt. Die folgende Abbildung zeigt die Ausführung der bubbling-Ereignisse (dem Tunneling-Ereignisse werden der Einfachheit halber ausgelassen).  
  
 ![Die Reihenfolge der Berührungsereignisse.](../../../../docs/framework/wpf/advanced/media/ndp-touchevents.png "NDP_TouchEvents")  
Touch-Ereignisse  
  
 Die folgende Liste beschreibt die Abfolge der Ereignisse in der vorherigen Abbildung.  
  
1.  Die <xref:System.Windows.UIElement.TouchEnter> -Ereignis tritt einmal, wenn der Benutzer einen Finger auf das Element legt.  
  
2.  Die <xref:System.Windows.UIElement.TouchDown> -Ereignis tritt einmal auf.  
  
3.  Die <xref:System.Windows.UIElement.TouchMove> -Ereignis tritt mehrmals auf, wenn der Benutzer den Finger auf dem Element bewegt.  
  
4.  Die <xref:System.Windows.UIElement.TouchUp> -Ereignis tritt einmal, wenn der Benutzer den Finger vom Element hebt.  
  
5.  Die <xref:System.Windows.UIElement.TouchLeave> -Ereignis tritt einmal auf.  
  
 Wenn mehr als zwei Finger verwendet werden, treten die Ereignisse für jeden Finger.  
  
### <a name="manipulation-events"></a>Manipulation-Ereignisse  
 Für Fälle, in denen eine Anwendung einen Benutzer zum Bearbeiten eines Objekts kann, die <xref:System.Windows.UIElement> Klasse definiert Bearbeitungsereignisse. Im Gegensatz zu den touchereignisse, die einfach die Position der Fingereingabe melden, melden die Bearbeitungsereignisse, wie die Eingabe interpretiert werden kann. Es gibt drei Arten von Manipulationen, Übersetzung, Erweiterung und Drehung. Die folgende Liste beschreibt, wie die drei Typen von Manipulationen aufgerufen wird.  
  
-   Legen Sie einen Finger auf ein Objekt, und verschieben Sie den Finger über dem Touchscreen, um eine Manipulation Übersetzung aufzurufen. Dadurch wird in der Regel das Objekt verschoben.  
  
-   Legen Sie zwei Finger auf ein Objekt, und bewegen Sie die Finger näher zusammen oder weiter dürfen eine Erweiterung Bearbeitung aufgerufen. Dies wird in der Regel das Objekt.  
  
-   Legen Sie zwei Finger auf ein Objekt, und drehen Sie die Finger um den jeweils anderen um eine Manipulation Drehung aufzurufen. Dies wird in der Regel das Objekt gedreht.  
  
 Mehr als eine Art von Manipulation kann gleichzeitig durchgeführt werden.  
  
 Wenn Sie dazu führen, dass die Objekte, um Manipulationen zu reagieren, haben Sie das Objekt scheinbar Trägheit haben. Dadurch kann die physische Welt simulieren Objekte sein. Wenn Sie ein Buch über eine Tabelle übertragen, wenn Sie die Festplatte übertragen wird z. B. genug Buch weiterhin, verschieben, nachdem Sie sie freigeben. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]können Sie dieses Verhalten durch das Auslösen von Bearbeitungsereignissen, nachdem die Finger des Benutzers das Objekt simulieren.  
  
 Informationen dazu, wie Sie eine Anwendung erstellen, mit dem Benutzer zu verschieben, skalieren und Drehen von Objekten, finden Sie unter [Walkthrough: Creating Your First Touch Application](../../../../docs/framework/wpf/advanced/walkthrough-creating-your-first-touch-application.md).  
  
 Die <xref:System.Windows.UIElement> definiert die folgenden Bearbeitungsereignisse.  
  
-   <xref:System.Windows.UIElement.ManipulationStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationStarted>  
  
-   <xref:System.Windows.UIElement.ManipulationDelta>  
  
-   <xref:System.Windows.UIElement.ManipulationInertiaStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationCompleted>  
  
-   <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>  
  
 In der Standardeinstellung eine <xref:System.Windows.UIElement> empfängt diese Manipulationsereignisse nicht. Um Manipulation-Ereignisse empfangen ein <xref:System.Windows.UIElement>legen <xref:System.Windows.UIElement.IsManipulationEnabled%2A?displayProperty=fullName> auf `true`.  
  
#### <a name="the-execution-path-of-manipulation-events"></a>Der Ausführungspfad von Bearbeitungsereignissen  
 Betrachten Sie ein Szenario, in dem ein Benutzer ein Objekt "wirft". Der Benutzer einen Finger auf das Objekt, legt der Finger bewegt sich über dem Touchscreen für eine kurze Entfernung und hebt dann den Finger während der Bewegung. Das Ergebnis davon ist, dass das Objekt unter dem Finger des Benutzers verschieben und weiterhin bewegt, nachdem der Benutzer den Finger gehoben hat.  
  
 Die folgende Abbildung zeigt den Ausführungspfad von Bearbeitungsereignissen und wichtige Informationen zu jedem Ereignis.  
  
 ![Die Reihenfolge der Bearbeitungsereignisse.](../../../../docs/framework/wpf/advanced/media/ndp-manipulationevents.png "NDP_ManipulationEvents")  
Manipulation-Ereignisse  
  
 Die folgende Liste beschreibt die Abfolge der Ereignisse in der vorherigen Abbildung.  
  
1.  Die <xref:System.Windows.UIElement.ManipulationStarting> Ereignis tritt auf, wenn der Benutzer einen Finger auf das Objekt platziert. Unter anderem mit diesem Ereignis können Sie festlegen, die <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> Eigenschaft. In den nachfolgenden Ereignissen werden relativ zu die Position der Manipulation der <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>. In anderen Ereignissen als <xref:System.Windows.UIElement.ManipulationStarting>, diese Eigenschaft ist schreibgeschützt, sodass die <xref:System.Windows.UIElement.ManipulationStarting> Ereignis ist das einzige Mal, das diese Eigenschaft festgelegt werden kann.  
  
2.  Die <xref:System.Windows.UIElement.ManipulationStarted> Ereignisses weiter. Dieses Ereignis meldet den Ursprung der Manipulation.  
  
3.  Die <xref:System.Windows.UIElement.ManipulationDelta> -Ereignis tritt mehrmals als ein Benutzer Finger auf einem Touchscreen bewegen. Die <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> Eigenschaft der <xref:System.Windows.Input.ManipulationDeltaEventArgs> -Klasse meldet, ob die Bearbeitung als Drehung, Erweiterung oder Verschiebung interpretiert wird. Dies ist, in dem Sie die meisten der Bearbeitung eines Objekts ausführen.  
  
4.  Die <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis tritt auf, wenn die Finger des Benutzers den Kontakt mit dem Objekt verlieren. Dieses Ereignis können Sie die Verlangsamung der Manipulationen während der Trägheit an. Dies ist das Objekt verschiedene physikalische Räume oder Attribute emulieren kann, auf Wunsch. Nehmen wir beispielsweise an, Ihre Anwendung enthält zwei Objekte, die Elemente in der realen Welt darstellen, und eine größere als das andere. Sie können das größere Objekt schneller als das leichtere Objekt verlangsamt vornehmen.  
  
5.  Die <xref:System.Windows.UIElement.ManipulationDelta> -Ereignis tritt mehrmals aus, wenn Trägheit auftritt. Beachten Sie, dass dieses Ereignis tritt auf, wenn die Finger des Benutzers über dem Touchscreen bewegen und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Trägheit simuliert. Das heißt, <xref:System.Windows.UIElement.ManipulationDelta> tritt vor und nach der <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis. Die <xref:System.Windows.Input.ManipulationDeltaEventArgs.IsInertial%2A?displayProperty=fullName> -Eigenschaft Berichten, ob der <xref:System.Windows.UIElement.ManipulationDelta> Ereignis tritt auf, während der Trägheit, damit Sie diese Eigenschaft überprüfen und je nach Wert verschiedene Aktionen ausführen können.  
  
6.  Die <xref:System.Windows.UIElement.ManipulationCompleted> Ereignis tritt auf, wenn die Bearbeitung und alle Trägheit endet. Das heißt, nachdem alle der <xref:System.Windows.UIElement.ManipulationDelta> Ereignisse auftreten, die <xref:System.Windows.UIElement.ManipulationCompleted> Ereignis tritt auf, um zu signalisieren, dass die Bearbeitung abgeschlossen ist.  
  
 Die <xref:System.Windows.UIElement> definiert außerdem die <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Ereignis. Dieses Ereignis tritt auf, wenn die <xref:System.Windows.Input.ManipulationDeltaEventArgs.ReportBoundaryFeedback%2A> Methode wird aufgerufen, der <xref:System.Windows.UIElement.ManipulationDelta> Ereignis. Die <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Ereignis ermöglicht, Anwendungen oder Komponenten, visuelles Feedback bereitzustellen, wenn ein Objekt eine Grenze erreicht. Zum Beispiel die <xref:System.Windows.Window> -Klasse behandelt die <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Ereignis, um das Fenster leicht bewegt, wenn der Rand erreicht wird.  
  
 Brechen Sie die Bearbeitung durch Aufrufen der <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> -Methode für die Ereignisargumente in jedem Bearbeitungsereignis außer <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Ereignis. Beim Aufruf von <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A>, das die Manipulationsereignisse nicht mehr ausgelöst und Mausereignisse treten für Touch. Die folgende Tabelle beschreibt die Beziehung zwischen dem Zeitpunkt, den die Bearbeitung abgebrochen wird und die Mausereignisse, die auftreten.  
  
|Das Ereignis, das Abbrechen wird im aufgerufen|Die Mausereignisse, die auftreten, für die Eingabe, die bereits aufgetreten ist.|  
|----------------------------------------|-----------------------------------------------------------------|  
|<xref:System.Windows.UIElement.ManipulationStarting> und <xref:System.Windows.UIElement.ManipulationStarted>|Ereignisse mit der Maus.|  
|<xref:System.Windows.UIElement.ManipulationDelta>|Maus nach unten und Ereignisse der Maus verschieben.|  
|<xref:System.Windows.UIElement.ManipulationInertiaStarting> und <xref:System.Windows.UIElement.ManipulationCompleted>|Die Maus nach unten, Maus und Maus Ereignisse.|  
  
 Beachten Sie, dass beim Aufrufen <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> , wenn die Bearbeitung in Trägheit ist, gibt die Methode `false` und die Eingabe keine Mausereignisse auslöst.  
  
### <a name="the-relationship-between-touch-and-manipulation-events"></a>Die Beziehung zwischen Berührungs- und Bearbeitungsereignissen  
 Ein <xref:System.Windows.UIElement> immer touchereignisse empfangen werden können. Wenn die <xref:System.Windows.UIElement.IsManipulationEnabled%2A> -Eigenschaft auf festgelegt ist `true`, <xref:System.Windows.UIElement> Fingereingabe und Manipulation-Ereignisse empfangen werden können.  Wenn die <xref:System.Windows.UIElement.TouchDown> -Ereignis nicht behandelt (d. h. die <xref:System.Windows.RoutedEventArgs.Handled%2A> Eigenschaft ist `false`), die Bearbeitungslogik erfasst die Fingereingabe für das Element, und generiert die Bearbeitungsereignisse. Wenn der <xref:System.Windows.RoutedEventArgs.Handled%2A> -Eigenschaft wird festgelegt, um `true` in der <xref:System.Windows.UIElement.TouchDown> generiert Ereignis die Bearbeitungslogik keine Bearbeitungsereignisse. Die folgende Abbildung zeigt die Beziehung zwischen Fingereingabe und Manipulationsereignisse.  
  
 ![Beziehung zwischen berührungs-und Bearbeitungsereignissen](../../../../docs/framework/wpf/advanced/media/ndp-touchmanipulateevents.png "NDP_TouchManipulateEvents")  
Berührungs-und Bearbeitungsereignissen  
  
 Die folgende Liste beschreibt die Beziehung zwischen berührungs- und Bearbeitungsereignissen-Ereignissen, die in der vorherigen Abbildung dargestellt ist.  
  
-   Das erste touchgerät beim Generieren einer <xref:System.Windows.UIElement.TouchDown> -Ereignis auf eine <xref:System.Windows.UIElement>, ruft die Bearbeitungslogik die <xref:System.Windows.UIElement.CaptureTouch%2A> Methode, die generiert die <xref:System.Windows.UIElement.GotTouchCapture> Ereignis.  
  
-   Wenn die <xref:System.Windows.UIElement.GotTouchCapture> auftritt, ruft die Bearbeitungslogik die <xref:System.Windows.Input.Manipulation.AddManipulator%2A?displayProperty=fullName> Methode, die generiert die <xref:System.Windows.UIElement.ManipulationStarting> Ereignis.  
  
-   Wenn die <xref:System.Windows.UIElement.TouchMove> Ereignisse auftreten, generiert die Bearbeitungslogik die <xref:System.Windows.UIElement.ManipulationDelta> Ereignisse, die vor dem Auftreten der <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis.  
  
-   Löst das Element, wenn das letzte Gerät tippen Sie auf die <xref:System.Windows.UIElement.TouchUp> Ereignis, generiert die Bearbeitungslogik die <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis.  
  
<a name="focus"></a>   
## <a name="focus"></a>Fokus  
 Es gibt zwei Hauptkonzepte, die hinsichtlich des Fokus in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: den Tastaturfokus und den logischen Fokus.  
  
### <a name="keyboard-focus"></a>Der Tastaturfokus  
 Der Tastaturfokus bezieht sich auf das Element, das Tastatureingaben empfängt.  Es kann nur ein Element auf dem gesamten desktop, das über den Tastaturfokus verfügt.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], das Element, das den Tastaturfokus hat <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> festgelegt `true`.  Die statische <xref:System.Windows.Input.Keyboard> Methode <xref:System.Windows.Input.Keyboard.FocusedElement%2A> gibt das Element zurück, die derzeit über den Tastaturfokus verfügt.  
  
 Der Tastaturfokus kann abgerufen werden, durch die TAB-Taste zu einem Element oder durch Klicken mit der Maus auf bestimmte Elemente, wie z. B. ein <xref:System.Windows.Controls.TextBox>.  Der Tastaturfokus kann auch programmgesteuert mithilfe von abgerufen werden die <xref:System.Windows.Input.Keyboard.Focus%2A> Methode für die <xref:System.Windows.Input.Keyboard> Klasse.  <xref:System.Windows.Input.Keyboard.Focus%2A> Versuche für das angegebene Element ein Tastatur den Fokus.  Das zurückgegebene Element <xref:System.Windows.Input.Keyboard.Focus%2A> ist das Element, das derzeit über den Tastaturfokus verfügt.  
  
 In der Reihenfolge für ein Element den Tastaturfokus erhalten die <xref:System.Windows.UIElement.Focusable%2A> Eigenschaft und die <xref:System.Windows.UIElement.IsVisible%2A> Eigenschaften müssen festgelegt werden, um **true**.  Einige Klassen, z. B. <xref:System.Windows.Controls.Panel>, haben <xref:System.Windows.UIElement.Focusable%2A> festgelegt `false` standardmäßig; aus diesem Grund müssen unter Umständen zum Festlegen dieser Eigenschaft auf `true` Wenn Sie möchten, dass dieses Element den Fokus erhalten kann.  
  
 Im folgenden Beispiel wird <xref:System.Windows.Input.Keyboard.Focus%2A> festzulegende Tastaturfokus auf eine <xref:System.Windows.Controls.Button>.  Am besten platzieren Sie den Anfangsfokus in einer Anwendung wird der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Weitere Informationen über den Tastaturfokus finden Sie unter [Fokus-Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
### <a name="logical-focus"></a>Der logische Fokus  
 Der logische Fokus bezieht sich auf die <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=fullName> in einem Bereich konzentrieren.  Können mehrere Elemente mit der logische Fokus in einer Anwendung vorhanden sein, aber es kann nur ein Element mit dem logischen Fokus in einem Bereich Schwerpunkt vorhanden sein.  
  
 Ein Schwerpunkt Bereich ist ein Containerelement, das verfolgt die <xref:System.Windows.Input.FocusManager.FocusedElement%2A> innerhalb des Bereichs.  Wenn der Fokus auf einem verlässt, das Element Tastaturfokus gehen verloren, aber Sie werden der logische Fokus wird beibehalten.  Gibt den Fokus auf den Fokusbereich erhalten das Element über den Tastaturfokus.  Dies ermöglicht Tastaturfokus zwischen verschiedenen geändert werden, jedoch wird sichergestellt, dass das fokussierte Element innerhalb des Fokusbereichs das Element bleibt, wenn der Fokus wechselt wieder.  
  
 Ein Element kann in einem Fokusbereich umgewandelt werden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] durch Festlegen der <xref:System.Windows.Input.FocusManager> angefügte Eigenschaft <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> auf `true`, oder im Code, indem Sie die angefügte Eigenschaft mithilfe der <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> Methode.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.StackPanel> zu einem durch Festlegen der <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> angefügte Eigenschaft.  
  
 [!code-xml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 Klassen im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind standardmäßig Fokusbereiche sind <xref:System.Windows.Window>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolBar>, und <xref:System.Windows.Controls.ContextMenu>.  
  
 Ein Element, das den Tastaturfokus ist auch der logische Fokus innerhalb, der er angehört. daher das Festlegen des Fokus auf ein Element mit der <xref:System.Windows.Input.Keyboard.Focus%2A> Methode für die <xref:System.Windows.Input.Keyboard> -Klasse oder der Basiselementklasse versucht, dem Element den Tastaturfokus und der logische Fokus zuzuweisen.  
  
 Verwenden Sie zum Bestimmen der fokussierten Elements in einem <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>. Um das fokussierte Element für einen Bereich konzentrieren zu ändern, verwenden Sie <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>.  
  
 Weitere Informationen über den logischen Fokus finden Sie unter [Fokus-Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
<a name="mouse_position"></a>   
## <a name="mouse-position"></a>Position des Mauszeigers  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] input [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] bietet nützliche Informationen in Bezug auf Koordinatensysteme.  Z. B. koordinieren `(0,0)` ist die linke obere Koordinate, aber der linken oberen Ecke von welchem Element in der Struktur? Das Element, das Eingabe-Ziel ist? Das Element angefügten Ereignishandler können? Oder etwas anderes? Um Verwechslungen zu vermeiden der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] input [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] erfordert, dass Sie Ihre Verweisrahmen angeben, bei der Arbeit mit den Koordinaten der Maus. Die <xref:System.Windows.Input.Mouse.GetPosition%2A> -Methode gibt die Koordinate des Mauszeigers relativ zum angegebenen Element zurück.  
  
<a name="mouse_capture"></a>   
## <a name="mouse-capture"></a>Erfassen von Mauseingaben  
 Mausgeräte verfügen ein modales Merkmal, das als Mausauswahl bezeichnet. Erfassen von Mauseingaben wird verwendet, um eine Eingabe Übergangsstatus, wenn ein Drag & Drop-Vorgang gestartet wird, beibehalten werden, damit andere Vorgänge, die auf dem Bildschirm betreffen die nominale Position des Mauszeigers nicht unbedingt auftreten. Während des Ziehens kann nicht der Benutzer klicken, ohne die Drag & Drop, die Hinweise für die meisten Mouseover werden, während die Mauseingaben vom Ursprung Ziehens abbrechen. Das Eingabesystem stellt [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] feststellen, dass des Zustands von Mauseingaben, sowie [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] , die Mausauswahl für ein bestimmtes Element erzwingen oder Löschen des Zustands von Mauseingaben können. Weitere Informationen zu Drag & Drop-Vorgängen finden Sie unter [Drag and Drop Overview](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md).  
  
<a name="commands"></a>   
## <a name="commands"></a>Befehle  
 Befehle ermöglichen die Eingabebehandlung auf einer eher semantischen Ebene als.  Befehle sind einfache Direktiven, wie z. B. `Cut`, `Copy`, `Paste`, oder `Open`.  Befehle sind nützlich für die Zentralisierung der Befehlslogik.  Derselbe Befehl aus zugegriffen werden kann ein <xref:System.Windows.Controls.Menu>auf eine <xref:System.Windows.Controls.ToolBar>, oder über eine Tastenkombination. Befehle stellen außerdem einen Mechanismus zum Deaktivieren von Steuerelementen, wenn der Befehl nicht verfügbar ist.  
  
 <xref:System.Windows.Input.RoutedCommand> ist die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Implementierung von <xref:System.Windows.Input.ICommand>.  Wenn ein <xref:System.Windows.Input.RoutedCommand> ausgeführt wird, eine <xref:System.Windows.Input.CommandManager.PreviewExecuted> und ein <xref:System.Windows.Input.CommandManager.Executed> für das Ziel des Befehls, welche Aufwärts und in der Elementstruktur wie andere Eingaben Ereignis ausgelöst.  Wenn ein Befehlsziel nicht festgelegt ist, wird das Element mit dem Tastaturfokus das Befehlsziel sein.  Die Logik, die den Befehl ausführt gehört ein <xref:System.Windows.Input.CommandBinding>.  Wenn ein <xref:System.Windows.Input.CommandManager.Executed> -Ereignis erreicht eine <xref:System.Windows.Input.CommandBinding> für diesen Befehl, der <xref:System.Windows.Input.ExecutedRoutedEventHandler> auf der <xref:System.Windows.Input.CommandBinding> aufgerufen wird.  Dieser Handler führt die Aktion des Befehls.  
  
 Weitere Informationen über Befehle finden Sie unter [Befehle (Übersicht)](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Stellt eine Bibliothek mit häufig verwendeten Befehlen besteht aus <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, und <xref:System.Windows.Documents.EditingCommands>, oder Sie können Ihren eigenen definieren.  
  
 Das folgende Beispiel zeigt, wie eine <xref:System.Windows.Controls.MenuItem> , wenn darauf geklickt wird aufgerufen der <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl die <xref:System.Windows.Controls.TextBox>, vorausgesetzt die <xref:System.Windows.Controls.TextBox> Tastaturfokus hat.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
 Weitere Informationen über Befehle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter [Befehle (Übersicht)](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="the_input_system_and_base_elements"></a>   
## <a name="the-input-system-and-base-elements"></a>Das Eingabesystem und die Basiselemente  
 Eingabeereignisse wie die angefügten Ereignisse definiert, die von der <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, und <xref:System.Windows.Input.Stylus> Klassen werden vom Eingabesystem ausgelöst und an einer bestimmten Position im Objektmodell basierend auf einem Treffertest der visuellen Struktur zur Laufzeit eingefügt.  
  
 Jedes der Ereignisse, die <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, und <xref:System.Windows.Input.Stylus> definieren, wie ein angefügtes Ereignis auch von der Basiselementklasse wieder verfügbar gemacht wird <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> als ein neues Ereignis. Die Basiselement-Routingereignisse werden von Klassen, die die ursprüngliche angefügte Ereignis behandeln und Wiederverwendung von Daten für das Ereignis generiert.  
  
 Wenn das Eingabeereignis eine bestimmte Quellelement durch seine Implementierung des Basiselements Eingabeereignis zugeordnet wird, können sie über den Rest der eine Ereignisroute weitergeleitet werden, die auf einer Kombination von logischen und visuelle Struktur basiert, und vom Anwendungscode behandelt werden.  Im Allgemeinen ist es einfacher, diese gerätebezogenen Eingabeereignisse anhand der Routingereignisse für verarbeiten <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement>, da Sie eine intuitivere Ereignishandlersyntax sowohl in verwenden können [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und im Code. Sie konnte das angefügte Ereignis zu behandeln, die stattdessen eingeleitet, jedoch würden Sie verschiedene Probleme aufwirft: das angefügte Ereignis möglicherweise von der Klassenbehandlung Basiselement gekennzeichnet, und Sie müssen Accessormethoden statt true Ereignissyntax verwenden, um Handler für angefügte Ereignisse anfügen.  
  
<a name="whats_next"></a>   
## <a name="whats-next"></a>Weitere Informationen  
 Sie verfügen jetzt über verschiedene Methoden zum Behandeln von Eingaben in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Sie sollten auch eine verbesserte Verständnis der verschiedenen Typen von Eingabeereignissen und stellt Routingereignis haben [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Zusätzliche Ressourcen sind verfügbar, die erläutern [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Framework-Elemente und das Ereignisrouting noch ausführlicher. Finden Sie weitere Informationen in die folgenden Übersichten [Befehle (Übersicht)](../../../../docs/framework/wpf/advanced/commanding-overview.md), [Fokus-Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md), [Base Elements Overview](../../../../docs/framework/wpf/advanced/base-elements-overview.md), [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md), und [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Fokus-Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md)   
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Eigenschaften](../../../../docs/framework/wpf/advanced/properties-wpf.md)