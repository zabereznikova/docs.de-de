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
ms.openlocfilehash: 8fa9f2dd668efca6a3108973ff792cc17b37b410
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68818041"
---
# <a name="input-overview"></a>Übersicht über die Eingabe
<a name="introduction"></a>Das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Subsystem bietet eine leistungsstarke API zum Abrufen von Eingaben von einer Vielzahl von Geräten, einschließlich Maus, Tastatur, Fingereingabe und Tablettstift. In diesem Thema werden die Dienste beschrieben, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt werden sowie die Architektur des Eingabesystems.

<a name="input_api"></a>
## <a name="input-api"></a>Eingabe-API
 Die primäre Eingabe-API ist in den Basiselement Klassen enthalten: <xref:System.Windows.UIElement>, <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkElement>und <xref:System.Windows.FrameworkContentElement>.  Weitere Informationen zu den Basiselementen finden Sie unter [Übersicht über Basiselemente](base-elements-overview.md).  Diese Klassen bieten Funktionen für Eingabeereignisse, die im Zusammenhang mit Tastatureingaben, Maustasten, dem Mausrad, der Bewegung der Maus, der Fokusverwaltung und Mauseingabe stehen, um nur einige zu nennen. Durch das Platzieren der Eingabe-API für die Basiselemente, anstatt alle Eingabeereignisse als Dienst zu behandeln, ermöglicht die Eingabe Architektur, dass die Eingabeereignisse von einem bestimmten Objekt in der Benutzeroberfläche stammen und ein Ereignis Routing Schema unterstützen, bei dem mehr als ein Element über einen OPP verfügt. ortunity, um ein Eingabe Ereignis zu behandeln. Vielen Eingabeereignissen ist ein Paar von Ereignissen zugeordnet.  Beispielsweise ist das KeyDown-Ereignis dem-Ereignis <xref:System.Windows.Input.Keyboard.KeyDown> und <xref:System.Windows.Input.Keyboard.PreviewKeyDown> dem-Ereignis zugeordnet.  Der Unterschied zwischen diesen Ereignissen ist, wie an das Zielelement weitergeleitet werden.  Vorschauereignisse tunneln die Elementstruktur vom Stammelement hinunter zum Zielelement.  Bubbling-Ereignisse übergeben vom Zielelement an das Stammelement.  Das Ereignisrouting in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird ausführlicher unten in dieser Übersicht und unter der [Übersicht über Routingereignisse](routed-events-overview.md) behandelt.

### <a name="keyboard-and-mouse-classes"></a>Tastatur- und Mausklassen
 Zusätzlich zur Eingabe-API in den Basiselement Klassen stellen die- <xref:System.Windows.Input.Keyboard> Klasse und <xref:System.Windows.Input.Mouse> die-Klasse zusätzliche API für die Arbeit mit Tastatur-und Maus Eingaben bereit.

 Beispiele für die Eingabe-API <xref:System.Windows.Input.Keyboard> für die- <xref:System.Windows.Input.Keyboard.Modifiers%2A> Klasse sind die-Eigenschaft <xref:System.Windows.Input.ModifierKeys> , die den derzeit gedrückten zurückgibt, und die <xref:System.Windows.Input.Keyboard.IsKeyDown%2A> -Methode, die bestimmt, ob eine angegebene Taste gedrückt wird.

 Im folgenden Beispiel wird die <xref:System.Windows.Input.Keyboard.GetKeyStates%2A> -Methode verwendet, um <xref:System.Windows.Input.Key> zu bestimmen, ob sich ein im Zustand "herunter" befindet.

 [!code-csharp[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyArgsSnippetSample/CSharp/Window1.xaml.cs#keyeventargskeyboardgetkeystates)]
 [!code-vb[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyArgsSnippetSample/visualbasic/window1.xaml.vb#keyeventargskeyboardgetkeystates)]

 Beispiele für die Eingabe-API <xref:System.Windows.Input.Mouse> der- <xref:System.Windows.Input.Mouse.MiddleButton%2A>Klasse sind, die den Zustand der mittleren Maustaste erhält, und <xref:System.Windows.Input.Mouse.DirectlyOver%2A>, der das Element abruft, über dem sich der Mauszeiger befindet.

 Im folgenden Beispiel wird bestimmt, <xref:System.Windows.Input.Mouse.LeftButton%2A> ob sich die auf der Maus <xref:System.Windows.Input.MouseButtonState.Pressed> im-Zustand befindet.

 [!code-csharp[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](~/samples/snippets/csharp/VS_Snippets_Wpf/MouseRelatedSnippets/CSharp/Window1.xaml.cs#mouserelatedsnippetsgetleftbuttonmouse)]
 [!code-vb[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MouseRelatedSnippets/visualbasic/window1.xaml.vb#mouserelatedsnippetsgetleftbuttonmouse)]

 Die <xref:System.Windows.Input.Mouse> Klassen <xref:System.Windows.Input.Keyboard> und werden in dieser Übersicht ausführlicher behandelt.

### <a name="stylus-input"></a>Stifteingabe
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verfügt über integrierte Unterstützung <xref:System.Windows.Input.Stylus>für.  Der <xref:System.Windows.Input.Stylus> ist eine Stift Eingabe, die von der [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)]beliebt gemacht wird.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Anwendungen können den Tablettstift mithilfe der Maus-API als Maus behandeln, aber [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auch eine Stift-Geräte Abstraktion, die ein Modell ähnlich der Tastatur und der Maus verwendet.  Alle tablettstiftbezogenen APIs enthalten das Wort "Tablettstift".

 Da der Stift als Maus fungieren kann, können Anwendungen, die nur die Mauseingabe unterstützen, noch immer ein gewisses Maß an automatischer Unterstützung für den Stift erhalten. Wenn der Stift auf diese Weise verwendet wird, bekommt die Anwendung die Gelegenheit, das entsprechende Stiftereignis zu behandeln und behandelt dann das entsprechende Mausereignis. Darüber hinaus sind Dienste auf höherer Ebene (z.B. Freihandeingabe) noch immer über die Stift-Geräteabstraktion verfügbar.  Weitere Informationen zur Freihandeingabe finden Sie unter [Erste Schritte mit Freihandeingaben](getting-started-with-ink.md).

<a name="event_routing"></a>
## <a name="event-routing"></a>Ereignisrouting
 Eine <xref:System.Windows.FrameworkElement> kann andere Elemente als untergeordnete Elemente in Ihrem Inhalts Modell enthalten, die eine Struktur von Elementen bilden.  Durch die Übergabe von Ereignissen kann das übergeordnete Element in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in der Eingabe teilnehmen, die an dessen untergeordnetes Element oder andere indirekt untergeordnete Elemente weitergeleitet wird. Dies ist besonders nützlich, um Steuerelemente aus kleineren Steuerelementen zu erstellen. Dieser Prozess wird als „Zusammensetzung von Steuerelementen“ oder „Zusammensetzen“ bezeichnet. Weitere Informationen über Elementstrukturen und wie sich Elementstrukturen auf Ereignisrouten beziehen, finden Sie unter [Strukturen in WPF](trees-in-wpf.md).

 Das Ereignisrouting ist der Prozess, in dem Ereignisse an mehrere Elemente weitergeleitet werden, sodass ein bestimmtes Objekt oder Element entlang der Route einem Ereignis eine signifikante Antwort (durch Behandlung) anbieten kann, die sonst von einem anderen Element hätte stammen können.  Routingereignisse verwenden einen von drei Routingmechanismen: direkt, Bubbling und Tunneln.  Beim direkten Routing ist das Quellelement das einzige benachrichtigte Element, und das Ereignis wird nicht an andere Elemente weitergeleitet. Das direkte Routing Ereignis bietet jedoch noch einige zusätzliche Funktionen, die nur für Routing Ereignisse und nicht für CLR-Standard Ereignisse vorhanden sind. Bubbling arbeitet sich in der Elementstruktur nach oben, indem zuerst das Element benachrichtigt wird, von dem das Ereignis stammt, und anschließend das übergeordnete Element usw.  Tunneling beginnt am Stamm der Elementstruktur, arbeitet sich nach unten und endet mit dem ursprünglichen Quellelement.  Weitere Informationen zu Routingereignissen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabeereignisse treten generell in Paaren auf, die aus einem Tunneling-Ereignis und einem Bubbling-Ereignis bestehen.  Tunneling-Ereignisse unterscheiden sich von Bubbling-Ereignissen im Präfix „Preview“.  Beispielsweise <xref:System.Windows.Input.Mouse.MouseMove> ist die tunnelingversion eines Maus Verschiebungs Ereignisses und die bubblingerversion dieses Ereignisses. <xref:System.Windows.Input.Mouse.PreviewMouseMove> Diese Ereignispaarung ist eine Konvention, die auf der Elementebene implementiert ist, und keine inhärente Funktion des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignissystems, Weitere Informationen finden Sie im Abschnitt „Eingabeereignisse in WPF“ in [Übersicht über Routingereignisse](routed-events-overview.md).

<a name="handling_input_events"></a>
## <a name="handling-input-events"></a>Behandeln von Eingabeereignissen
 Um Eingaben für ein Element zu erhalten, muss ein Ereignishandler mit diesem speziellen Ereignis verknüpft sein.  In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist dies einfach: Sie verweisen auf den Namen des Ereignisses als ein Attribut des Elements, das für dieses Ereignis überwacht.  Legen Sie anschließend den Wert des Attributs auf den Namen des Ereignishandlers, den Sie basierend auf einen Delegaten definieren, fest.  Der Ereignishandler muss in Code wie geschrieben C# und in einer Code Behind-Datei enthalten sein.

 Tastaturereignisse treten auf, wenn das Betriebssystem Tastaturaktionen meldet, die auftreten, während sich der Tastaturfokus auf einem Element befindet. Maus- und Stiftereignisse lassen sich in zwei Kategorien unterteilen: Ereignisse, die Änderungen der Zeigerposition relativ zum Element melden sowie Ereignisse, die Änderungen im Status der Geräteschaltflächen melden.

### <a name="keyboard-input-event-example"></a>Beispiel eines Tastatureingabeereignisses
 Das folgende Beispiel überwacht das Drücken der Nach-Links-Taste.  Eine <xref:System.Windows.Controls.StackPanel> wird erstellt, die über <xref:System.Windows.Controls.Button>eine verfügt.  Ein Ereignishandler, der die nach-links-Taste gedrückt halten soll, <xref:System.Windows.Controls.Button> wird an die Instanz angefügt.

 Im ersten Abschnitt des Beispiels werden <xref:System.Windows.Controls.StackPanel> und der <xref:System.Windows.Controls.Button> erstellt, und <xref:System.Windows.UIElement.KeyDown>der-Ereignishandler wird an angefügt.

 [!code-xaml[InputOvw#Input_OvwKeyboardExampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwkeyboardexamplexaml)]

 [!code-csharp[InputOvw#Input_OvwKeyboardExampleUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexampleuicodebehind)]

 Der zweite Abschnitt ist in Code geschrieben und definiert den Ereignishandler.  Wenn die nach-links-Taste gedrückt wird <xref:System.Windows.Controls.Button> und der über den Tastaturfokus verfügt, <xref:System.Windows.Controls.Button> wird <xref:System.Windows.Controls.Control.Background%2A> der Handler ausgeführt, und die Farbe des wird geändert.  Wenn die Taste gedrückt wird, es sich aber nicht um die nach-links- <xref:System.Windows.Controls.Control.Background%2A> Taste handelt, <xref:System.Windows.Controls.Button> wird die Farbe der wieder in die Start Farbe geändert.

 [!code-csharp[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexamplehandlercodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexamplehandlercodebehind)]

### <a name="mouse-input-event-example"></a>Beispiel für Mauseingabeereignisse
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.Control.Background%2A> Farbe einer <xref:System.Windows.Controls.Button> geändert, wenn der Mauszeiger in den <xref:System.Windows.Controls.Button>eintritt.  Die <xref:System.Windows.Controls.Control.Background%2A> Farbe wird wieder hergestellt, wenn die Maus <xref:System.Windows.Controls.Button>die verlässt.

 Im ersten Abschnitt <xref:System.Windows.Controls.StackPanel> des Beispiels werden das-Steuerelement und das <xref:System.Windows.Controls.Button> -Steuerelement erstellt und die Ereignis <xref:System.Windows.UIElement.MouseEnter> Handler <xref:System.Windows.UIElement.MouseLeave> für das- <xref:System.Windows.Controls.Button>Ereignis und das-Ereignis an den angefügt.

 [!code-xaml[InputOvw#Input_OvwMouseExampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwmouseexamplexaml)]

 [!code-csharp[InputOvw#Input_OvwMouseExampleUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwMouseExampleUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleuicodebehind)]

 Der zweite Abschnitt des Beispiels wird in Code geschrieben und definiert die Ereignishandler.  Wenn die Maus in den <xref:System.Windows.Controls.Button>eintritt, <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button> wird die Farbe von in <xref:System.Windows.Media.Brushes.SlateGray%2A>geändert.  Wenn die <xref:System.Windows.Controls.Button>Maus den verlässt, <xref:System.Windows.Controls.Button> wird <xref:System.Windows.Controls.Control.Background%2A> die Farbe von wieder in <xref:System.Windows.Media.Brushes.AliceBlue%2A>geändert.

 [!code-csharp[InputOvw#Input_OvwMouseExampleEneterHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleeneterhandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleEneterHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleeneterhandler)]

 [!code-csharp[InputOvw#Input_OvwMouseExampleLeaveHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleleavehandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleLeaveHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleleavehandler)]

<a name="text_input"></a>
## <a name="text-input"></a>Texteingabe
 Das <xref:System.Windows.ContentElement.TextInput> Ereignis ermöglicht es Ihnen, auf geräteunabhängige Weise auf Texteingaben zu lauschen. Die Tastatur dient primär der Texteingabe, jedoch können Sie auch durch die Sprache, handschriftlich oder mit anderen Eingabegeräten Texteingabe generieren.

 Für Tastatureingaben [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sendet zunächst die / entsprechenden <xref:System.Windows.ContentElement.KeyDown> <xref:System.Windows.ContentElement.KeyUp> Ereignisse. Wenn diese Ereignisse nicht behandelt werden und es sich bei dem Schlüssel um einen Text handelt (anstelle eines Steuer Elements, z. b. direktionale Pfeile oder Funktionstasten), wird ein <xref:System.Windows.ContentElement.TextInput> -Ereignis ausgelöst.  Zwischen <xref:System.Windows.ContentElement.KeyDown> dem-Ereignis/ und<xref:System.Windows.ContentElement.TextInput> dem-Ereignis besteht nicht immer eine einfache 1: Eins-Zuordnung, da mehrere Tastatureingaben ein einzelnes Zeichen von Texteingabe generieren können und einzelne Tastatureingaben mehrere Zeichen generieren können. <xref:System.Windows.ContentElement.KeyUp> Folgen.  Dies gilt insbesondere für Sprachen wie Chinesisch, Japanisch und Koreanisch, die Eingabemethoden-Editoren (Input Method Editors, IMEs) verwenden, um Tausende von möglichen Zeichen in den entsprechenden Alphabets zu generieren.

 Wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein <xref:System.Windows.ContentElement.KeyUp> <xref:System.Windows.Input.KeyEventArgs.Key%2A> <xref:System.Windows.ContentElement.TextInput> -Ereignis sendet, wird auf<xref:System.Windows.Input.Key.System?displayProperty=nameWithType> festgelegt, wenn die Tastatureingaben Teil eines-Ereignisses werden könnten (Wenn z. b. ALT + S gedrückt wird). / <xref:System.Windows.ContentElement.KeyDown> Dies ermöglicht es dem Code <xref:System.Windows.ContentElement.KeyDown> in einem <xref:System.Windows.Input.Key.System?displayProperty=nameWithType> -Ereignishandler, die Verarbeitung des- <xref:System.Windows.ContentElement.TextInput> Handlers des nachfolgend ausgelössten Ereignisses zu überprüfen und, wenn er gefunden wird. In diesen Fällen können die verschiedenen Eigenschaften des <xref:System.Windows.Input.TextCompositionEventArgs> Arguments verwendet werden, um die ursprünglichen Tastatureingaben zu bestimmen. Ebenso gilt, wenn [!INCLUDE[TLA2#tla_ime](../../../../includes/tla2sharptla-ime-md.md)] eine aktiv ist <xref:System.Windows.Input.Key> , den Wert <xref:System.Windows.Input.Key.ImeProcessed?displayProperty=nameWithType>hat und <xref:System.Windows.Input.KeyEventArgs.ImeProcessedKey%2A> den ursprünglichen Tastatur Strich oder Tastatureingaben übergibt.

 Im folgenden Beispiel wird ein Handler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis und ein-Handler <xref:System.Windows.UIElement.KeyDown> für das-Ereignis definiert.

 Das erste Segment des Codes oder Markups erstellt die Benutzeroberfläche.

 [!code-xaml[InputOvw#Input_OvwTextInputXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwtextinputxaml)]

 [!code-csharp[InputOvw#Input_OvwTextInputUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputuicodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputuicodebehind)]

 Das zweite Segment des Codes enthält die Ereignishandler.

 [!code-csharp[InputOvw#Input_OvwTextInputHandlersCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputhandlerscodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputHandlersCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputhandlerscodebehind)]

 Da Eingabeereignisse die Ereignis Route aufblasen, <xref:System.Windows.Controls.StackPanel> empfängt die Eingabe unabhängig davon, welches Element den Tastaturfokus besitzt. Das <xref:System.Windows.Controls.TextBox> -Steuerelement wird zuerst benachrichtigt `OnTextInputKeyDown` , und der-Handler <xref:System.Windows.Controls.TextBox> wird nur aufgerufen, wenn der die Eingabe nicht behandelt hat. Wenn das <xref:System.Windows.UIElement.PreviewKeyDown> Ereignis anstelle <xref:System.Windows.UIElement.KeyDown> des-Ereignisses verwendet wird, wird `OnTextInputKeyDown` der Handler zuerst aufgerufen.

 In diesem Beispiel wird die Behandlungslogik zweimal geschrieben: einmal für STRG+O und nochmal für das Click-Ereignis der Schaltfläche. Anstatt die Eingabeereignisse direkt zu behandeln, können Sie dies mithilfe von Befehlen vereinfachen.  Befehle werden in dieser Übersicht unter [Befehlsübersicht](commanding-overview.md) erläutert.

<a name="touch_and_manipulation"></a>
## <a name="touch-and-manipulation"></a>Fingereingabe (Touch) und-Bearbeitung
 Neue Hardware und API im Windows 7-Betriebssystem bieten Anwendungen die Möglichkeit, Eingabe von mehreren Berührungen gleichzeitig zu erhalten. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht Anwendungen, Fingereingabe zu erkennen und ähnlich wie auf andere Eingabe zu reagieren, z.B. von einer Maus oder einer Tastatur, durch Auslösen von Ereignissen, wenn eine Fingereingabe erfolgt.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] macht zwei Typen von Ereignissen verfügbar, wenn eine Fingereingabe erfolgt: Berührungsereignisse und Bearbeitungsereignisse. Berührungsereignisse stellen Rohdaten zu jedem Finger auf einem Touchscreen und seiner Bewegung bereit. Bearbeitungsereignisse interpretieren die Eingabe als bestimmte Aktionen. Beide Typen von Ereignissen werden in diesem Abschnitt erläutert.

### <a name="prerequisites"></a>Vorraussetzungen
 Sie benötigen die folgenden Komponenten zur Entwicklung einer Anwendung, die auf Fingereingabe reagiert.

- Visual Studio 2010.

- Windows 7

- Ein Gerät, z.B. ein Touchscreen, das Windows Touch unterstützt

### <a name="terminology"></a>Terminologie
 Die folgenden Begriffe werden verwendet, wenn die Fingereingabe behandelt wird.

- **Touch (Fingereingabe)** ist ein Typ von Benutzereingabe, der von Windows 7 erkannt wird. In der Regel wird die Fingereingabe initiiert, indem ein berührungsempfindlicher Bildschirm mit Fingern berührt wird. Beachten Sie, dass Geräte wie Touchpads, die auf Laptops gang und gäbe sind, keine Fingereingabe unterstützen, wenn das Gerät lediglich die Position und die Bewegung des Fingers als Mauseingabe konvertiert.

- **Multitouch (Mehrfingereingabe)** ist Berührung, die gleichzeitig von mehreren Punkten erfolgt. Windows 7 und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützen die Mehrfingereingabe. Wann immer die Fingereingabe in der Dokumentation für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erläutert wird, gelten die Konzepte auch für die Mehrfingereingabe.

- Ein **Manipulation** tritt auf, wenn die Berührung als physische Aktion interpretiert wird, die auf ein Objekt angewendet wird. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] interpretieren Bearbeitungsereignisse die Eingabe als Übersetzungs-, Erweiterungs- und Drehungsmanipualtion.

- Ein `touch device` stellt ein Gerät dar, das Fingereingabe erzeugt, z.B. ein einzelner Finger auf einem Touchscreen.

### <a name="controls-that-respond-to-touch"></a>Steuerelemente, die auf Fingereingabe reagieren
 Die folgenden Steuerelemente können gescrollt werden, wenn Sie über Inhalt verfügen, der sich außerhalb der Ansicht befindet, indem Sie mit einem Finger über die Steuerelemente wischen.

- <xref:System.Windows.Controls.ComboBox>

- <xref:System.Windows.Controls.ContextMenu>

- <xref:System.Windows.Controls.DataGrid>

- <xref:System.Windows.Controls.ListBox>

- <xref:System.Windows.Controls.ListView>

- <xref:System.Windows.Controls.MenuItem>

- <xref:System.Windows.Controls.TextBox>

- <xref:System.Windows.Controls.ToolBar>

- <xref:System.Windows.Controls.TreeView>

 Definiert <xref:System.Windows.Controls.ScrollViewer> die<xref:System.Windows.Controls.ScrollViewer.PanningMode%2A?displayProperty=nameWithType> angefügte-Eigenschaft, mit der Sie angeben können, ob die Berührungs schwenken horizontal, vertikal, beides oder keines von beiden aktiviert ist. Die <xref:System.Windows.Controls.ScrollViewer.PanningDeceleration%2A?displayProperty=nameWithType> -Eigenschaft gibt an, wie schnell der Bildlauf verlangsamt wird, wenn der Benutzer den Finger vom Touchscreen aufhebt. Die <xref:System.Windows.Controls.ScrollViewer.PanningRatio%2A?displayProperty=nameWithType> angefügte-Eigenschaft gibt das Verhältnis des scrolloffsets zum Übersetzen der Manipulations Abweichung an.

### <a name="touch-events"></a>Berührungsereignisse
 Die Basisklassen <xref:System.Windows.UIElement> <xref:System.Windows.UIElement3D>,, und <xref:System.Windows.ContentElement>definieren Ereignisse, die Sie abonnieren können, damit Ihre Anwendung auf die Fingereingabe reagiert. Berührungsereignisse sind nützlich, wenn Ihre Anwendung Fingereingabe als etwas anderes als die Bearbeitung eines Objekts interpretiert. Beispielsweise würde eine Anwendung, mit der ein Benutzer mit einem oder mehreren Fingern zeichnen kann, Berührungsereignisse abonnieren.

 Alle drei Klassen definieren die folgenden Ereignisse, die sich ähnlich verhalten, unabhängig von der definierenden Klasse.

- <xref:System.Windows.UIElement.TouchDown>

- <xref:System.Windows.UIElement.TouchMove>

- <xref:System.Windows.UIElement.TouchUp>

- <xref:System.Windows.UIElement.TouchEnter>

- <xref:System.Windows.UIElement.TouchLeave>

- <xref:System.Windows.UIElement.PreviewTouchDown>

- <xref:System.Windows.UIElement.PreviewTouchMove>

- <xref:System.Windows.UIElement.PreviewTouchUp>

- <xref:System.Windows.UIElement.GotTouchCapture>

- <xref:System.Windows.UIElement.LostTouchCapture>

 Wie die Tastatur- und Maus-Ereignisse sind die Berührungsereignisse Routingereignisse. Die Ereignisse, die mit `Preview` beginnen, sind Tunneling-Ereignisse, und die Ereignisse, die mit `Touch` beginnen, sind Bubbling-Ereignisse. Weitere Informationen zu Routingereignissen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md). Wenn Sie diese Ereignisse behandeln, können Sie die Position der Eingabe relativ zu einem beliebigen Element abrufen, indem Sie die- <xref:System.Windows.Input.TouchEventArgs.GetTouchPoint%2A> Methode <xref:System.Windows.Input.TouchEventArgs.GetIntermediateTouchPoints%2A> oder die-Methode aufrufen.

 Um die Interaktion zwischen Berührungsereignissen zu verstehen, denken Sie an das Szenario, bei dem ein Benutzer einen Finger auf ein Element legt, den Finger im Element bewegt und anschließend den Finger vom Element wegnimmt. Die folgende Abbildung zeigt die Ausführung der Bubbling-Ereignisse (die Tunneling-Ereignisse werden der Einfachheit halber ausgelassen).

 ![Die Sequenz von Berührungs Ereignissen.](./media/ndp-touchevents.png "NDP_TouchEvents") Berührungs Ereignisse

 Die folgende Liste beschreibt die Abfolge der Ereignisse in der vorherigen Abbildung.

1. Das <xref:System.Windows.UIElement.TouchEnter> Ereignis tritt einmal auf, wenn der Benutzer einen Finger auf das Element legt.

2. Das <xref:System.Windows.UIElement.TouchDown> Ereignis tritt einmal auf.

3. Das <xref:System.Windows.UIElement.TouchMove> Ereignis tritt mehrmals auf, wenn der Benutzer den Finger im Element bewegt.

4. Das <xref:System.Windows.UIElement.TouchUp> Ereignis tritt einmal auf, wenn der Benutzer den Finger vom Element aufhebt.

5. Das <xref:System.Windows.UIElement.TouchLeave> Ereignis tritt einmal auf.

 Wenn mehr als zwei Finger verwendet werden, treten die Ereignisse für jeden Finger auf.

### <a name="manipulation-events"></a>Bearbeitungsereignisse
 In Fällen, in denen eine Anwendung einem Benutzer das Bearbeiten eines Objekts ermöglicht <xref:System.Windows.UIElement> , definiert die Klasse Bearbeitungs Ereignisse. Im Gegensatz zu den Berührungsereignissen, die einfach die Position der Berührung melden, melden die Bearbeitungsereignisse, wie die Eingabe interpretiert werden kann. Es gibt drei Arten von Manipulationen, Übersetzung, Erweiterung und Drehung. Die folgende Liste beschreibt, wie die drei Typen von Manipulationen aufgerufen werden.

- Legen Sie einen Finger auf ein Objekt, und verschieben Sie den Finger über den Touchscreen, um eine Übersetzungsmanipulation aufzurufen. Dadurch wird in der Regel das Objekt verschoben.

- Legen Sie zwei Finger auf ein Objekt, und bewegen Sie die Finger näher zusammen oder weiter auseinander, um eine Erweiterungsmanipulation aufzurufen. Dadurch wird in der Regel die Größe des Objekts geändert.

- Legen Sie zwei Finger auf ein Objekt, und drehen Sie einen Finger um den jeweils anderen um eine Drehungsmanipulation aufzurufen. Dadurch wird in der Regel das Objekt gedreht.

 Es kann mehr als eine Manipulation gleichzeitig geschehen.

 Wenn Sie Objekte dazu bringen, auf Manipulationen anzusprechen, können Sie erreichen, dass das Objekt verzögert wird. Dadurch kann Ihr Objekt die physische Welt simulieren. Wenn Sie z.B. ein Buch über einen Tisch schieben, dann bewegt sich das Buch nach dem Loslassen weiter voran, wenn Sie nur kräftig genug anschieben. Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie dieses Verhalten übernehmen, indem Sie Bearbeitungsereignisse auslösen,nachdem der Benutzer das Objekt losgelassen hat.

 Weitere Informationen zum Erstellen einer Anwendung, die dem Benutzer das Verschieben, Ändern der Größe und das Drehen eines Objekts ermöglicht, finden [Sie unter Exemplarische Vorgehensweise: Erstellen Ihrer ersten Touchscreen-](walkthrough-creating-your-first-touch-application.md)Anwendung.

 <xref:System.Windows.UIElement> Definiert die folgenden Bearbeitungs Ereignisse.

- <xref:System.Windows.UIElement.ManipulationStarting>

- <xref:System.Windows.UIElement.ManipulationStarted>

- <xref:System.Windows.UIElement.ManipulationDelta>

- <xref:System.Windows.UIElement.ManipulationInertiaStarting>

- <xref:System.Windows.UIElement.ManipulationCompleted>

- <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>

 Standardmäßig empfängt eine <xref:System.Windows.UIElement> diese Manipulations Ereignisse nicht. Legen Sie <xref:System.Windows.UIElement> <xref:System.Windows.UIElement.IsManipulationEnabled%2A?displayProperty=nameWithType>auffest , um Bearbeitungs Ereignisse für eine zu empfangen. `true`

#### <a name="the-execution-path-of-manipulation-events"></a>Der Ausführungspfad von Bearbeitungsereignissen
 Denken Sie an ein Szenario, in dem ein Benutzer ein Objekt „wirft“. Der Benutzer legt einen Finger auf das Objekt, bewegt den Finger etwas über den Touchscreen und hebt dann in der Bewegung den Finger. Dadurch bewegt sich das Objekt unter dem Finger des Benutzers und bewegt sich dann noch weiter, wenn der Benutzer den Finger hebt.

 Die folgende Abbildung zeigt den Ausführungspfad von Bearbeitungsereignissen und wichtige Informationen zu jedem Ereignis.

 ![Die Sequenz der Bearbeitungs Ereignisse.](./media/ndp-manipulationevents.png "NDP_ManipulationEvents") Manipulations Ereignisse

 Die folgende Liste beschreibt die Abfolge der Ereignisse in der vorherigen Abbildung.

1. Das <xref:System.Windows.UIElement.ManipulationStarting> Ereignis tritt auf, wenn der Benutzer einen Finger auf das Objekt legt. Unter anderem ermöglicht dieses Ereignis das Festlegen der <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> -Eigenschaft. In den nachfolgenden Ereignissen ist die Position der Bearbeitung relativ zum <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>. In anderen Ereignissen als <xref:System.Windows.UIElement.ManipulationStarting>ist diese Eigenschaft schreibgeschützt, sodass das <xref:System.Windows.UIElement.ManipulationStarting> Ereignis das einzige Mal ist, dass Sie diese Eigenschaft festlegen können.

2. Das <xref:System.Windows.UIElement.ManipulationStarted> Ereignis tritt als nächstes auf. Dieses Ereignis meldet den Ursprung der Manipulation.

3. Das <xref:System.Windows.UIElement.ManipulationDelta> Ereignis tritt mehrmals auf, wenn die Finger des Benutzers auf einem Touchscreen bewegt werden. Die <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> -Eigenschaft <xref:System.Windows.Input.ManipulationDeltaEventArgs> der-Klasse meldet, ob die Manipulation als Bewegung, Erweiterung oder Übersetzung interpretiert wird. Hier können Sie die meisten Bearbeitungen an einem Objekt durchführen.

4. Das <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis tritt auf, wenn die Finger des Benutzers den Kontakt mit dem Objekt verlieren. Mit diesem Ereignis können Sie die Verlangsamung der Bearbeitungen während der Verzögerung angeben. So kann Ihr Objekt unterschiedliche physikalische Bereiche oder Attribute Ihrer Wahl emulieren. Nehmen wir beispielsweise an, Ihre Anwendung enthält zwei Objekte, die Elemente in der realen Welt darstellen, und eines massiger als das andere ist. Sie können veranlassen, dass das massige Objekt schneller verlangsamt wird als das leichtere Objekt

5. Das <xref:System.Windows.UIElement.ManipulationDelta> Ereignis tritt mehrmals auf, wenn Trägheit auftritt. Beachten Sie, dass dieses Ereignis auftritt, wenn der Benutzer seine Finger über den Touchscreen bewegt, und wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Verzögerung simuliert. Anders ausgedrückt, <xref:System.Windows.UIElement.ManipulationDelta> tritt vor und nach dem <xref:System.Windows.UIElement.ManipulationInertiaStarting> -Ereignis auf. Die <xref:System.Windows.Input.ManipulationDeltaEventArgs.IsInertial%2A?displayProperty=nameWithType> -Eigenschaft meldet, <xref:System.Windows.UIElement.ManipulationDelta> ob das Ereignis während der Trägheit auftritt, sodass Sie diese Eigenschaft überprüfen und abhängig von ihrem Wert verschiedene Aktionen ausführen können.

6. Das <xref:System.Windows.UIElement.ManipulationCompleted> Ereignis tritt auf, wenn die Manipulation und Trägheit beendet werden. Das heißt, nachdem alle <xref:System.Windows.UIElement.ManipulationDelta> Ereignisse aufgetreten sind, tritt das <xref:System.Windows.UIElement.ManipulationCompleted> -Ereignis auf, um zu signalisieren, dass die Bearbeitung vollständig ist.

 Der <xref:System.Windows.UIElement> definiert auch das <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Ereignis. Dieses Ereignis tritt <xref:System.Windows.UIElement.ManipulationDelta> auf, <xref:System.Windows.Input.ManipulationDeltaEventArgs.ReportBoundaryFeedback%2A> wenn die-Methode im-Ereignis aufgerufen wird. Das <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> -Ereignis ermöglicht Anwendungen oder Komponenten das Bereitstellen von visuellem Feedback, wenn ein Objekt auf eine Grenze trifft. Die <xref:System.Windows.Window> -Klasse verarbeitet z. b <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> . das-Ereignis, um zu bewirken, dass das Fenster beim Auftreten seines Edge leicht verschoben wird.

 Sie können die Bearbeitung abbrechen, indem Sie <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> die-Methode für die Ereignis Argumente in einem beliebigen <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Manipulations Ereignis außer Ereignis aufrufen. Wenn Sie aufzurufen <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A>, werden die Manipulations Ereignisse nicht mehr ausgelöst, und es treten Mausereignisse für die Fingereingabe auf. Die folgende Tabelle beschreibt die Beziehung zwischen dem Zeitpunkt, an dem die Bearbeitung abgebrochen wird, und den Mausereignissen, die auftreten.

|Das Ereignis zum Abbruch, das aufgerufen wird|Die Mausereignisse, die für die Eingabe auftreten, die bereits aufgetreten sind|
|----------------------------------------|-----------------------------------------------------------------|
|<xref:System.Windows.UIElement.ManipulationStarting> und <xref:System.Windows.UIElement.ManipulationStarted>|Ereignisse mit gedrückter Maustaste|
|<xref:System.Windows.UIElement.ManipulationDelta>|Ereignisse mit gedrückter Maustaste und beim Verschieben der Maus|
|<xref:System.Windows.UIElement.ManipulationInertiaStarting> und <xref:System.Windows.UIElement.ManipulationCompleted>|Ereignisse mit gedrückter Maustaste, beim Verschieben der Maus und beim Loslassen der Maustaste|

 Beachten Sie, dass die <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> -Methode zurückgibt, wenn Sie bei einer Trägheit `false` -Bearbeitung den Wert zurückgeben und die Eingabe keine Mausereignisse aufruft.

### <a name="the-relationship-between-touch-and-manipulation-events"></a>Die Beziehung zwischen Berührungs- und Bearbeitungsereignissen
 Ein <xref:System.Windows.UIElement> kann immer Berührungs Ereignisse empfangen. Wenn die <xref:System.Windows.UIElement.IsManipulationEnabled%2A> -Eigenschaft auf `true`festgelegt ist <xref:System.Windows.UIElement> , kann ein sowohl Berührungs-als auch Bearbeitungs Ereignisse empfangen.  Wenn das <xref:System.Windows.UIElement.TouchDown> -Ereignis nicht behandelt wird (d. h <xref:System.Windows.RoutedEventArgs.Handled%2A> . die `false`-Eigenschaft ist), erfasst die Bearbeitungs Logik die Fingereingabe für das-Element und generiert die Manipulations Ereignisse. Wenn die <xref:System.Windows.RoutedEventArgs.Handled%2A> -Eigenschaft im <xref:System.Windows.UIElement.TouchDown> - `true` Ereignis auf festgelegt wird, generiert die Bearbeitungs Logik keine Bearbeitungs Ereignisse. Die folgende Abbildung zeigt die Beziehung zwischen Berührungs- und Bearbeitungsereignissen.

 ![Beziehung zwischen Berührungs-und Bearbeitungs Ereignissen](./media/ndp-touchmanipulateevents.png "NDP_TouchManipulateEvents") Berührungs-und Bearbeitungs Ereignisse

 Die folgende Liste beschreibt die Beziehung zwischen Berührungs- und Bearbeitungsereignissen, die in der folgenden Abbildung dargestellt ist.

- Wenn das erste Fingerabdruck-Gerät <xref:System.Windows.UIElement.TouchDown> ein-Ereignis <xref:System.Windows.UIElement>auf einem generiert, ruft <xref:System.Windows.UIElement.CaptureTouch%2A> die Bearbeitungs Logik die-Methode <xref:System.Windows.UIElement.GotTouchCapture> auf, die das-Ereignis generiert.

- Wenn das <xref:System.Windows.UIElement.GotTouchCapture> auftritt, <xref:System.Windows.Input.Manipulation.AddManipulator%2A?displayProperty=nameWithType> Ruft die Bearbeitungs Logik die-Methode auf, die <xref:System.Windows.UIElement.ManipulationStarting> das-Ereignis generiert.

- Wenn die <xref:System.Windows.UIElement.TouchMove> Ereignisse auftreten, generiert die Bearbeitungs Logik die <xref:System.Windows.UIElement.ManipulationDelta> Ereignisse, die vor dem <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis auftreten.

- Wenn das letzte Fingerabdruck-Gerät des-Elements <xref:System.Windows.UIElement.TouchUp> das-Ereignis auslöst, generiert die <xref:System.Windows.UIElement.ManipulationInertiaStarting> Bearbeitungs Logik das-Ereignis.

<a name="focus"></a>
## <a name="focus"></a>Fokus
 Es gibt zwei Hauptkonzepte, die den Fokus in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] betreffen: Tastaturfokus und logischer Fokus.

### <a name="keyboard-focus"></a>Tastaturfokus
 Der Tastaturfokus bezieht sich auf das Element, das Tastatureingaben empfängt.  Es kann nur ein Element auf dem gesamten Desktop geben, das über den Tastaturfokus verfügt.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wirddasElement,`true`das über den Tastaturfokus verfügt, auf festgelegt.<xref:System.Windows.IInputElement.IsKeyboardFocused%2A>  Die statische <xref:System.Windows.Input.Keyboard> - <xref:System.Windows.Input.Keyboard.FocusedElement%2A> Methode gibt das Element zurück, das derzeit über den Tastaturfokus verfügt.

 Der Tastaturfokus kann durch die Tab-Taste für ein Element oder durch Klicken auf die Maus auf bestimmte Elemente (z <xref:System.Windows.Controls.TextBox>. b.) abgerufen werden.  Der Tastaturfokus kann auch Programm gesteuert mithilfe der <xref:System.Windows.Input.Keyboard.Focus%2A> -Methode für die <xref:System.Windows.Input.Keyboard> -Klasse abgerufen werden.  <xref:System.Windows.Input.Keyboard.Focus%2A>versucht, dem angegebenen Element Tastaturfokus zu übergeben.  Das von <xref:System.Windows.Input.Keyboard.Focus%2A> zurückgegebene Element ist das Element, das derzeit über den Tastaturfokus verfügt.

 Damit ein Element den Tastaturfokus erhält, müssen die <xref:System.Windows.UIElement.Focusable%2A> -Eigenschaft und <xref:System.Windows.UIElement.IsVisible%2A> die-Eigenschaften auf **true**festgelegt werden.  Einige Klassen, wie z <xref:System.Windows.Controls.Panel>. b <xref:System.Windows.UIElement.Focusable%2A> ., `false` haben standardmäßig auf festgelegt. Daher müssen Sie diese Eigenschaft möglich `true` erweise auf festlegen, wenn dieses Element den Fokus erhalten soll.

 Im folgenden Beispiel wird <xref:System.Windows.Input.Keyboard.Focus%2A> verwendet, um den Tastaturfokus <xref:System.Windows.Controls.Button>auf einen festzulegen.  Die empfohlene Stelle zum Festlegen des ersten Fokus in einer Anwendung ist der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.

 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]

 Weitere Informationen über den Tastaturfokus finden Sie unter [Fokus – Übersicht](focus-overview.md).

### <a name="logical-focus"></a>Logischer Fokus
 Der logische Fokus bezieht sich <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> auf den in einem Fokusbereich.  Es können mehrere Elemente vorhanden sein, die über logischen Fokus in einer Anwendung verfügen, jedoch kann es nur ein Element geben, das den logischen Fokus in einem bestimmten Fokusbereich besitzt.

 Ein Fokusbereich ist ein Containerelement, das den <xref:System.Windows.Input.FocusManager.FocusedElement%2A> innerhalb seines Bereichs verfolgt.  Wenn der Fokus einen Fokusbereich verlässt, wird das Element den Tastaturfokus verlieren, jedoch behält es den logischen Fokus.  Wenn der Fokus zum Fokusbereich zurückkehrt, wird das Fokuselement Tastaturfokus erhalten.  Somit kann der Tastaturfokus zwischen mehreren Fokusbereichen geändert werden, aber es wird sichergestellt, dass das Fokuselement im Fokusbereich das Element bleibt, das über den Fokus verfügt, wenn dieser zurückgegeben wird.

 Ein Element kann in einen Fokusbereich in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] umgewandelt werden, indem die <xref:System.Windows.Input.FocusManager> angefügte-Eigenschaft <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> auf `true`festgelegt wird, oder im Code durch Festlegen der <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> angefügten-Eigenschaft mithilfe der-Methode.

 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.StackPanel> durch Festlegen der <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> angefügten-Eigenschaft in einen Fokusbereich umgewandelt.

 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]

 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]

 Klassen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bei denen es sich standardmäßig um Schwerpunkt <xref:System.Windows.Controls.Menu>Bereiche handelt, <xref:System.Windows.Controls.ContextMenu>sind <xref:System.Windows.Window>,, <xref:System.Windows.Controls.ToolBar>und.

 Ein Element, das über den Tastaturfokus verfügt, weist auch den logischen Fokus auf den Fokusbereich auf, zu dem er gehört. Daher wird beim Festlegen des Fokus auf ein Element <xref:System.Windows.Input.Keyboard.Focus%2A> , das die <xref:System.Windows.Input.Keyboard> -Methode für die Klasse oder die Basiselement Klassen verwendet, versucht, dem Element Tastaturfokus und logischen Fokus zu übergeben.

 Verwenden <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>Sie, um das fokussierte Element in einem Fokusbereich zu ermitteln. Verwenden <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>Sie, um das fokussierte Element für einen Fokusbereich zu ändern.

 Weitere Informationen über den logischen Fokus finden Sie unter [Fokus – Übersicht](focus-overview.md).

<a name="mouse_position"></a>
## <a name="mouse-position"></a>Mausposition
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eingabe-API bietet hilfreiche Informationen in Bezug auf Koordinaten Bereiche.  Zum Beispiel ist die Koordinate `(0,0)` die Koordinate oben links, aber von welchem Element in der Struktur? Das Element, das das Eingabeziel ist? Das Element, an das Sie Ihren Ereignishandler angefügt haben? Oder doch etwas anderes? Um Verwirrung zu vermeiden, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erfordert die Eingabe-API, dass Sie den Verweis Rahmen angeben, wenn Sie mit Koordinaten arbeiten, die mit der Maus abgerufen wurden. Die <xref:System.Windows.Input.Mouse.GetPosition%2A> -Methode gibt die Koordinate des Mauszeigers relativ zum angegebenen Element zurück.

<a name="mouse_capture"></a>
## <a name="mouse-capture"></a>Mausaufzeichnung
 Insbesondere Mausgeräte verfügen über modale Eigenschaften, die als Mausaufzeichnung bekannt sind. Die Mausaufzeichnung wird verwendet, um einen vorübergehenden Eingabestatus beizubehalten, wenn ein Drag & Drop-Vorgang gestartet wird, damit andere Vorgänge, einschließlich die nominale Position auf dem Bildschirm, nicht unbedingt auftreten. Während des Ziehens kann der Benutzer nicht klicken, ohne dass der Drag & Drop-Vorgang abgebrochen wird. Darum sind die meisten Mouseover-Cues nicht geeignet, während die Mausaufzeichnung durch die Drag-Quelle gehalten wird. Das Eingabe System macht APIs verfügbar, mit denen der Status der Maus Aufzeichnung bestimmt werden kann, sowie APIs, mit denen die Maus Aufzeichnung an ein bestimmtes Element erzwungen oder der Zustand der Maus Aufzeichnung gelöscht werden kann. Weitere Informationen zu Drag & Drop-Vorgängen finden Sie unter [Übersicht über Drag & Drop](drag-and-drop-overview.md).

<a name="commands"></a>
## <a name="commands"></a>Befehle
 Befehle ermöglichen die Eingabebehandlung auf einer eher semantischeren Ebene als die Geräteeingabe.  Befehle sind einfache Direktive, wie etwa `Cut`, `Copy`, `Paste` oder `Open`.  Befehle sind nützlich für die Zentralisierung der Befehlslogik.  Auf denselben Befehl kann von einem <xref:System.Windows.Controls.Menu>, auf einem <xref:System.Windows.Controls.ToolBar>oder über eine Tastenkombination zugegriffen werden. Befehle stellen außerdem einen Mechanismus zum Deaktivieren von Steuerelementen bereit, wenn der Befehl nicht verfügbar ist.

 <xref:System.Windows.Input.RoutedCommand>ist die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Implementierung von <xref:System.Windows.Input.ICommand>.  Wenn eine <xref:System.Windows.Input.RoutedCommand> ausgeführt wird, werden <xref:System.Windows.Input.CommandManager.PreviewExecuted> ein- <xref:System.Windows.Input.CommandManager.Executed> Ereignis und ein-Ereignis für das Befehls Ziel ausgelöst, das den Tunnel und die-Elementstruktur durchläuft, wie andere Eingaben.  Wenn ein Befehlsziel nicht festgelegt ist, wird das Element mit dem Tastaturfokus das Befehlsziel sein.  Die Logik, die den Befehl ausführt, wird an <xref:System.Windows.Input.CommandBinding>einen angefügt.  Wenn ein <xref:System.Windows.Input.CommandBinding> <xref:System.Windows.Input.ExecutedRoutedEventHandler> Ereignis einen für diesen bestimmten Befehl erreicht, wird der auf <xref:System.Windows.Input.CommandBinding> dem aufgerufen. <xref:System.Windows.Input.CommandManager.Executed>  Dieser Handler führt die Aktion des Befehls aus.

 Weitere Informationen über Befehle finden Sie unter [Befehlsübersicht](commanding-overview.md).

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt eine Bibliothek allgemeiner Befehle bereit, die aus <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>und <xref:System.Windows.Documents.EditingCommands>besteht, oder Sie können eigene Befehle definieren.

 Im folgenden Beispiel wird <xref:System.Windows.Controls.MenuItem> gezeigt, wie ein eingerichtet wird, sodass beim Klicken auf den- <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl im aufgerufen <xref:System.Windows.Controls.TextBox>wird, vorausgesetzt, <xref:System.Windows.Controls.TextBox> dass über den Tastaturfokus verfügt.

 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]

 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]

 Weitere Informationen über Befehle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Befehlsübersicht](commanding-overview.md).

<a name="the_input_system_and_base_elements"></a>
## <a name="the-input-system-and-base-elements"></a>Das Eingabesystem und die Basiselemente
 Eingabeereignisse, wie z. b. die angefügten <xref:System.Windows.Input.Keyboard>Ereignisse, <xref:System.Windows.Input.Stylus> die durch die <xref:System.Windows.Input.Mouse>Klassen, und definiert werden, werden vom Eingabe System ausgelöst und in eine bestimmte Position im Objektmodell eingefügt, basierend auf dem Treffer Test der visuellen Struktur zur Laufzeit.

 Jedes Ereignis, das <xref:System.Windows.Input.Mouse>, und <xref:System.Windows.Input.Keyboard> <xref:System.Windows.Input.Stylus> als angefügtes Ereignis definiert, wird auch von den Basiselement Klassen <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> als neues Routing Ereignis erneut verfügbar gemacht. Die Basiselement-Routingereignisse werden von Klassen generiert, die das ursprüngliche angefügte Ereignis behandeln und die Ereignisdaten wiederverwenden.

 Wenn das Eingabeereignis einem bestimmten Quellelement durch seine Implementierung des Eingabeereignisses des Basiselements zugeordnet wird, kann es durch den Rest einer Ereignisroute weitergeleitet werden, die auf einer Kombination von logischen und visuellen Strukturobjekten basiert und vom Anwendungscode behandelt wird.  Im Allgemeinen ist es einfacher, diese gerätebezogenen Eingabeereignisse mithilfe der Routing Ereignisse für <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement>zu verarbeiten, da Sie eine intuitivere Ereignishandlersyntax sowohl [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in als auch in Code verwenden können. Sie könnten stattdessen das angefügte Ereignis behandeln, das den Prozess initiiert hat, jedoch würden Sie auf Probleme stoßen: das angefügte Ereignis kann möglicherweise durch die Behandlung der Basiselementklasse behandelt markiert werden, und Sie müssen Accessormethoden verwenden, anstatt die richtige Ereignissyntax, um Handler für angefügte Ereignisse anzufügen.

<a name="whats_next"></a>
## <a name="whats-next"></a>Weitere Informationen
 Sie kennen nun verschiedene Methoden, um Eingabe in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu behandeln.  Sie sollten auch ein tieferes Verständnis der verschiedenen Typen von Eingabeereignissen und Routingereignismechanismen haben, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] genutzt werden.

 Es gibt zusätzliche Ressourcen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Frameworkelemente und das Ereignisrouting detaillierter beschreiben. In den folgenden Übersichten finden Sie weitere Informationen: [Befehlsübersicht](commanding-overview.md), [Fokus – Übersicht](focus-overview.md), [Übersicht über Basiselemente](base-elements-overview.md), [Strukturen in WPF](trees-in-wpf.md) und [Übersicht über Routingereignisse](routed-events-overview.md).

## <a name="see-also"></a>Siehe auch

- [Fokus - Übersicht](focus-overview.md)
- [Befehlsübersicht](commanding-overview.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Übersicht über Basiselemente](base-elements-overview.md)
- [Eigenschaften](properties-wpf.md)
