---
title: Fokus - Übersicht
description: 'Erfahren Sie mehr über die beiden Hauptkonzepte in Windows Presentation Foundation, die sich auf den Fokus beziehen: Tastaturfokus und logischer Fokus.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: 71aeb577cccd2c3b16df1c5a3cb772dd1f5479e2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165101"
---
# <a name="focus-overview"></a>Fokus - Übersicht
In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es zwei Hauptkonzepte, die den Fokus betreffen: Tastaturfokus und logischer Fokus.  Tastaturfokus bezieht sich auf das Element, das Tastatureingaben empfängt, und der logische Fokus bezieht sich auf das Element in einem Fokusbereich, der Fokus besitzt.  Diese Konzepte werden in dieser Übersicht ausführlich erläutert.  Für das Erstellen von komplexen Anwendungen, die über mehrere Bereiche verfügen, in denen Fokus abgerufen werden kann, ist es wichtig den Unterschied der Konzepte zu verstehen.  
  
 Die wichtigsten Klassen, die an der Fokus Verwaltung beteiligt sind, sind die <xref:System.Windows.Input.Keyboard> -Klasse, die <xref:System.Windows.Input.FocusManager> -Klasse und die-Basiselement Klassen, z <xref:System.Windows.UIElement> . b <xref:System.Windows.ContentElement> . und.  Weitere Informationen zu den Basiselementen finden Sie unter [Übersicht über Basiselemente](base-elements-overview.md).  
  
 Die <xref:System.Windows.Input.Keyboard> Klasse befasst sich hauptsächlich mit dem Tastaturfokus <xref:System.Windows.Input.FocusManager> , und die ist in erster Linie mit dem logischen Fokus beschäftigt, aber dies ist kein absoluter Unterschied.  Ein Element, das über den Tastaturfokus verfügt, besitzt auch einen logischen Fokus, aber ein Element mit dem logischen Fokus muss nicht unbedingt über den Tastaturfokus verfügen.  Dies ist offensichtlich, wenn Sie die-Klasse verwenden, <xref:System.Windows.Input.Keyboard> um das Element mit dem Tastaturfokus festzulegen, damit auch der logische Fokus auf dem Element festgelegt wird.  

<a name="Keyboard_Focus"></a>
## <a name="keyboard-focus"></a>Tastaturfokus  
 Der Tastaturfokus bezieht sich auf das Element, das derzeit Tastatureingaben empfängt.  Es kann nur ein Element auf dem gesamten Desktop geben, das über den Tastaturfokus verfügt.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird das Element, das über den Tastaturfokus verfügt, <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> auf festgelegt `true` .  Die statische-Eigenschaft der- <xref:System.Windows.Input.Keyboard.FocusedElement%2A> <xref:System.Windows.Input.Keyboard> Klasse ruft das Element ab, das derzeit über den Tastaturfokus verfügt.  
  
 Damit ein Element den Tastaturfokus erhalten kann, müssen die <xref:System.Windows.UIElement.Focusable%2A> -Eigenschaft und die-Eigenschaft der <xref:System.Windows.UIElement.IsVisible%2A> Basiselemente auf festgelegt werden `true` .  Einige Klassen, z <xref:System.Windows.Controls.Panel> . b. die Basisklasse, haben <xref:System.Windows.UIElement.Focusable%2A> standardmäßig auf festgelegt `false` . Daher müssen Sie auf festlegen, <xref:System.Windows.UIElement.Focusable%2A> `true` Wenn ein solches Element den Tastaturfokus abrufen soll.  
  
 Tastaturfokus kann durch die Benutzerinteraktion mit [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] abgerufen werden, z.B. durch das Wechseln mit der Tabulatortaste zu einem Element oder durch Klicken mit der Maus auf bestimmte Elemente.  Der Tastaturfokus kann auch Programm gesteuert mithilfe der- <xref:System.Windows.Input.Keyboard.Focus%2A> Methode für die- <xref:System.Windows.Input.Keyboard> Klasse abgerufen werden.  Die- <xref:System.Windows.Input.Keyboard.Focus%2A> Methode versucht, dem angegebenen Element den Tastaturfokus zu übergeben.  Das zurückgegebene Element ist das Element mit Tastaturfokus, was möglicherweise ein anderes Element als angefordert sein kann, wenn das alte oder neue Fokusobjekt die Anforderung blockiert.  
  
 Im folgenden Beispiel wird die- <xref:System.Windows.Input.Keyboard.Focus%2A> Methode verwendet, um den Tastaturfokus auf einen festzulegen <xref:System.Windows.Controls.Button> .  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Die- <xref:System.Windows.UIElement.IsKeyboardFocused%2A> Eigenschaft in den Basiselement Klassen Ruft einen Wert ab, der angibt, ob das Element über den Tastaturfokus verfügt.  Die- <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> Eigenschaft in den Basiselement Klassen Ruft einen Wert ab, der angibt, ob das Element oder eines seiner visuellen untergeordneten Elemente über den Tastaturfokus verfügt.  
  
 Wenn beim Starten der Anwendung der anfängliche Fokus festgelegt wird, muss sich das Element, das den Fokus erhält, in der visuellen Struktur des ursprünglichen Fensters befinden, das von der Anwendung geladen wird, und das-Element muss über <xref:System.Windows.UIElement.Focusable%2A> und <xref:System.Windows.UIElement.IsVisible%2A> auf festlegen `true` .  Die empfohlene Stelle zum Festlegen des ersten Fokus ist der- <xref:System.Windows.FrameworkElement.Loaded> Ereignishandler.  Ein <xref:System.Windows.Threading.Dispatcher> Rückruf kann auch durch Aufrufen von oder verwendet werden <xref:System.Windows.Threading.Dispatcher.Invoke%2A> <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> .  
  
<a name="Logical_Focus"></a>
## <a name="logical-focus"></a>Logischer Fokus  
 Der logische Fokus bezieht sich auf den <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> in einem Fokusbereich.  Ein Fokusbereich ist ein Element, das den <xref:System.Windows.Input.FocusManager.FocusedElement%2A> innerhalb seines Bereichs verfolgt.  Wenn der Tastaturfokus einen Fokusbereich verlässt, wird das Element den Tastaturfokus verlieren, jedoch behält es den logischen Fokus.  Wenn der Tastaturfokus zum Fokusbereich zurückkehrt, wird das Fokuselement Tastaturfokus erhalten.  Somit kann der Tastaturfokus zwischen mehreren Fokusbereichen geändert werden, aber es wird sichergestellt, dass das Fokuselement im Fokusbereich erneut Tastaturfokus erhält, wenn der Fokus wieder zum Fokusbereich zurückkehrt.  
  
 Es können mehrere Elemente vorhanden sein, die über logischen Fokus in einer Anwendung verfügen, jedoch kann es nur ein Element geben, das den logischen Fokus in einem bestimmten Fokusbereich besitzt.  
  
 Ein Element, das den Tastaturfokus besitzt, verfügt über den logischen Fokus innerhalb des Fokusbereichs, dem er angehört.  
  
 Ein Element kann in einen Fokusbereich in umgewandelt werden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , indem die <xref:System.Windows.Input.FocusManager> angefügte-Eigenschaft auf festgelegt wird <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> `true` .  Im Code kann ein Element in einen Fokusbereich umgewandelt werden, indem aufgerufen wird <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> .  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.StackPanel> durch Festlegen der angefügten-Eigenschaft in einen Fokusbereich umgewandelt <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> .  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>Gibt den Fokusbereich für das angegebene Element zurück.  
  
 Klassen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , bei denen es sich standardmäßig um Schwerpunktbereiche handelt, sind <xref:System.Windows.Window> , <xref:System.Windows.Controls.MenuItem> , <xref:System.Windows.Controls.ToolBar> und <xref:System.Windows.Controls.ContextMenu> .  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>Ruft das fokussierte Element für den angegebenen Fokusbereich ab.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>legt das fokussierte Element im angegebenen Fokusbereich fest.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>wird normalerweise verwendet, um das anfängliche Fokus Element festzulegen.  
  
 Das folgende Beispiel legt das Fokuselement auf einen Fokusbereich fest und ruft das Fokuselement eines Fokusbereichs ab.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>
## <a name="keyboard-navigation"></a>Tastaturnavigation  
 Die- <xref:System.Windows.Input.KeyboardNavigation> Klasse ist für die Implementierung der Standardtastatur Fokus Navigation verantwortlich, wenn eine der Navigationstasten gedrückt wird.  Die Navigationstasten sind: TAB, UMSCHALT+TAB, STRG+TAB, STRG+UMSCHALT+TAB, PFEIL-NACH-OBEN, PFEIL-NACH-UNTEN, PFEIL-NACH LINKS und PFEIL-NACH-RECHTS.  
  
 Das Navigationsverhalten eines Navigations Containers kann geändert werden, indem die angefügten <xref:System.Windows.Input.KeyboardNavigation> Eigenschaften <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> , und festgelegt werden <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A> <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A> .  Diese Eigenschaften sind vom Typ <xref:System.Windows.Input.KeyboardNavigationMode> , und die möglichen Werte lauten <xref:System.Windows.Input.KeyboardNavigationMode.Continue> ,, <xref:System.Windows.Input.KeyboardNavigationMode.Local> <xref:System.Windows.Input.KeyboardNavigationMode.Contained> , <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> , <xref:System.Windows.Input.KeyboardNavigationMode.Once> und <xref:System.Windows.Input.KeyboardNavigationMode.None> .  Der Standardwert ist <xref:System.Windows.Input.KeyboardNavigationMode.Continue> . Dies bedeutet, dass das Element kein Navigations Container ist.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Menu> mit einer Reihe von- <xref:System.Windows.Controls.MenuItem> Objekten erstellt.  Die <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> angefügte-Eigenschaft ist <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> auf festgelegt <xref:System.Windows.Controls.Menu> .  Wenn der Fokus mithilfe der Tab-Taste in geändert wird <xref:System.Windows.Controls.Menu> , wird der Fokus von jedem Element verschoben, und wenn das letzte Element erreicht ist, wird der Fokus an das erste Element zurückgegeben.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>
## <a name="navigating-focus-programmatically"></a>Programmgesteuertes Navigieren des Fokus  
 Weitere APIs, die mit dem Fokus arbeiten, sind <xref:System.Windows.UIElement.MoveFocus%2A> und <xref:System.Windows.UIElement.PredictFocus%2A> .  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>ändert den Fokus auf das nächste Element in der Anwendung.  Eine <xref:System.Windows.Input.TraversalRequest> wird verwendet, um die Richtung anzugeben.   Der <xref:System.Windows.Input.FocusNavigationDirection> an weiter gegebene <xref:System.Windows.UIElement.MoveFocus%2A> gibt an, dass die verschiedenen Richtungen verschoben werden können, z <xref:System.Windows.Input.FocusNavigationDirection.First> . b., <xref:System.Windows.Input.FocusNavigationDirection.Last> <xref:System.Windows.Input.FocusNavigationDirection.Up> und <xref:System.Windows.Input.FocusNavigationDirection.Down> .  
  
 Im folgenden Beispiel wird verwendet <xref:System.Windows.FrameworkElement.MoveFocus%2A> , um das fokussierte Element zu ändern.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>Gibt das-Objekt zurück, das den Fokus erhält, wenn der Fokus geändert werden sollte.  Derzeit werden nur <xref:System.Windows.Input.FocusNavigationDirection.Up> , <xref:System.Windows.Input.FocusNavigationDirection.Down> , <xref:System.Windows.Input.FocusNavigationDirection.Left> und <xref:System.Windows.Input.FocusNavigationDirection.Right> von unterstützt <xref:System.Windows.FrameworkElement.PredictFocus%2A> .  
  
<a name="Focus_Events"></a>
## <a name="focus-events"></a>Fokusereignisse  
 Die Ereignisse im Zusammenhang mit dem Tastaturfokus sind <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> , <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> und <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus> <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> .  Die Ereignisse werden als angefügte Ereignisse in der- <xref:System.Windows.Input.Keyboard> Klasse definiert, sind aber leichter als äquivalente Routing Ereignisse in den Basiselement Klassen zugänglich.  Weitere Informationen zu Ereignissen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>wird ausgelöst, wenn das Element den Tastaturfokus erhält.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>wird ausgelöst, wenn das Element den Tastaturfokus verliert.  Wenn das <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> -Ereignis oder das <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> -Ereignis behandelt wird und <xref:System.Windows.RoutedEventArgs.Handled%2A> auf festgelegt ist `true` , wird der Fokus nicht geändert.  
  
 Im folgenden Beispiel werden die <xref:System.Windows.UIElement.GotKeyboardFocus> -und- <xref:System.Windows.UIElement.LostKeyboardFocus> Ereignishandler an einen angefügt <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Wenn das den <xref:System.Windows.Controls.TextBox> Tastaturfokus erhält, <xref:System.Windows.Controls.Control.Background%2A> wird die-Eigenschaft von <xref:System.Windows.Controls.TextBox> in geändert <xref:System.Windows.Media.Brushes.LightBlue%2A> .  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Wenn das den <xref:System.Windows.Controls.TextBox> Tastaturfokus verliert, <xref:System.Windows.Controls.Control.Background%2A> wird die-Eigenschaft des-Objekts <xref:System.Windows.Controls.TextBox> wieder in weiß geändert.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Die Ereignisse im Zusammenhang mit dem logischen Fokus sind <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> .  Diese Ereignisse werden für die <xref:System.Windows.Input.FocusManager> als angefügte Ereignisse definiert, aber <xref:System.Windows.Input.FocusManager> nicht die CLR-Ereigniswrapper.  <xref:System.Windows.UIElement>und machen <xref:System.Windows.ContentElement> diese Ereignisse bequemer verfügbar.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [Übersicht über die Eingabe](input-overview.md)
- [Übersicht über Basiselemente](base-elements-overview.md)
