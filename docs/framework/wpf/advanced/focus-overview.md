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
ms.openlocfilehash: 72b866d714e6a77020bdb74843c3aaa0ba0c3278
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073883"
---
# <a name="focus-overview"></a>Fokus - Übersicht
In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es zwei Hauptkonzepte, die den Fokus betreffen: Tastaturfokus und logischer Fokus.  Tastaturfokus bezieht sich auf das Element, das Tastatureingaben empfängt, und der logische Fokus bezieht sich auf das Element in einem Fokusbereich, der Fokus besitzt.  Diese Konzepte werden in dieser Übersicht ausführlich erläutert.  Für das Erstellen von komplexen Anwendungen, die über mehrere Bereiche verfügen, in denen Fokus abgerufen werden kann, ist es wichtig den Unterschied der Konzepte zu verstehen.  
  
 Sind die wichtigsten Klassen, die an der fokusverwaltung beteiligt sind die <xref:System.Windows.Input.Keyboard> -Klasse, die <xref:System.Windows.Input.FocusManager> -Klasse, und das Basiselement Klassen, z. B. <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement>.  Weitere Informationen zu den Basiselementen finden Sie unter [Übersicht über Basiselemente](base-elements-overview.md).  
  
 Die <xref:System.Windows.Input.Keyboard> -Klasse betrifft in erster Linie mit dem Tastaturfokus und die <xref:System.Windows.Input.FocusManager> ist in erster Linie mit den logischen Fokus, aber dies ist keine absolute Unterscheidung.  Ein Element, das über den Tastaturfokus verfügt, besitzt auch einen logischen Fokus, aber ein Element mit dem logischen Fokus muss nicht unbedingt über den Tastaturfokus verfügen.  Dies ist offensichtlich, wenn Sie verwenden die <xref:System.Windows.Input.Keyboard> Klasse das Element festgelegt werden, die über den Tastaturfokus, dafür legt auch den logischen Fokus auf das Element.  

<a name="Keyboard_Focus"></a>   
## <a name="keyboard-focus"></a>Tastaturfokus  
 Der Tastaturfokus bezieht sich auf das Element, das derzeit Tastatureingaben empfängt.  Es kann nur ein Element auf dem gesamten Desktop geben, das über den Tastaturfokus verfügt.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], das Element, das den Tastaturfokus hat <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> festgelegt `true`.  Die statische Eigenschaft <xref:System.Windows.Input.Keyboard.FocusedElement%2A> auf die <xref:System.Windows.Input.Keyboard> Klasse ruft das Element, das derzeit Tastaturfokus besitzt.  
  
 In der Reihenfolge für ein Element den Tastaturfokus hat, erhalten die <xref:System.Windows.UIElement.Focusable%2A> und <xref:System.Windows.UIElement.IsVisible%2A> Eigenschaften in den Basiselementen müssen festgelegt werden, um `true`.  Einige Klassen, z. B. die <xref:System.Windows.Controls.Panel> Basisklasse, haben <xref:System.Windows.UIElement.Focusable%2A> festgelegt `false` standardmäßig aus diesem Grund müssen Sie festlegen <xref:System.Windows.UIElement.Focusable%2A> zu `true` sollten Sie dieses Element den Tastaturfokus erhalten können.  
  
 Tastaturfokus kann durch die Benutzerinteraktion mit [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] abgerufen werden, z.B. durch das Wechseln mit der Tabulatortaste zu einem Element oder durch Klicken mit der Maus auf bestimmte Elemente.  Tastaturfokus kann auch programmgesteuert mithilfe von abgerufen werden die <xref:System.Windows.Input.Keyboard.Focus%2A> Methode für die <xref:System.Windows.Input.Keyboard> Klasse.  Die <xref:System.Windows.Input.Keyboard.Focus%2A> -Methode versucht, die den angegebene Element den Tastaturfokus erhalten.  Das zurückgegebene Element ist das Element mit Tastaturfokus, was möglicherweise ein anderes Element als angefordert sein kann, wenn das alte oder neue Fokusobjekt die Anforderung blockiert.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Input.Keyboard.Focus%2A> Methode zum Festlegen der Tastaturfokus auf einen <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Die <xref:System.Windows.UIElement.IsKeyboardFocused%2A> Eigenschaft in den Basiselementklassen ruft einen Wert, der angibt, ob das Element den Tastaturfokus verfügt.  Die <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> Eigenschaft in den Basiselementklassen ruft einen Wert, der angibt, ob das Element oder eines seiner visuellen untergeordneten Elemente den Tastaturfokus verfügt.  
  
 Das Element benötigen, sowie Wenn Anfangsfokus beim Start der Anwendung festlegen möchten, muss das Element, das Fokus erhalten in der visuellen Struktur des ersten von der Anwendung geladenen Fensters <xref:System.Windows.UIElement.Focusable%2A> und <xref:System.Windows.UIElement.IsVisible%2A> festgelegt `true`.  Der empfohlene Ort Anfangsfokus ist in der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.  Ein <xref:System.Windows.Threading.Dispatcher> Rückruf kann auch verwendet werden, durch den Aufruf <xref:System.Windows.Threading.Dispatcher.Invoke%2A> oder <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.  
  
<a name="Logical_Focus"></a>   
## <a name="logical-focus"></a>Logischer Fokus  
 Der logische Fokus bezieht sich auf die <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> in einem Fokusbereich.  Ein Fokusbereich ist ein Element, das verfolgt die <xref:System.Windows.Input.FocusManager.FocusedElement%2A> innerhalb seines Bereichs.  Wenn der Tastaturfokus einen Fokusbereich verlässt, wird das Element den Tastaturfokus verlieren, jedoch behält es den logischen Fokus.  Wenn der Tastaturfokus zum Fokusbereich zurückkehrt, wird das Fokuselement Tastaturfokus erhalten.  Somit kann der Tastaturfokus zwischen mehreren Fokusbereichen geändert werden, aber es wird sichergestellt, dass das Fokuselement im Fokusbereich erneut Tastaturfokus erhält, wenn der Fokus wieder zum Fokusbereich zurückkehrt.  
  
 Es können mehrere Elemente mit logischem Fokus in einer Anwendung vorhanden sein, aber es kann möglicherweise nur ein Element mit dem logischen Fokus in einem bestimmten Fokusbereich geben.  
  
 Ein Element, das den Tastaturfokus besitzt, verfügt über den logischen Fokus innerhalb des Fokusbereichs, dem er angehört.  
  
 Ein Element kann aktiviert werden, in einen Fokusbereich in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] durch Festlegen der <xref:System.Windows.Input.FocusManager> angefügte Eigenschaft <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> zu `true`.  Im Code wird ein Element kann aktiviert werden in einen Fokusbereich durch Aufrufen von <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.StackPanel> in einen Fokusbereich durch Festlegen der <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> angefügte Eigenschaft.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A> Gibt den Fokusbereich für das angegebene Element zurück.  
  
 Klassen im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die standardmäßig Fokusbereiche sind, sind <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, und <xref:System.Windows.Controls.ContextMenu>.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> Ruft das Fokuselement für den angegebenen Fokusbereich ab.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> Legt das Fokuselement im angegebenen Fokusbereich fest.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> wird normalerweise verwendet, um das erste Fokuselement festzulegen.  
  
 Das folgende Beispiel legt das Fokuselement auf einen Fokusbereich fest und ruft das Fokuselement eines Fokusbereichs ab.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## <a name="keyboard-navigation"></a>Tastaturnavigation  
 Die <xref:System.Windows.Input.KeyboardNavigation> -Klasse ist verantwortlich für das Implementieren der Standardtastaturfokusnavigation, wenn eine der Navigationstasten gedrückt wird.  Die Navigationstasten sind: Registerkarte, UMSCHALT + TAB, STRG + TAB, STRG + UMSCHALT + TAB, nach-oben, nach-unten, nach-links und nach-rechts-Tasten.  
  
 Das Navigationsverhalten eines Navigationscontainers kann geändert werden, indem die angefügte <xref:System.Windows.Input.KeyboardNavigation> Eigenschaften <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, und <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.  Diese Eigenschaften sind vom Typ <xref:System.Windows.Input.KeyboardNavigationMode> und die möglichen Werte sind <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, und <xref:System.Windows.Input.KeyboardNavigationMode.None>.  Der Standardwert ist <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, was bedeutet, dass das Element ist kein navigationscontainer.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Menu> mit einer Reihe von <xref:System.Windows.Controls.MenuItem> Objekte.  Die <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> angefügte Eigenschaft nastaven NA hodnotu <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> auf die <xref:System.Windows.Controls.Menu>.  Wenn der Fokus geändert wird, mit der Tab-Taste in der <xref:System.Windows.Controls.Menu>, den Fokus aus jedem Element verschoben wird, und wenn das letzte Element erreicht, wird den Fokus auf das erste Element zurück.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## <a name="navigating-focus-programmatically"></a>Programmgesteuertes Navigieren des Fokus  
 Zusätzliche [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] zum Arbeiten mit Fokus sind <xref:System.Windows.UIElement.MoveFocus%2A> und <xref:System.Windows.UIElement.PredictFocus%2A>.  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A> Ändert den Fokus auf das nächste Element in der Anwendung.  Ein <xref:System.Windows.Input.TraversalRequest> wird verwendet, um die Richtung anzugeben.   Die <xref:System.Windows.Input.FocusNavigationDirection> übergeben <xref:System.Windows.UIElement.MoveFocus%2A> gibt an, die verschiedenen Richtungen des Fokus verschoben werden kann, wie z. B. <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> und <xref:System.Windows.Input.FocusNavigationDirection.Down>.  
  
 Im folgenden Beispiel wird <xref:System.Windows.FrameworkElement.MoveFocus%2A> so ändern Sie das fokussierte Element.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A> Gibt das Objekt, das Fokus erhalten würde, wenn der Fokus geändert werden würde.  Derzeit nur <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, und <xref:System.Windows.Input.FocusNavigationDirection.Right> werden von unterstützt <xref:System.Windows.FrameworkElement.PredictFocus%2A>.  
  
<a name="Focus_Events"></a>   
## <a name="focus-events"></a>Fokusereignisse  
 Die mit Tastaturfokus verknüpften Ereignisse sind <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> und <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.  Die Ereignisse werden als angefügte Ereignisse definiert, auf die <xref:System.Windows.Input.Keyboard> Klasse, sondern als entsprechende Routingereignissen in Basiselementklassen sofort zugänglich sind.  Weitere Informationen zu Ereignissen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> wird ausgelöst, wenn das Element den Tastaturfokus erhält.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> wird ausgelöst, wenn das Element den Tastaturfokus verliert.  Wenn die <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> Ereignis oder die <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> Ereignis erfolgt und <xref:System.Windows.RoutedEventArgs.Handled%2A> nastaven NA hodnotu `true`, und klicken Sie dann den Fokus nicht ändern.  
  
 Im folgenden Beispiel wird <xref:System.Windows.UIElement.GotKeyboardFocus> und <xref:System.Windows.UIElement.LostKeyboardFocus> Ereignishandler eine <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Wenn die <xref:System.Windows.Controls.TextBox> Tastaturfokus erhält, die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft der <xref:System.Windows.Controls.TextBox> geändert wird, um <xref:System.Windows.Media.Brushes.LightBlue%2A>.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Wenn die <xref:System.Windows.Controls.TextBox> den Tastaturfokus verliert, die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft der <xref:System.Windows.Controls.TextBox> wieder auf Weiß geändert wird.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Die Ereignisse im Zusammenhang mit logischen Fokus sind <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus>.  Diese Ereignisse werden definiert, auf die <xref:System.Windows.Input.FocusManager> als angefügte Ereignisse, aber die <xref:System.Windows.Input.FocusManager> macht keine CLR-Ereigniswrapper verfügbar.  <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> einfacher, diese Ereignisse verfügbar zu machen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [Übersicht über die Eingabe](input-overview.md)
- [Übersicht über Basiselemente](base-elements-overview.md)
