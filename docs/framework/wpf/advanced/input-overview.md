---
title: Übersicht über die Eingabe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [WPF]
- input [WPF], overview
- keyboard focus [WPF]
- keyboard input [WPF]
- touch events [WPF]
- event routing [WPF]
- touch input [WPF]
- manipulation [WPF]
- logical focus [WPF]
- stylus input [WPF]
- text input [WPF]
- input events [WPF], handling
- WPF [WPF], input overview
- manipulation events [WPF]
- mouse input [WPF]
- mouse capture [WPF]
- focus [WPF]
- mouse position [WPF]
ms.assetid: ee5258b7-6567-415a-9b1c-c0cbe46e79ef
ms.openlocfilehash: 00a1f25546bb8dd4f8a587c8a5f03f1043632e08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549528"
---
# <a name="input-overview"></a>Übersicht über die Eingabe
<a name="introduction"></a> Das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Subsystem bietet eine leistungsstarke [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] zum Abrufen von Eingabe von einer Vielzahl von Geräten, einschließlich Maus, Tastatur, Touchpad und Stift. In diesem Thema werden die Dienste beschrieben, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt werden sowie die Architektur des Eingabesystems.  
  
  
<a name="input_api"></a>   
## <a name="input-api"></a>Eingabe-API  
 Die primäre Eingabe [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] Offenlegung finden Sie in den Klassen Basiselement: <xref:System.Windows.UIElement>, <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkElement>, und <xref:System.Windows.FrameworkContentElement>.  Weitere Informationen zu den Basiselementen finden Sie unter [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  Diese Klassen bieten Funktionen für Eingabeereignisse, die im Zusammenhang mit Tastatureingaben, Maustasten, dem Mausrad, der Bewegung der Maus, der Fokusverwaltung und Mauseingabe stehen, um nur einige zu nennen. Anstatt alle Eingabeereignisse als einen Dienst zu behandeln, ermöglicht die Eingabearchitektur durch die Platzierung der Eingabe-[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] auf Basiselementen, dass die Eingabeereignisse von einem bestimmten Objekt auf der Benutzeroberfläche stammen und ein Ereignisroutingschema unterstützen, wobei mehr als ein Element die Möglichkeit hat, ein Eingabeereignis zu behandeln. Vielen Eingabeereignissen ist ein Paar von Ereignissen zugeordnet.  Z. B. das KeyDown-Ereignis zugeordnet ist die <xref:System.Windows.Input.Keyboard.KeyDown> und <xref:System.Windows.Input.Keyboard.PreviewKeyDown> Ereignisse.  Der Unterschied zwischen diesen Ereignissen ist, wie an das Zielelement weitergeleitet werden.  Vorschauereignisse tunneln die Elementstruktur vom Stammelement hinunter zum Zielelement.  Bubbling-Ereignisse übergeben vom Zielelement an das Stammelement.  Das Ereignisrouting in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird ausführlicher unten in dieser Übersicht und unter der [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md) behandelt.  
  
### <a name="keyboard-and-mouse-classes"></a>Tastatur- und Mausklassen  
 Zusätzlich zu den Eingaben [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] Basiselement-Klassen, die <xref:System.Windows.Input.Keyboard> Klasse und <xref:System.Windows.Input.Mouse> Klassen bieten zusätzliche [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] für die Arbeit mit Tastatur- und Mauseingaben.  
  
 Beispiele für die Eingabe [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] auf die <xref:System.Windows.Input.Keyboard> Klasse werden die <xref:System.Windows.Input.Keyboard.Modifiers%2A> Eigenschaft, die zurückgibt der <xref:System.Windows.Input.ModifierKeys> derzeit gedrückt, und die <xref:System.Windows.Input.Keyboard.IsKeyDown%2A> -Methode, die bestimmt, ob eine angegebene Taste gedrückt wird.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Input.Keyboard.GetKeyStates%2A> Methode, um festzustellen, wo eine <xref:System.Windows.Input.Key> im gedrückten Zustand ist.  
  
 [!code-csharp[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyArgsSnippetSample/CSharp/Window1.xaml.cs#keyeventargskeyboardgetkeystates)]
 [!code-vb[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyArgsSnippetSample/visualbasic/window1.xaml.vb#keyeventargskeyboardgetkeystates)]  
  
 Beispiele für die Eingabe [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] auf die <xref:System.Windows.Input.Mouse> -Klasse sind <xref:System.Windows.Input.Mouse.MiddleButton%2A>, dem der Zustand der mittleren Maustaste abruft und <xref:System.Windows.Input.Mouse.DirectlyOver%2A>, derzeit über ist dem Mauszeiger auf dem Element abgerufen.  
  
 Im folgenden Beispiel wird ermittelt, ob die <xref:System.Windows.Input.Mouse.LeftButton%2A> auf die Maus ist der <xref:System.Windows.Input.MouseButtonState.Pressed> Zustand.  
  
 [!code-csharp[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MouseRelatedSnippets/CSharp/Window1.xaml.cs#mouserelatedsnippetsgetleftbuttonmouse)]
 [!code-vb[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MouseRelatedSnippets/visualbasic/window1.xaml.vb#mouserelatedsnippetsgetleftbuttonmouse)]  
  
 Die <xref:System.Windows.Input.Mouse> und <xref:System.Windows.Input.Keyboard> Klassen werden im weiteren Verlauf dieser Übersicht behandelt.  
  
### <a name="stylus-input"></a>Stifteingabe  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt über eine integrierte Unterstützung für die <xref:System.Windows.Input.Stylus>.  Die <xref:System.Windows.Input.Stylus> ist eine beliebte von vorgenommen Stifteingabe der [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)].  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen können den Stift als Maus behandeln, indem Sie die Maus-[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] verwenden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] macht jedoch auch eine Stift-Gertäteabstraktion verfügbar, die ein Modell ähnlich der Tastatur und der Maus verwendet.  Alle dem Stift zugehörigen [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] enthalten den Begriff „Stylus“ (Stift oder Tablettstift).  
  
 Da der Stift als Maus fungieren kann, können Anwendungen, die nur die Mauseingabe unterstützen, noch immer ein gewisses Maß an automatischer Unterstützung für den Stift erhalten. Wenn der Stift auf diese Weise verwendet wird, bekommt die Anwendung die Gelegenheit, das entsprechende Stiftereignis zu behandeln und behandelt dann das entsprechende Mausereignis. Darüber hinaus sind Dienste auf höherer Ebene (z.B. Freihandeingabe) noch immer über die Stift-Geräteabstraktion verfügbar.  Weitere Informationen zur Freihandeingabe finden Sie unter [Erste Schritte mit Freihandeingaben](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).  
  
<a name="event_routing"></a>   
## <a name="event-routing"></a>Ereignisrouting  
 Ein <xref:System.Windows.FrameworkElement> kann andere Elemente als untergeordnete Elemente im Inhaltsmodell, bilden eine Struktur mit Elementen enthalten.  Durch die Übergabe von Ereignissen kann das übergeordnete Element in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in der Eingabe teilnehmen, die an dessen untergeordnetes Element oder andere indirekt untergeordnete Elemente weitergeleitet wird. Dies ist besonders nützlich, um Steuerelemente aus kleineren Steuerelementen zu erstellen. Dieser Prozess wird als „Zusammensetzung von Steuerelementen“ oder „Zusammensetzen“ bezeichnet. Weitere Informationen über Elementstrukturen und wie sich Elementstrukturen auf Ereignisrouten beziehen, finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 Das Ereignisrouting ist der Prozess, in dem Ereignisse an mehrere Elemente weitergeleitet werden, sodass ein bestimmtes Objekt oder Element entlang der Route einem Ereignis eine signifikante Antwort (durch Behandlung) anbieten kann, die sonst von einem anderen Element hätte stammen können.  Routingereignisse verwenden einen von drei Routingmechanismen: direkt, Bubbling und Tunneln.  Beim direkten Routing ist das Quellelement das einzige benachrichtigte Element, und das Ereignis wird nicht an andere Elemente weitergeleitet. Das direkte Routingereignis bietet jedoch noch einige zusätzliche Funktionen, die im Gegensatz zu [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Standardereignissen nur für Routingereignisse vorhanden sind. Bubbling arbeitet sich in der Elementstruktur nach oben, indem zuerst das Element benachrichtigt wird, von dem das Ereignis stammt, und anschließend das übergeordnete Element usw.  Tunneling beginnt am Stamm der Elementstruktur, arbeitet sich nach unten und endet mit dem ursprünglichen Quellelement.  Weitere Informationen zu Routingereignissen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabeereignisse treten generell in Paaren auf, die aus einem Tunneling-Ereignis und einem Bubbling-Ereignis bestehen.  Tunneling-Ereignisse unterscheiden sich von Bubbling-Ereignissen im Präfix „Preview“.  Z. B. <xref:System.Windows.Input.Mouse.PreviewMouseMove> ist eine Mauszeigerposition ausgelöste Ereignis die Tunneling-Version und <xref:System.Windows.Input.Mouse.MouseMove> ist die bubbling-Version dieses Ereignisses. Diese Ereignispaarung ist eine Konvention, die auf der Elementebene implementiert ist, und keine inhärente Funktion des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignissystems, Weitere Informationen finden Sie im Abschnitt „Eingabeereignisse in WPF“ in [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="handling_input_events"></a>   
## <a name="handling-input-events"></a>Behandeln von Eingabeereignissen  
 Um Eingaben für ein Element zu erhalten, muss ein Ereignishandler mit diesem speziellen Ereignis verknüpft sein.  In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist dies einfach: Sie verweisen auf den Namen des Ereignisses als ein Attribut des Elements, das für dieses Ereignis überwacht.  Legen Sie anschließend den Wert des Attributs auf den Namen des Ereignishandlers, den Sie basierend auf einen Delegaten definieren, fest.  Der Ereignishandler im Code, wie z. B. c# geschrieben werden muss und in einer Code-Behind-Datei enthalten sein kann.  
  
 Tastaturereignisse treten auf, wenn das Betriebssystem Tastaturaktionen meldet, die auftreten, während sich der Tastaturfokus auf einem Element befindet. Maus- und Stiftereignisse lassen sich in zwei Kategorien unterteilen: Ereignisse, die Änderungen der Zeigerposition relativ zum Element melden sowie Ereignisse, die Änderungen im Status der Geräteschaltflächen melden.  
  
### <a name="keyboard-input-event-example"></a>Beispiel eines Tastatureingabeereignisses  
 Das folgende Beispiel überwacht das Drücken der Nach-Links-Taste.  Ein <xref:System.Windows.Controls.StackPanel> wird erstellt, verfügt über eine <xref:System.Windows.Controls.Button>.  Ein Ereignishandler überwacht das Drücken der nach-links-Taste angefügt ist die <xref:System.Windows.Controls.Button> Instanz.  
  
 Der erste Abschnitt des Beispiels erstellt die <xref:System.Windows.Controls.StackPanel> und <xref:System.Windows.Controls.Button> und fügt den Ereignishandler für die <xref:System.Windows.UIElement.KeyDown>.  
  
 [!code-xaml[InputOvw#Input_OvwKeyboardExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwkeyboardexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexampleuicodebehind)]  
  
 Der zweite Abschnitt ist in Code geschrieben und definiert den Ereignishandler.  Wenn die nach-links-Taste gedrückt wird und die <xref:System.Windows.Controls.Button> Tastaturfokus hat, der Handler ausgeführt und die <xref:System.Windows.Controls.Control.Background%2A> Farbe der <xref:System.Windows.Controls.Button> geändert wird.  Wenn die Taste gedrückt wird, aber es nicht die links-Taste ist, die <xref:System.Windows.Controls.Control.Background%2A> Farbe der <xref:System.Windows.Controls.Button> wieder in die Anfangsfarbe geändert wird.  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexamplehandlercodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexamplehandlercodebehind)]  
  
### <a name="mouse-input-event-example"></a>Beispiel für Mauseingabeereignisse  
 Im folgenden Beispiel die <xref:System.Windows.Controls.Control.Background%2A> Farbe ein <xref:System.Windows.Controls.Button> wird geändert, wenn der Mauszeiger wird die <xref:System.Windows.Controls.Button>.  Die <xref:System.Windows.Controls.Control.Background%2A> Farbe wird wiederhergestellt, wenn der Mauszeiger den Bereich verlässt den <xref:System.Windows.Controls.Button>.  
  
 Der erste Abschnitt des Beispiels erstellt die <xref:System.Windows.Controls.StackPanel> und die <xref:System.Windows.Controls.Button> steuern und fügt die Ereignishandler für die <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave> Ereignisse an die <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[InputOvw#Input_OvwMouseExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwmouseexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleuicodebehind)]  
  
 Der zweite Abschnitt des Beispiels wird in Code geschrieben und definiert die Ereignishandler.  Wenn die Maus bewegt wird die <xref:System.Windows.Controls.Button>, die <xref:System.Windows.Controls.Control.Background%2A> Farbe der <xref:System.Windows.Controls.Button> geändert wird, um <xref:System.Windows.Media.Brushes.SlateGray%2A>.  Wenn die Maus bewegt wird die <xref:System.Windows.Controls.Button>, die <xref:System.Windows.Controls.Control.Background%2A> Farbe der <xref:System.Windows.Controls.Button> geändert wird, zurück an <xref:System.Windows.Media.Brushes.AliceBlue%2A>.  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleeneterhandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleeneterhandler)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleleavehandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleleavehandler)]  
  
<a name="text_input"></a>   
## <a name="text-input"></a>Texteingabe  
 Die <xref:System.Windows.ContentElement.TextInput> Ereignis ermöglicht es Ihnen, die Texteingabe auf eine Weise geräteunabhängige überwachen. Die Tastatur dient primär der Texteingabe, jedoch können Sie auch durch die Sprache, handschriftlich oder mit anderen Eingabegeräten Texteingabe generieren.  
  
 Für die Tastatureingabe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zuerst sendet die entsprechende <xref:System.Windows.ContentElement.KeyDown> / <xref:System.Windows.ContentElement.KeyUp> Ereignisse. Wenn diese Ereignisse nicht behandelt werden, und der Schlüssel Text anstatt (z. B. Richtungspfeile eine STRG-Taste) oder Funktionstasten wird ein <xref:System.Windows.ContentElement.TextInput> Ereignis wird ausgelöst.  Es ist nicht immer eine einfache Zuordnung zwischen <xref:System.Windows.ContentElement.KeyDown> / <xref:System.Windows.ContentElement.KeyUp> und <xref:System.Windows.ContentElement.TextInput> Ereignisse, da mehrere Tastatureingaben ein einzelnes Zeichen der Texteingabe und einzelne Tastatureingaben können mit mehreren Zeichen generieren Zeichenfolgen.  Dies gilt insbesondere für Sprachen wie Chinesisch, Japanisch und Koreanisch die [!INCLUDE[TLA#tla_ime#plural](../../../../includes/tlasharptla-imesharpplural-md.md)] zum Generieren von Tausenden von möglichen Zeichen in ihrem jeweiligen Alphabet verwenden.  
  
 Wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sendet eine <xref:System.Windows.ContentElement.KeyUp> / <xref:System.Windows.ContentElement.KeyDown> Ereignis <xref:System.Windows.Input.KeyEventArgs.Key%2A> auf festgelegt ist <xref:System.Windows.Input.Key.System?displayProperty=nameWithType> , wenn die Tastatureingaben Teil zugegriffen werden können eine <xref:System.Windows.ContentElement.TextInput> Ereignisses (Wenn z. B. ALT + S gedrückt wird). Dies ermöglicht es Code in einem <xref:System.Windows.ContentElement.KeyDown> -Ereignishandler zu suchende <xref:System.Windows.Input.Key.System?displayProperty=nameWithType> und, falls gefunden, lassen Sie die Verarbeitung für den Handler, der anschließend erhöhten <xref:System.Windows.ContentElement.TextInput> Ereignis. In diesen Fällen werden die verschiedenen Eigenschaften der <xref:System.Windows.Input.TextCompositionEventArgs> Argument kann verwendet werden, um die ursprünglichen Tastatureingaben zu ermitteln. Auf ähnliche Weise, wenn ein [!INCLUDE[TLA2#tla_ime](../../../../includes/tla2sharptla-ime-md.md)] aktiv ist, <xref:System.Windows.Input.Key> hat den Wert der <xref:System.Windows.Input.Key.ImeProcessed?displayProperty=nameWithType>, und <xref:System.Windows.Input.KeyEventArgs.ImeProcessedKey%2A> gibt die Tastenkombination oder die Tastatureingaben.  
  
 Das folgende Beispiel definiert einen Handler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis und einen Handler für das <xref:System.Windows.UIElement.KeyDown> Ereignis.  
  
 Das erste Segment des Codes oder Markups erstellt die Benutzeroberfläche.  
  
 [!code-xaml[InputOvw#Input_OvwTextInputXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwtextinputxaml)]  
  
 [!code-csharp[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputuicodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputuicodebehind)]  
  
 Das zweite Segment des Codes enthält die Ereignishandler.  
  
 [!code-csharp[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputhandlerscodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputhandlerscodebehind)]  
  
 Da der Ereignisroute Eingabeereignisse Bubbling die <xref:System.Windows.Controls.StackPanel> die Eingabe, unabhängig davon, welches Element den Tastaturfokus, erhält. Die <xref:System.Windows.Controls.TextBox> Steuerelement wird zuerst benachrichtigt, und die `OnTextInputKeyDown` Handler wird aufgerufen, wenn nur die <xref:System.Windows.Controls.TextBox> hat nicht die Eingabe verarbeitet. Wenn die <xref:System.Windows.UIElement.PreviewKeyDown> wird verwendet, statt die <xref:System.Windows.UIElement.KeyDown> -Ereignis der `OnTextInputKeyDown` Handler wird zuerst aufgerufen.  
  
 In diesem Beispiel wird die Behandlungslogik zweimal geschrieben: einmal für STRG+O und nochmal für das Click-Ereignis der Schaltfläche. Anstatt die Eingabeereignisse direkt zu behandeln, können Sie dies mithilfe von Befehlen vereinfachen.  Befehle werden in dieser Übersicht unter [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md) erläutert.  
  
<a name="touch_and_manipulation"></a>   
## <a name="touch-and-manipulation"></a>Fingereingabe (Touch) und-Bearbeitung  
 Neue Hardware und API im Windows 7-Betriebssystem bieten Anwendungen die Möglichkeit, Eingabe von mehreren Berührungen gleichzeitig zu erhalten. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht Anwendungen, Fingereingabe zu erkennen und ähnlich wie auf andere Eingabe zu reagieren, z.B. von einer Maus oder einer Tastatur, durch Auslösen von Ereignissen, wenn eine Fingereingabe erfolgt.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] macht zwei Typen von Ereignissen verfügbar, wenn eine Fingereingabe erfolgt: Berührungsereignisse und Bearbeitungsereignisse. Berührungsereignisse stellen Rohdaten zu jedem Finger auf einem Touchscreen und seiner Bewegung bereit. Bearbeitungsereignisse interpretieren die Eingabe als bestimmte Aktionen. Beide Typen von Ereignissen werden in diesem Abschnitt erläutert.  
  
### <a name="prerequisites"></a>Erforderliche Komponenten  
 Sie benötigen die folgenden Komponenten zur Entwicklung einer Anwendung, die auf Fingereingabe reagiert.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]  
  
-   Windows 7  
  
-   Ein Gerät, z.B. ein Touchscreen, das Windows Touch unterstützt  
  
### <a name="terminology"></a>Terminologie  
 Die folgenden Begriffe werden verwendet, wenn die Fingereingabe behandelt wird.  
  
-   **Touch (Fingereingabe)** ist ein Typ von Benutzereingabe, der von Windows 7 erkannt wird. In der Regel wird die Fingereingabe initiiert, indem ein berührungsempfindlicher Bildschirm mit Fingern berührt wird. Beachten Sie, dass Geräte wie Touchpads, die auf Laptops gang und gäbe sind, keine Fingereingabe unterstützen, wenn das Gerät lediglich die Position und die Bewegung des Fingers als Mauseingabe konvertiert.  
  
-   **Multitouch (Mehrfingereingabe)** ist Berührung, die gleichzeitig von mehreren Punkten erfolgt. Windows 7 und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützen die Mehrfingereingabe. Wann immer die Fingereingabe in der Dokumentation für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erläutert wird, gelten die Konzepte auch für die Mehrfingereingabe.  
  
-   Ein **Manipulation** tritt auf, wenn die Berührung als physische Aktion interpretiert wird, die auf ein Objekt angewendet wird. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] interpretieren Bearbeitungsereignisse die Eingabe als Übersetzungs-, Erweiterungs- und Drehungsmanipualtion.  
  
-   Ein `touch device` stellt ein Gerät dar, das Fingereingabe erzeugt, z.B. ein einzelner Finger auf einem Touchscreen.  
  
### <a name="controls-that-respond-to-touch"></a>Steuerelemente, die auf Fingereingabe reagieren  
 Die folgenden Steuerelemente können gescrollt werden, wenn Sie über Inhalt verfügen, der sich außerhalb der Ansicht befindet, indem Sie mit einem Finger über die Steuerelemente wischen.  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.DataGrid>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
 Die <xref:System.Windows.Controls.ScrollViewer> definiert die <xref:System.Windows.Controls.ScrollViewer.PanningMode%2A?displayProperty=nameWithType> -Eigenschaft, die es Ihnen die ermöglicht Angabe, ob Touch Schwenken aktiviert ist horizontal, vertikal, beides oder keines von beiden. Die <xref:System.Windows.Controls.ScrollViewer.PanningDeceleration%2A?displayProperty=nameWithType> Eigenschaft gibt an, wie schnell sich der Bildlauf verlangsamt, wenn der Benutzer den Finger vom Touchscreen hebt. Die <xref:System.Windows.Controls.ScrollViewer.PanningRatio%2A?displayProperty=nameWithType> angefügte Eigenschaft gibt das Verhältnis zum Durchführen eines Bildlaufs Manipulation Offset übersetzt.  
  
### <a name="touch-events"></a>Berührungsereignisse  
 Die Basisklassen <xref:System.Windows.UIElement>, <xref:System.Windows.UIElement3D>, und <xref:System.Windows.ContentElement>, definieren Ereignisse, die Sie abonnieren können, damit Ihre Anwendung auf Fingereingabe reagiert. Berührungsereignisse sind nützlich, wenn Ihre Anwendung Fingereingabe als etwas anderes als die Bearbeitung eines Objekts interpretiert. Beispielsweise würde eine Anwendung, mit der ein Benutzer mit einem oder mehreren Fingern zeichnen kann, Berührungsereignisse abonnieren.  
  
 Alle drei Klassen definieren die folgenden Ereignisse, die sich ähnlich verhalten, unabhängig von der definierenden Klasse.  
  
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
  
 Wie die Tastatur- und Maus-Ereignisse sind die Berührungsereignisse Routingereignisse. Die Ereignisse, die mit `Preview` beginnen, sind Tunneling-Ereignisse, und die Ereignisse, die mit `Touch` beginnen, sind Bubbling-Ereignisse. Weitere Informationen zu Routingereignissen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md). Wenn Sie diese Ereignisse behandeln, erhalten Sie die Position der Eingabe, relativ zum beliebiges Element durch Aufrufen der <xref:System.Windows.Input.TouchEventArgs.GetTouchPoint%2A> oder <xref:System.Windows.Input.TouchEventArgs.GetIntermediateTouchPoints%2A> Methode.  
  
 Um die Interaktion zwischen Berührungsereignissen zu verstehen, denken Sie an das Szenario, bei dem ein Benutzer einen Finger auf ein Element legt, den Finger im Element bewegt und anschließend den Finger vom Element wegnimmt. Die folgende Abbildung zeigt die Ausführung der Bubbling-Ereignisse (die Tunneling-Ereignisse werden der Einfachheit halber ausgelassen).  
  
 ![Die Reihenfolge der Berührungsereignisse. ] (../../../../docs/framework/wpf/advanced/media/ndp-touchevents.png "NDP_TouchEvents")  
Berührungsereignisse  
  
 Die folgende Liste beschreibt die Abfolge der Ereignisse in der vorherigen Abbildung.  
  
1.  Die <xref:System.Windows.UIElement.TouchEnter> Ereignis tritt auf, wenn der Benutzer einen Finger auf das Element legt, einmal.  
  
2.  Die <xref:System.Windows.UIElement.TouchDown> Ereignis tritt einmal auf.  
  
3.  Die <xref:System.Windows.UIElement.TouchMove> Ereignis tritt auf, mehrmals aus, wenn der Benutzer den Finger innerhalb des Elements bewegt.  
  
4.  Die <xref:System.Windows.UIElement.TouchUp> Ereignis tritt auf, wenn der Benutzer den Finger vom Element hebt, einmal.  
  
5.  Die <xref:System.Windows.UIElement.TouchLeave> Ereignis tritt einmal auf.  
  
 Wenn mehr als zwei Finger verwendet werden, treten die Ereignisse für jeden Finger auf.  
  
### <a name="manipulation-events"></a>Bearbeitungsereignisse  
 Für Fälle, die einer Anwendung ermöglicht, in denen einen Benutzer ein Objekt, das Bearbeiten der <xref:System.Windows.UIElement> Klasse definiert Bearbeitungsereignisse. Im Gegensatz zu den Berührungsereignissen, die einfach die Position der Berührung melden, melden die Bearbeitungsereignisse, wie die Eingabe interpretiert werden kann. Es gibt drei Arten von Manipulationen, Übersetzung, Erweiterung und Drehung. Die folgende Liste beschreibt, wie die drei Typen von Manipulationen aufgerufen werden.  
  
-   Legen Sie einen Finger auf ein Objekt, und verschieben Sie den Finger über den Touchscreen, um eine Übersetzungsmanipulation aufzurufen. Dadurch wird in der Regel das Objekt verschoben.  
  
-   Legen Sie zwei Finger auf ein Objekt, und bewegen Sie die Finger näher zusammen oder weiter auseinander, um eine Erweiterungsmanipulation aufzurufen. Dadurch wird in der Regel die Größe des Objekts geändert.  
  
-   Legen Sie zwei Finger auf ein Objekt, und drehen Sie einen Finger um den jeweils anderen um eine Drehungsmanipulation aufzurufen. Dadurch wird in der Regel das Objekt gedreht.  
  
 Es kann mehr als eine Manipulation gleichzeitig geschehen.  
  
 Wenn Sie Objekte dazu bringen, auf Manipulationen anzusprechen, können Sie erreichen, dass das Objekt verzögert wird. Dadurch kann Ihr Objekt die physische Welt simulieren. Wenn Sie z.B. ein Buch über einen Tisch schieben, dann bewegt sich das Buch nach dem Loslassen weiter voran, wenn Sie nur kräftig genug anschieben. Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie dieses Verhalten übernehmen, indem Sie Bearbeitungsereignisse auslösen,nachdem der Benutzer das Objekt losgelassen hat.  
  
 Informationen dazu, wie Sie eine Anwendung erstellen, mit der ein Benutzer ein Objekt bewegen, drehen und dessen Größe verändern kann, finden Sie unter [Exemplarische Vorgehensweise: Erstellen der ersten Fingereingabeanwendung](../../../../docs/framework/wpf/advanced/walkthrough-creating-your-first-touch-application.md).  
  
 Die <xref:System.Windows.UIElement> definiert die folgenden Bearbeitungsereignisse.  
  
-   <xref:System.Windows.UIElement.ManipulationStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationStarted>  
  
-   <xref:System.Windows.UIElement.ManipulationDelta>  
  
-   <xref:System.Windows.UIElement.ManipulationInertiaStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationCompleted>  
  
-   <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>  
  
 Wird standardmäßig ein <xref:System.Windows.UIElement> empfängt diese Bearbeitungsereignisse nicht. Zum Empfangen von Manipulationsereignisse auf eine <xref:System.Windows.UIElement>legen <xref:System.Windows.UIElement.IsManipulationEnabled%2A?displayProperty=nameWithType> auf `true`.  
  
#### <a name="the-execution-path-of-manipulation-events"></a>Der Ausführungspfad von Bearbeitungsereignissen  
 Denken Sie an ein Szenario, in dem ein Benutzer ein Objekt „wirft“. Der Benutzer legt einen Finger auf das Objekt, bewegt den Finger etwas über den Touchscreen und hebt dann in der Bewegung den Finger. Dadurch bewegt sich das Objekt unter dem Finger des Benutzers und bewegt sich dann noch weiter, wenn der Benutzer den Finger hebt.  
  
 Die folgende Abbildung zeigt den Ausführungspfad von Bearbeitungsereignissen und wichtige Informationen zu jedem Ereignis.  
  
 ![Die Reihenfolge der Bearbeitungsereignisse. ] (../../../../docs/framework/wpf/advanced/media/ndp-manipulationevents.png "NDP_ManipulationEvents")  
Bearbeitungsereignisse  
  
 Die folgende Liste beschreibt die Abfolge der Ereignisse in der vorherigen Abbildung.  
  
1.  Die <xref:System.Windows.UIElement.ManipulationStarting> Ereignis tritt auf, wenn der Benutzer für das Objekt einen Finger platziert. Dieses Ereignis unter anderem können Sie festlegen der <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> Eigenschaft. In den nachfolgenden Ereignissen werden relativ zu die Position der Manipulation der <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>. In anderen Ereignissen als <xref:System.Windows.UIElement.ManipulationStarting>, diese Eigenschaft ist schreibgeschützt, sodass der <xref:System.Windows.UIElement.ManipulationStarting> Ereignis ist das einzige Mal, die diese Eigenschaft festgelegt werden können.  
  
2.  Die <xref:System.Windows.UIElement.ManipulationStarted> Ereignis tritt auf, weiter. Dieses Ereignis meldet den Ursprung der Manipulation.  
  
3.  Die <xref:System.Windows.UIElement.ManipulationDelta> Ereignis tritt auf, mehrmals als ein Benutzer Finger auf einem Touchscreen bewegen. Die <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> Eigenschaft von der <xref:System.Windows.Input.ManipulationDeltaEventArgs> -Klasse meldet, ob die Bearbeitung als Drehung, Erweiterung oder Verschiebung interpretiert wird. Hier können Sie die meisten Bearbeitungen an einem Objekt durchführen.  
  
4.  Die <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis tritt auf, wenn der Benutzer Finger Kontakt mit dem Objekt unterbrochen. Mit diesem Ereignis können Sie die Verlangsamung der Bearbeitungen während der Verzögerung angeben. So kann Ihr Objekt unterschiedliche physikalische Bereiche oder Attribute Ihrer Wahl emulieren. Nehmen wir beispielsweise an, Ihre Anwendung enthält zwei Objekte, die Elemente in der realen Welt darstellen, und eines massiger als das andere ist. Sie können veranlassen, dass das massige Objekt schneller verlangsamt wird als das leichtere Objekt  
  
5.  Die <xref:System.Windows.UIElement.ManipulationDelta> Ereignis tritt auf, mehrmals aus, wie Trägheit auftritt. Beachten Sie, dass dieses Ereignis auftritt, wenn der Benutzer seine Finger über den Touchscreen bewegt, und wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Verzögerung simuliert. Das heißt, <xref:System.Windows.UIElement.ManipulationDelta> tritt vor und nach der <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis. Die <xref:System.Windows.Input.ManipulationDeltaEventArgs.IsInertial%2A?displayProperty=nameWithType> -Eigenschaft Berichten, ob die <xref:System.Windows.UIElement.ManipulationDelta> Ereignis tritt auf, während der Trägheit, daher können Sie diese Eigenschaft überprüfen und Ausführen von verschiedenen Aktionen, basierend auf dessen Wert.  
  
6.  Die <xref:System.Windows.UIElement.ManipulationCompleted> Ereignis tritt auf, wenn die Bearbeitung und alle Trägheit endet. Das heißt, nachdem alle der <xref:System.Windows.UIElement.ManipulationDelta> Ereignisse auftreten, die <xref:System.Windows.UIElement.ManipulationCompleted> Ereignis tritt auf, um zu signalisieren, dass die Bearbeitung abgeschlossen ist.  
  
 Die <xref:System.Windows.UIElement> definiert außerdem die <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Ereignis. Dieses Ereignis tritt auf, wenn die <xref:System.Windows.Input.ManipulationDeltaEventArgs.ReportBoundaryFeedback%2A> Methode wird aufgerufen, dem <xref:System.Windows.UIElement.ManipulationDelta> Ereignis. Die <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Ereignis ermöglicht, Anwendungen oder Komponenten visuelles Feedback bereitstellen, wenn ein Objekt eine Grenze erreicht. Z. B. die <xref:System.Windows.Window> -Klasse behandelt die <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Ereignis dazu führen, dass das Fenster, leicht zu wechseln, wenn der Rand erreicht wird.  
  
 Brechen Sie die Bearbeitung durch Aufrufen der <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> -Methode für die Ereignisargumente in jedem Fall Manipulation außer <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Ereignis. Beim Aufruf <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A>, die Bearbeitungsereignisse nicht mehr ausgelöst werden und Mausereignisse treten für Touch. Die folgende Tabelle beschreibt die Beziehung zwischen dem Zeitpunkt, an dem die Bearbeitung abgebrochen wird, und den Mausereignissen, die auftreten.  
  
|Das Ereignis zum Abbruch, das aufgerufen wird|Die Mausereignisse, die für die Eingabe auftreten, die bereits aufgetreten sind|  
|----------------------------------------|-----------------------------------------------------------------|  
|<xref:System.Windows.UIElement.ManipulationStarting> und <xref:System.Windows.UIElement.ManipulationStarted>|Ereignisse mit gedrückter Maustaste|  
|<xref:System.Windows.UIElement.ManipulationDelta>|Ereignisse mit gedrückter Maustaste und beim Verschieben der Maus|  
|<xref:System.Windows.UIElement.ManipulationInertiaStarting> und <xref:System.Windows.UIElement.ManipulationCompleted>|Ereignisse mit gedrückter Maustaste, beim Verschieben der Maus und beim Loslassen der Maustaste|  
  
 Beachten Sie, dass beim Aufrufen <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> bei der Bearbeitung in Trägheit ist, gibt die Methode `false` und die Eingabe keine Mausereignisse auslöst.  
  
### <a name="the-relationship-between-touch-and-manipulation-events"></a>Die Beziehung zwischen Berührungs- und Bearbeitungsereignissen  
 Ein <xref:System.Windows.UIElement> immer Touch-Ereignisse empfangen werden können. Wenn die <xref:System.Windows.UIElement.IsManipulationEnabled%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.UIElement> berührungs- und Bearbeitungsereignissen Ereignisse empfangen werden können.  Wenn die <xref:System.Windows.UIElement.TouchDown> Ereignis nicht behandelt wird (d. h. die <xref:System.Windows.RoutedEventArgs.Handled%2A> Eigenschaft ist `false`), die Manipulation Logik erfasst die Fingereingabe auf das Element, und generiert die Bearbeitungsereignisse. Wenn die <xref:System.Windows.RoutedEventArgs.Handled%2A> -Eigenschaftensatz auf `true` in die <xref:System.Windows.UIElement.TouchDown> Ereignis, das Manipulation Logik generiert keine Bearbeitungsereignisse. Die folgende Abbildung zeigt die Beziehung zwischen Berührungs- und Bearbeitungsereignissen.  
  
 ![Beziehung zwischen berührungs-und Bearbeitungsereignissen](../../../../docs/framework/wpf/advanced/media/ndp-touchmanipulateevents.png "NDP_TouchManipulateEvents")  
Berührungs-und Bearbeitungsereignisse  
  
 Die folgende Liste beschreibt die Beziehung zwischen Berührungs- und Bearbeitungsereignissen, die in der folgenden Abbildung dargestellt ist.  
  
-   Wenn das erste Touch Gerät generiert eine <xref:System.Windows.UIElement.TouchDown> Ereignis auf einer <xref:System.Windows.UIElement>, ruft die Manipulation der <xref:System.Windows.UIElement.CaptureTouch%2A> -Methode, die generiert die <xref:System.Windows.UIElement.GotTouchCapture> Ereignis.  
  
-   Wenn die <xref:System.Windows.UIElement.GotTouchCapture> auftritt, ruft die Manipulation der <xref:System.Windows.Input.Manipulation.AddManipulator%2A?displayProperty=nameWithType> -Methode, die generiert die <xref:System.Windows.UIElement.ManipulationStarting> Ereignis.  
  
-   Wenn die <xref:System.Windows.UIElement.TouchMove> Ereignisse auftreten, generiert die Bearbeitungslogik der <xref:System.Windows.UIElement.ManipulationDelta> Ereignisse, die vor dem Auftreten der <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis.  
  
-   Wenn die letzte touch-Geräte auf das Element löst die <xref:System.Windows.UIElement.TouchUp> Ereignis, das Manipulation Logik generiert die <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis.  
  
<a name="focus"></a>   
## <a name="focus"></a>Fokus  
 Es gibt zwei Hauptkonzepte, die den Fokus in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] betreffen: Tastaturfokus und logischer Fokus.  
  
### <a name="keyboard-focus"></a>Tastaturfokus  
 Der Tastaturfokus bezieht sich auf das Element, das Tastatureingaben empfängt.  Es kann nur ein Element auf dem gesamten Desktop geben, das über den Tastaturfokus verfügt.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], weist das Element, das über den Tastaturfokus verfügt <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> festgelegt `true`.  Die statische <xref:System.Windows.Input.Keyboard> Methode <xref:System.Windows.Input.Keyboard.FocusedElement%2A> gibt das Element, das derzeit über den Tastaturfokus verfügt.  
  
 Über den Tastaturfokus abgerufen werden kann, durch die TAB-Taste auf ein Element oder durch Klicken mit der Maus auf bestimmte Elemente, wie z. B. eine <xref:System.Windows.Controls.TextBox>.  Über den Tastaturfokus kann auch programmgesteuert mithilfe von abgerufen werden die <xref:System.Windows.Input.Keyboard.Focus%2A> Methode für die <xref:System.Windows.Input.Keyboard> Klasse.  <xref:System.Windows.Input.Keyboard.Focus%2A> versucht, das angegebene Element den Tastaturfokus erhalten.  Das von zurückgegebene Element <xref:System.Windows.Input.Keyboard.Focus%2A> ist das Element, das derzeit über den Tastaturfokus verfügt.  
  
 In der Reihenfolge nach einem Element den Tastaturfokus erhalten die <xref:System.Windows.UIElement.Focusable%2A> Eigenschaft und die <xref:System.Windows.UIElement.IsVisible%2A> Eigenschaften müssen festgelegt werden, um **"true"**.  Einige Klassen, z. B. <xref:System.Windows.Controls.Panel>, haben <xref:System.Windows.UIElement.Focusable%2A> festgelegt `false` standardmäßig; aus diesem Grund müssen unter Umständen zum Festlegen dieser Eigenschaft `true` ggf. für dieses Element den Fokus erhalten können.  
  
 Im folgenden Beispiel wird <xref:System.Windows.Input.Keyboard.Focus%2A> festzulegende über den Tastaturfokus auf eine <xref:System.Windows.Controls.Button>.  Die empfohlene Anfangsfokus in einer Anwendung muss der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Weitere Informationen über den Tastaturfokus finden Sie unter [Fokus – Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
### <a name="logical-focus"></a>Logischer Fokus  
 Der logische Fokus bezieht sich auf die <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> in einem Fokusbereich.  Es können mehrere Elemente vorhanden sein, die über logischen Fokus in einer Anwendung verfügen, jedoch kann es nur ein Element geben, das den logischen Fokus in einem bestimmten Fokusbereich besitzt.  
  
 Ein Fokusbereich ist ein Containerelement, das verfolgt die <xref:System.Windows.Input.FocusManager.FocusedElement%2A> innerhalb dieses Bereichs.  Wenn der Fokus einen Fokusbereich verlässt, wird das Element den Tastaturfokus verlieren, jedoch behält es den logischen Fokus.  Wenn der Fokus zum Fokusbereich zurückkehrt, wird das Fokuselement Tastaturfokus erhalten.  Somit kann der Tastaturfokus zwischen mehreren Fokusbereichen geändert werden, aber es wird sichergestellt, dass das Fokuselement im Fokusbereich das Element bleibt, das über den Fokus verfügt, wenn dieser zurückgegeben wird.  
  
 Ein Element kann in einem Fokusbereich umgewandelt werden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] durch Festlegen der <xref:System.Windows.Input.FocusManager> angefügte Eigenschaft <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> auf `true`, oder in Code, indem Sie die angefügte Eigenschaft mit der <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> Methode.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.StackPanel> in einem Fokusbereich durch Festlegen der <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> -Eigenschaft.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 Klassen im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind die Fokusbereiche in der Standardeinstellung sind <xref:System.Windows.Window>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolBar>, und <xref:System.Windows.Controls.ContextMenu>.  
  
 Ein Element, das über den Tastaturfokus verfügt ist auch der logische Fokus für den Fokusbereich, der er angehört. aus diesem Grund Festlegen des Fokus auf ein Element mit der <xref:System.Windows.Input.Keyboard.Focus%2A> Methode auf die <xref:System.Windows.Input.Keyboard> Klasse oder die Basiselementklasse versucht, das Element den Tastaturfokus und den logischen Fokus zu erteilen.  
  
 Verwenden Sie zum Bestimmen der Fokuselement in einem Fokusbereich <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>. Verwenden Sie zum Ändern der Fokuselement für einen Fokusbereich <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>.  
  
 Weitere Informationen über den logischen Fokus finden Sie unter [Fokus – Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
<a name="mouse_position"></a>   
## <a name="mouse-position"></a>Mausposition  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabe-[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] stellt hilfreiche Informationen bezüglich Koordinatenbereichen bereit.  Zum Beispiel ist die Koordinate `(0,0)` die Koordinate oben links, aber von welchem Element in der Struktur? Das Element, das das Eingabeziel ist? Das Element, an das Sie Ihren Ereignishandler angefügt haben? Oder doch etwas anderes? Um Verwechslungen zu vermeiden erfordert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabe-[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], dass Sie Ihren Verweisrahmen angeben, wenn Sie mit Koordinaten arbeiten, die über die Maus aufgerufen werden. Die <xref:System.Windows.Input.Mouse.GetPosition%2A> Methode gibt die Koordinate des Mauszeigers relativ zum angegebenen Element zurück.  
  
<a name="mouse_capture"></a>   
## <a name="mouse-capture"></a>Mausaufzeichnung  
 Insbesondere Mausgeräte verfügen über modale Eigenschaften, die als Mausaufzeichnung bekannt sind. Die Mausaufzeichnung wird verwendet, um einen vorübergehenden Eingabestatus beizubehalten, wenn ein Drag & Drop-Vorgang gestartet wird, damit andere Vorgänge, einschließlich die nominale Position auf dem Bildschirm, nicht unbedingt auftreten. Während des Ziehens kann der Benutzer nicht klicken, ohne dass der Drag & Drop-Vorgang abgebrochen wird. Darum sind die meisten Mouseover-Cues nicht geeignet, während die Mausaufzeichnung durch die Drag-Quelle gehalten wird. Das Eingabesystem macht [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] verfügbar, was den Status der Mausaufzeichnung bestimmen kann, sowie [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], was die Mausaufzeichnung auf ein bestimmtes Element erzwingen oder den Status der Mausaufzeichnung löschen kann. Weitere Informationen zu Drag & Drop-Vorgängen finden Sie unter [Übersicht über Drag & Drop](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md).  
  
<a name="commands"></a>   
## <a name="commands"></a>Befehle  
 Befehle ermöglichen die Eingabebehandlung auf einer eher semantischeren Ebene als die Geräteeingabe.  Befehle sind einfache Direktive, wie etwa `Cut`, `Copy`, `Paste` oder `Open`.  Befehle sind nützlich für die Zentralisierung der Befehlslogik.  Denselben Befehl zugegriffen werden kann, aus einer <xref:System.Windows.Controls.Menu>auf eine <xref:System.Windows.Controls.ToolBar>, oder über eine Tastenkombination. Befehle stellen außerdem einen Mechanismus zum Deaktivieren von Steuerelementen bereit, wenn der Befehl nicht verfügbar ist.  
  
 <xref:System.Windows.Input.RoutedCommand> ist die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Implementierung von <xref:System.Windows.Input.ICommand>.  Wenn eine <xref:System.Windows.Input.RoutedCommand> ausgeführt wird, eine <xref:System.Windows.Input.CommandManager.PreviewExecuted> und ein <xref:System.Windows.Input.CommandManager.Executed> -Ereignis für das Befehlsziel, welche und aufwärts durch die Elementstruktur wie andere Eingaben ausgelöst werden.  Wenn ein Befehlsziel nicht festgelegt ist, wird das Element mit dem Tastaturfokus das Befehlsziel sein.  Die Logik, die den Befehl ausführt angefügt ist eine <xref:System.Windows.Input.CommandBinding>.  Wenn ein <xref:System.Windows.Input.CommandManager.Executed> Ereignis erreicht eine <xref:System.Windows.Input.CommandBinding> für diesen Befehl, der <xref:System.Windows.Input.ExecutedRoutedEventHandler> auf die <xref:System.Windows.Input.CommandBinding> aufgerufen wird.  Dieser Handler führt die Aktion des Befehls aus.  
  
 Weitere Informationen über Befehle finden Sie unter [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stellt eine Bibliothek von allgemeinen Befehlen besteht aus <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, und <xref:System.Windows.Documents.EditingCommands>, oder Sie können eigene definieren.  
  
 Im folgende Beispiel wird gezeigt, wie zum Einrichten einer <xref:System.Windows.Controls.MenuItem> , wenn darauf geklickt wird aufgerufen der <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl die <xref:System.Windows.Controls.TextBox>davon ausgegangen, dass die <xref:System.Windows.Controls.TextBox> über den Tastaturfokus verfügt.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
 Weitere Informationen über Befehle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="the_input_system_and_base_elements"></a>   
## <a name="the-input-system-and-base-elements"></a>Das Eingabesystem und die Basiselemente  
 Eingabeereignisse wie der angefügte Ereignisse definiert, die von der <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, und <xref:System.Windows.Input.Stylus> Klassen, die von der Eingabesystem ausgelöst und in einer bestimmten Position im Objektmodell basierend auf einem Treffertest der visuellen Struktur zur Laufzeit eingefügt werden.  
  
 Jedes der Ereignisse, die <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, und <xref:System.Windows.Input.Stylus> definieren ein angefügtes Ereignis auch von den Klassen Basiselement erneut zur Verfügung gestellt wird <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> als ein neues Routingereignis. Die Basiselement-Routingereignisse werden von Klassen generiert, die das ursprüngliche angefügte Ereignis behandeln und die Ereignisdaten wiederverwenden.  
  
 Wenn das Eingabeereignis einem bestimmten Quellelement durch seine Implementierung des Eingabeereignisses des Basiselements zugeordnet wird, kann es durch den Rest einer Ereignisroute weitergeleitet werden, die auf einer Kombination von logischen und visuellen Strukturobjekten basiert und vom Anwendungscode behandelt wird.  Im Allgemeinen ist es einfacher, verarbeiten diese gerätespezifischen Eingabeereignisse anhand der Routingereignisse für <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement>, da Sie eine intuitivere Ereignishandlersyntax sowohl in verwenden können [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und im Code. Sie könnten stattdessen das angefügte Ereignis behandeln, das den Prozess initiiert hat, jedoch würden Sie auf Probleme stoßen: das angefügte Ereignis kann möglicherweise durch die Behandlung der Basiselementklasse behandelt markiert werden, und Sie müssen Accessormethoden verwenden, anstatt die richtige Ereignissyntax, um Handler für angefügte Ereignisse anzufügen.  
  
<a name="whats_next"></a>   
## <a name="whats-next"></a>Weitere Informationen  
 Sie kennen nun verschiedene Methoden, um Eingabe in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu behandeln.  Sie sollten auch ein tieferes Verständnis der verschiedenen Typen von Eingabeereignissen und Routingereignismechanismen haben, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] genutzt werden.  
  
 Es gibt zusätzliche Ressourcen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Frameworkelemente und das Ereignisrouting detaillierter beschreiben. In den folgenden Übersichten finden Sie weitere Informationen: [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md), [Fokus – Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md), [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md), [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md) und [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Fokus - Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md)  
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [Eigenschaften](../../../../docs/framework/wpf/advanced/properties-wpf.md)
