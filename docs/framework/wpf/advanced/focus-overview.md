---
title: Fokus - Übersicht
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: 620839a0060469604d0affa6637c3cafac0f62c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="focus-overview"></a>Fokus - Übersicht
In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es zwei Hauptkonzepte, die den Fokus betreffen: Tastaturfokus und logischer Fokus.  Tastaturfokus bezieht sich auf das Element, das Tastatureingaben empfängt, und der logische Fokus bezieht sich auf das Element in einem Fokusbereich, der Fokus besitzt.  Diese Konzepte werden in dieser Übersicht ausführlich erläutert.  Für das Erstellen von komplexen Anwendungen, die über mehrere Bereiche verfügen, in denen Fokus abgerufen werden kann, ist es wichtig den Unterschied der Konzepte zu verstehen.  
  
 Die wichtigsten Klassen, die in fokusverwaltung einbezogen werden die <xref:System.Windows.Input.Keyboard> -Klasse, die <xref:System.Windows.Input.FocusManager> Klasse und das Basiselement Klassen, z. B. <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement>.  Weitere Informationen zu den Basiselementen finden Sie unter [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  
  
 Die <xref:System.Windows.Input.Keyboard> Klasse ist in erster Linie mit dem Tastaturfokus betroffenen und die <xref:System.Windows.Input.FocusManager> befasst sich hauptsächlich mit den logischen Fokus, dies ist jedoch keine absolute Unterscheidung.  Ein Element, das über den Tastaturfokus verfügt, besitzt auch einen logischen Fokus, aber ein Element mit dem logischen Fokus muss nicht unbedingt über den Tastaturfokus verfügen.  Dies ist offensichtlich, bei der Verwendung der <xref:System.Windows.Input.Keyboard> Klasse das Element festgelegt werden, die über den Tastaturfokus, verfügt legt auch der logische Fokus auf das Element.  
  

  
<a name="Keyboard_Focus"></a>   
## <a name="keyboard-focus"></a>Tastaturfokus  
 Der Tastaturfokus bezieht sich auf das Element, das derzeit Tastatureingaben empfängt.  Es kann nur ein Element auf dem gesamten Desktop geben, das über den Tastaturfokus verfügt.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], weist das Element, das über den Tastaturfokus verfügt <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> festgelegt `true`.  Die statische Eigenschaft <xref:System.Windows.Input.Keyboard.FocusedElement%2A> auf die <xref:System.Windows.Input.Keyboard> Klasse ruft das Element, das derzeit über den Tastaturfokus verfügt.  
  
 In der Reihenfolge nach einem Element den Tastaturfokus, erhalten die <xref:System.Windows.UIElement.Focusable%2A> und <xref:System.Windows.UIElement.IsVisible%2A> Eigenschaften auf die Basiselemente müssen festgelegt werden, um `true`.  Einige Klassen, z. B. die <xref:System.Windows.Controls.Panel> Basisklasse haben <xref:System.Windows.UIElement.Focusable%2A> festgelegt `false` standardmäßig; aus diesem Grund müssen Sie festlegen <xref:System.Windows.UIElement.Focusable%2A> auf `true` gegebenenfalls derartiges Element den Tastaturfokus erhalten können.  
  
 Tastaturfokus kann durch die Benutzerinteraktion mit [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] abgerufen werden, z.B. durch das Wechseln mit der Tabulatortaste zu einem Element oder durch Klicken mit der Maus auf bestimmte Elemente.  Über den Tastaturfokus kann auch programmgesteuert mithilfe von abgerufen werden die <xref:System.Windows.Input.Keyboard.Focus%2A> Methode für die <xref:System.Windows.Input.Keyboard> Klasse.  Die <xref:System.Windows.Input.Keyboard.Focus%2A> Methode versucht, das angegebene Element den Tastaturfokus erhalten.  Das zurückgegebene Element ist das Element mit Tastaturfokus, was möglicherweise ein anderes Element als angefordert sein kann, wenn das alte oder neue Fokusobjekt die Anforderung blockiert.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Input.Keyboard.Focus%2A> Methode, um den Tastaturfokus auf einzurichten eine <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Die <xref:System.Windows.UIElement.IsKeyboardFocused%2A> Eigenschaft in den Klassen Basiselement Ruft einen Wert, der angibt, ob das Element den Tastaturfokus verfügt.  Die <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> Eigenschaft in den Klassen Basiselement Ruft einen Wert, der angibt, ob das Element oder eine seiner untergeordneten visuellen Elemente über den Tastaturfokus verfügt.  
  
 Wenn Anfangsfokus beim Start der Anwendung festgelegt wird, muss das Element den Fokus erhalten in der visuellen Struktur des Fensters ersten von der Anwendung geladen werden, und das Element muss <xref:System.Windows.UIElement.Focusable%2A> und <xref:System.Windows.UIElement.IsVisible%2A> festgelegt `true`.  Der empfohlene Speicherort für Anfangsfokus ist die <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.  Ein <xref:System.Windows.Threading.Dispatcher> Rückruf kann auch verwendet werden, durch den Aufruf <xref:System.Windows.Threading.Dispatcher.Invoke%2A> oder <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.  
  
<a name="Logical_Focus"></a>   
## <a name="logical-focus"></a>Logischer Fokus  
 Der logische Fokus bezieht sich auf die <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> in einem Fokusbereich.  Ein Fokusbereich ist ein Element, das verfolgt die <xref:System.Windows.Input.FocusManager.FocusedElement%2A> innerhalb dieses Bereichs.  Wenn der Tastaturfokus einen Fokusbereich verlässt, wird das Element den Tastaturfokus verlieren, jedoch behält es den logischen Fokus.  Wenn der Tastaturfokus zum Fokusbereich zurückkehrt, wird das Fokuselement Tastaturfokus erhalten.  Somit kann der Tastaturfokus zwischen mehreren Fokusbereichen geändert werden, aber es wird sichergestellt, dass das Fokuselement im Fokusbereich erneut Tastaturfokus erhält, wenn der Fokus wieder zum Fokusbereich zurückkehrt.  
  
 Es können mehrere Elemente mit logischem Fokus in einer Anwendung vorhanden sein, aber es kann möglicherweise nur ein Element mit dem logischen Fokus in einem bestimmten Fokusbereich geben.  
  
 Ein Element, das den Tastaturfokus besitzt, verfügt über den logischen Fokus innerhalb des Fokusbereichs, dem er angehört.  
  
 Ein Element kann in einem Fokusbereich aktiviert [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] durch Festlegen der <xref:System.Windows.Input.FocusManager> angefügte Eigenschaft <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> auf `true`.  Im Code wird ein Element kann aktiviert werden in den Gültigkeitsbereich einer Fokus durch Aufrufen von <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.StackPanel> in einem Fokusbereich durch Festlegen der <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> -Eigenschaft.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A> Gibt den Fokusbereich für das angegebene Element zurück.  
  
 Klassen im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind die Fokusbereiche in der Standardeinstellung sind <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, und <xref:System.Windows.Controls.ContextMenu>.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> Ruft das Element für den angegebenen Fokusbereich ab.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> Legt Elements mit Fokus im angegebenen Fokusbereich fest.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> Legen Sie das erste Element wird in der Regel verwendet werden.  
  
 Das folgende Beispiel legt das Fokuselement auf einen Fokusbereich fest und ruft das Fokuselement eines Fokusbereichs ab.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## <a name="keyboard-navigation"></a>Tastaturnavigation  
 Die <xref:System.Windows.Input.KeyboardNavigation> -Klasse ist verantwortlich für das standardmäßig den Fokus Tastaturnavigation implementieren, wenn eine der Navigationstasten gedrückt wird.  Die Navigationstasten sind: TAB, UMSCHALT+TAB, STRG+TAB, STRG+UMSCHALT+TAB, PFEIL-NACH-OBEN, PFEIL-NACH-UNTEN, PFEIL-NACH LINKS und PFEIL-NACH-RECHTS.  
  
 Das Verhalten eines Navigationscontainers kann geändert werden, durch Festlegen der angefügte <xref:System.Windows.Input.KeyboardNavigation> Eigenschaften <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, und <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.  Diese Eigenschaften sind vom Typ <xref:System.Windows.Input.KeyboardNavigationMode> und die möglichen Werte sind <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, und <xref:System.Windows.Input.KeyboardNavigationMode.None>.  Der Standardwert ist <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, was bedeutet, dass das Element ist kein Container Navigation.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Menu> mit einer Anzahl von <xref:System.Windows.Controls.MenuItem> Objekte.  Die <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> auf gesetzte angehängte Eigenschaft <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> auf die <xref:System.Windows.Controls.Menu>.  Wenn der Fokus geändert wird, mit der Tab-Taste in der <xref:System.Windows.Controls.Menu>, wird der Fokus aus jedem Element und bei das letzte Element erreichen den Fokus auf das erste Element zurück.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## <a name="navigating-focus-programmatically"></a>Programmgesteuertes Navigieren des Fokus  
 Zusätzliche [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] mit Fokus sind <xref:System.Windows.UIElement.MoveFocus%2A> und <xref:System.Windows.UIElement.PredictFocus%2A>.  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A> Ändert den Fokus auf das nächste Element in der Anwendung.  Ein <xref:System.Windows.Input.TraversalRequest> wird verwendet, um die Richtung anzugeben.   Die <xref:System.Windows.Input.FocusNavigationDirection> übergeben <xref:System.Windows.UIElement.MoveFocus%2A> gibt an, die verschiedene Richtungen Fokus kann verschoben werden, z. B. <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> und <xref:System.Windows.Input.FocusNavigationDirection.Down>.  
  
 Im folgenden Beispiel wird <xref:System.Windows.FrameworkElement.MoveFocus%2A> Elements mit Fokus ändern.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A> Gibt das Objekt den Fokus erhalten, wenn der Fokus geändert werden, wurden zurück.  Derzeit nur <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, und <xref:System.Windows.Input.FocusNavigationDirection.Right> werden von unterstützt <xref:System.Windows.FrameworkElement.PredictFocus%2A>.  
  
<a name="Focus_Events"></a>   
## <a name="focus-events"></a>Fokusereignisse  
 Die Ereignisse im Zusammenhang mit den Tastaturfokus sind <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> und <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.  Die Ereignisse werden als angefügte Ereignisse definiert, auf die <xref:System.Windows.Input.Keyboard> Klasse, aber schneller als die entsprechende Routingereignisse Basiselement Klassen zugegriffen werden.  Weitere Informationen zu Ereignissen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> wird ausgelöst, wenn das Element den Tastaturfokus erhält.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> wird ausgelöst, wenn das Element den Tastaturfokus verliert.  Wenn die <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> Ereignis oder die <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> Ereignis behandelt wird und <xref:System.Windows.RoutedEventArgs.Handled%2A> festgelegt ist, um `true`, und klicken Sie dann den Fokus nicht ändert.  
  
 Das folgende Beispiel fügt <xref:System.Windows.UIElement.GotKeyboardFocus> und <xref:System.Windows.UIElement.LostKeyboardFocus> Ereignishandler an einen <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Wenn die <xref:System.Windows.Controls.TextBox> Tastaturfokus erhält, die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft der <xref:System.Windows.Controls.TextBox> geändert wird, um <xref:System.Windows.Media.Brushes.LightBlue%2A>.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Wenn die <xref:System.Windows.Controls.TextBox> den Tastaturfokus verliert, der <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft von der <xref:System.Windows.Controls.TextBox> nicht wieder in Weiß geändert wird.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Die Ereignisse im Zusammenhang mit den logischen Fokus sind <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus>.  Diese Ereignisse werden definiert, auf die <xref:System.Windows.Input.FocusManager> als angefügte Ereignisse jedoch <xref:System.Windows.Input.FocusManager> macht nicht Wrappern für CLR-Ereignis.  <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> komfortablere, diese Ereignisse verfügbar zu machen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Input.FocusManager>  
 <xref:System.Windows.UIElement>  
 <xref:System.Windows.ContentElement>  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md)
