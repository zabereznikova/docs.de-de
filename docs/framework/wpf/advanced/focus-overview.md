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
ms.openlocfilehash: de788ec3f0628ff2f7c422c76c73ff7985424113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186666"
---
# <a name="focus-overview"></a>Fokus - Übersicht
In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es zwei Hauptkonzepte, die den Fokus betreffen: Tastaturfokus und logischer Fokus.  Tastaturfokus bezieht sich auf das Element, das Tastatureingaben empfängt, und der logische Fokus bezieht sich auf das Element in einem Fokusbereich, der Fokus besitzt.  Diese Konzepte werden in dieser Übersicht ausführlich erläutert.  Für das Erstellen von komplexen Anwendungen, die über mehrere Bereiche verfügen, in denen Fokus abgerufen werden kann, ist es wichtig den Unterschied der Konzepte zu verstehen.  
  
 Die Hauptklassen, die an <xref:System.Windows.Input.Keyboard> der Fokusverwaltung teilnehmen, sind die Klasse, die <xref:System.Windows.Input.FocusManager> Klasse und die Basiselementklassen, z. B. <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement>.  Weitere Informationen zu den Basiselementen finden Sie unter [Übersicht über Basiselemente](base-elements-overview.md).  
  
 Die <xref:System.Windows.Input.Keyboard> Klasse beschäftigt sich in <xref:System.Windows.Input.FocusManager> erster Linie mit Tastaturfokus und die in erster Linie mit logischen Fokus, aber dies ist keine absolute Unterscheidung.  Ein Element, das über den Tastaturfokus verfügt, besitzt auch einen logischen Fokus, aber ein Element mit dem logischen Fokus muss nicht unbedingt über den Tastaturfokus verfügen.  Dies wird angezeigt, <xref:System.Windows.Input.Keyboard> wenn Sie die Klasse verwenden, um das Element mit Tastaturfokus festzulegen, da es auch den logischen Fokus auf das Element legt.  

<a name="Keyboard_Focus"></a>
## <a name="keyboard-focus"></a>Tastaturfokus  
 Der Tastaturfokus bezieht sich auf das Element, das derzeit Tastatureingaben empfängt.  Es kann nur ein Element auf dem gesamten Desktop geben, das über den Tastaturfokus verfügt.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]hat <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> das Element mit Demtastaturfokus auf `true`festgelegt.  Die statische <xref:System.Windows.Input.Keyboard.FocusedElement%2A> Eigenschaft <xref:System.Windows.Input.Keyboard> für die Klasse ruft das Element ab, das derzeit über den Tastaturfokus verfügt.  
  
 Damit ein Element den Tastaturfokus <xref:System.Windows.UIElement.Focusable%2A> erhält, <xref:System.Windows.UIElement.IsVisible%2A> müssen die und die `true`Eigenschaften auf den Basiselementen auf festgelegt werden.  Einige Klassen, z. B. die <xref:System.Windows.Controls.Panel> Basisklasse, haben <xref:System.Windows.UIElement.Focusable%2A> standardmäßig auf `false` .. Daher müssen Sie <xref:System.Windows.UIElement.Focusable%2A> `true` festlegen, ob ein solches Element in der Lage sein soll, den Tastaturfokus zu erhalten.  
  
 Tastaturfokus kann durch die Benutzerinteraktion mit [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] abgerufen werden, z.B. durch das Wechseln mit der Tabulatortaste zu einem Element oder durch Klicken mit der Maus auf bestimmte Elemente.  Der Tastaturfokus kann auch programmgesteuert <xref:System.Windows.Input.Keyboard.Focus%2A> mithilfe der <xref:System.Windows.Input.Keyboard> Methode für die Klasse abgerufen werden.  Die <xref:System.Windows.Input.Keyboard.Focus%2A> Methode versucht, dem angegebenen Element Tastaturfokus zu geben.  Das zurückgegebene Element ist das Element mit Tastaturfokus, was möglicherweise ein anderes Element als angefordert sein kann, wenn das alte oder neue Fokusobjekt die Anforderung blockiert.  
  
 Im folgenden Beispiel <xref:System.Windows.Input.Keyboard.Focus%2A> wird die Methode <xref:System.Windows.Controls.Button>zum Festlegen des Tastaturfokus auf eine verwendet.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Die <xref:System.Windows.UIElement.IsKeyboardFocused%2A> Eigenschaft in den Basiselementklassen ruft einen Wert ab, der angibt, ob das Element über einen Tastaturfokus verfügt.  Die <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> Eigenschaft in den Basiselementklassen ruft einen Wert ab, der angibt, ob das Element oder eines seiner visuellen untergeordneten Elemente den Tastaturfokus hat.  
  
 Wenn Sie den Anfänglichen Fokus beim Anwendungsstart festlegen, muss sich das Element, das den Fokus <xref:System.Windows.UIElement.Focusable%2A> <xref:System.Windows.UIElement.IsVisible%2A> erhält, `true`in der visuellen Struktur des ursprünglichen Fensters befinden, das von der Anwendung geladen wird, und das Element muss über haben und auf festgelegt sein.  Der empfohlene Ort zum Festlegen <xref:System.Windows.FrameworkElement.Loaded> des Anfangsfokus befindet sich im Ereignishandler.  Ein <xref:System.Windows.Threading.Dispatcher> Rückruf kann auch durch <xref:System.Windows.Threading.Dispatcher.Invoke%2A> <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>Aufrufen oder verwendet werden.  
  
<a name="Logical_Focus"></a>
## <a name="logical-focus"></a>Logischer Fokus  
 Logischer Fokus <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> bezieht sich auf den in einem Fokusbereich.  Ein Fokusbereich ist ein Element, <xref:System.Windows.Input.FocusManager.FocusedElement%2A> das den innerhalb seines Gültigkeitsbereichs nachverfolgt.  Wenn der Tastaturfokus einen Fokusbereich verlässt, wird das Element den Tastaturfokus verlieren, jedoch behält es den logischen Fokus.  Wenn der Tastaturfokus zum Fokusbereich zurückkehrt, wird das Fokuselement Tastaturfokus erhalten.  Somit kann der Tastaturfokus zwischen mehreren Fokusbereichen geändert werden, aber es wird sichergestellt, dass das Fokuselement im Fokusbereich erneut Tastaturfokus erhält, wenn der Fokus wieder zum Fokusbereich zurückkehrt.  
  
 Es können mehrere Elemente vorhanden sein, die über logischen Fokus in einer Anwendung verfügen, jedoch kann es nur ein Element geben, das den logischen Fokus in einem bestimmten Fokusbereich besitzt.  
  
 Ein Element, das den Tastaturfokus besitzt, verfügt über den logischen Fokus innerhalb des Fokusbereichs, dem er angehört.  
  
 Ein Element kann in einen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Fokusbereich <xref:System.Windows.Input.FocusManager> umgewandelt <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> werden, indem die angefügte Eigenschaft auf `true`.  Im Code kann ein Element durch Aufrufen <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>in einen Fokusbereich umgewandelt werden.  
  
 Im folgenden Beispiel <xref:System.Windows.Controls.StackPanel> wird ein in <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> einen Fokusbereich umgewandelt, indem die angefügte Eigenschaft gesetzt wird.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>gibt den Fokusbereich für das angegebene Element zurück.  
  
 Klassen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in denen Fokusbereiche <xref:System.Windows.Window>standardmäßig <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.ToolBar>sind, <xref:System.Windows.Controls.ContextMenu>sind , , und .  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>ruft das fokussierte Element für den angegebenen Fokusbereich ab.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>legt das fokussierte Element im angegebenen Fokusbereich fest.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>wird in der Regel verwendet, um das anfängliche fokussierte Element festzulegen.  
  
 Das folgende Beispiel legt das Fokuselement auf einen Fokusbereich fest und ruft das Fokuselement eines Fokusbereichs ab.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>
## <a name="keyboard-navigation"></a>Tastaturnavigation  
 Die <xref:System.Windows.Input.KeyboardNavigation> Klasse ist für die Implementierung der standardmäßigen Tastaturfokusnavigation verantwortlich, wenn eine der Navigationstasten gedrückt wird.  Die Navigationstasten sind: TAB, UMSCHALT+TAB, STRG+TAB, STRG+UMSCHALT+TAB, PFEIL-NACH-OBEN, PFEIL-NACH-UNTEN, PFEIL-NACH LINKS und PFEIL-NACH-RECHTS.  
  
 Das Navigationsverhalten eines Navigationscontainers kann durch <xref:System.Windows.Input.KeyboardNavigation> Festlegen <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>der <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>angefügten Eigenschaften , und geändert werden.  Diese Eigenschaften sind <xref:System.Windows.Input.KeyboardNavigationMode> vom Typ, <xref:System.Windows.Input.KeyboardNavigationMode.Continue> <xref:System.Windows.Input.KeyboardNavigationMode.Local>und <xref:System.Windows.Input.KeyboardNavigationMode.Contained> <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>die <xref:System.Windows.Input.KeyboardNavigationMode.Once>möglichen <xref:System.Windows.Input.KeyboardNavigationMode.None>Werte sind , , , , , und .  Der Standardwert <xref:System.Windows.Input.KeyboardNavigationMode.Continue>ist , was bedeutet, dass das Element kein Navigationscontainer ist.  
  
 Im folgenden Beispiel <xref:System.Windows.Controls.Menu> wird eine <xref:System.Windows.Controls.MenuItem> mit einer Reihe von Objekten erstellt.  Die <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> angefügte Eigenschaft <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> ist <xref:System.Windows.Controls.Menu>auf der festgelegt.  Wenn der Fokus mit der <xref:System.Windows.Controls.Menu>Tabulatortaste innerhalb der geändert wird, wird der Fokus von jedem Element verschoben, und wenn das letzte Element erreicht ist, kehrt der Fokus zum ersten Element zurück.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>
## <a name="navigating-focus-programmatically"></a>Programmgesteuertes Navigieren des Fokus  
 Zusätzliche API für die <xref:System.Windows.UIElement.MoveFocus%2A> <xref:System.Windows.UIElement.PredictFocus%2A>Arbeit mit Fokus sind und .  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>ändert den Fokus auf das nächste Element in der Anwendung.  A <xref:System.Windows.Input.TraversalRequest> wird verwendet, um die Richtung anzugeben.   Der <xref:System.Windows.Input.FocusNavigationDirection> <xref:System.Windows.UIElement.MoveFocus%2A> übergebene, um die verschiedenen Richtungen angibt, kann verschoben werden, z. <xref:System.Windows.Input.FocusNavigationDirection.First>B. , <xref:System.Windows.Input.FocusNavigationDirection.Last> <xref:System.Windows.Input.FocusNavigationDirection.Up> und <xref:System.Windows.Input.FocusNavigationDirection.Down>.  
  
 Im folgenden <xref:System.Windows.FrameworkElement.MoveFocus%2A> Beispiel wird das fokussierte Element geändert.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>gibt das Objekt zurück, das bei einer Änderung des Fokus den Fokus erhalten würde.  Derzeit nur <xref:System.Windows.Input.FocusNavigationDirection.Up> <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, <xref:System.Windows.Input.FocusNavigationDirection.Right> , <xref:System.Windows.FrameworkElement.PredictFocus%2A>und werden von unterstützt.  
  
<a name="Focus_Events"></a>
## <a name="focus-events"></a>Fokusereignisse  
 Die Ereignisse im Zusammenhang <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> mit <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus> <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>dem Tastaturfokus sind , und , .  Die Ereignisse werden als angefügte Ereignisse für die <xref:System.Windows.Input.Keyboard> Klasse definiert, sind jedoch leichter als äquivalente Routingereignisse für die Basiselementklassen zugänglich.  Weitere Informationen zu Ereignissen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>wird ausgelöst, wenn das Element den Tastaturfokus erhält.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>wird ausgelöst, wenn das Element den Tastaturfokus verliert.  Wenn <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> das Ereignis <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> oder das <xref:System.Windows.RoutedEventArgs.Handled%2A> Ereignis behandelt `true`wird und auf festgelegt ist, ändert sich der Fokus nicht.  
  
 Im folgenden Beispiel <xref:System.Windows.UIElement.GotKeyboardFocus> <xref:System.Windows.UIElement.LostKeyboardFocus> werden Anfüge- <xref:System.Windows.Controls.TextBox>und Ereignishandler an eine angefügt.  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Wenn <xref:System.Windows.Controls.TextBox> der Tastaturfokus erhält, <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.TextBox> wird die <xref:System.Windows.Media.Brushes.LightBlue%2A>Eigenschaft des in geändert.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Wenn <xref:System.Windows.Controls.TextBox> der Tastaturfokus <xref:System.Windows.Controls.Control.Background%2A> verliert, <xref:System.Windows.Controls.TextBox> wird die Eigenschaft des wieder in Weiß geändert.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Die Ereignisse im Zusammenhang <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus>mit dem logischen Fokus sind und .  Diese Ereignisse werden <xref:System.Windows.Input.FocusManager> auf den als <xref:System.Windows.Input.FocusManager> angefügten Ereignissen definiert, aber der macht CLR-Ereigniswrapper nicht verfügbar.  <xref:System.Windows.UIElement>und <xref:System.Windows.ContentElement> setzen diese Ereignisse bequemer zur Welt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [Übersicht über die Eingabe](input-overview.md)
- [Übersicht über Basiselemente](base-elements-overview.md)
