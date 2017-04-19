---
title: "Fokus - &#220;bersicht | Microsoft Docs"
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
  - "Anwendungen, Fokus"
  - "Fokus in Anwendungen"
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Fokus - &#220;bersicht
In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es hinsichtlich des Fokus zwei Hauptkonzepte: den Tastaturfokus und den logischen Fokus.  Tastaturfokus bezieht sich auf das Element, dem die Tastatureingabe gilt, und logischer Fokus bezieht sich auf das Element mit dem Fokus in einem Fokusbereich.  Diese Konzepte werden in dieser Übersicht detailliert besprochen.  Die Unterschiede zwischen diesen Konzepten zu kennen ist wichtig, wenn Sie komplexe Anwendungen mit mehreren Bereichen, auf die der Fokus gelegt werden kann, erstellen möchten.  
  
 Die hauptsächlich an der Fokusverwaltung beteiligten Klassen sind die <xref:System.Windows.Input.Keyboard>\-Klasse, die <xref:System.Windows.Input.FocusManager>\-Klasse und die Basiselementklassen wie <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement>.  Weitere Informationen zu den Basiselementen finden Sie unter [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  
  
 Die <xref:System.Windows.Input.Keyboard>\-Klasse gilt vornehmlich dem Tastaturfokus und die <xref:System.Windows.Input.FocusManager>\-Klasse dem logischen Fokus, dies ist jedoch keine absolute Unterscheidung.  Ein Element mit Tastaturfokus verfügt auch über den logischen Fokus, ein Element mit logischem Fokus weist jedoch nicht unbedingt auch den Tastaturfokus auf.  Dies wird deutlich, wenn Sie mit der <xref:System.Windows.Input.Keyboard>\-Klasse das Element mit dem Tastaturfokus festlegen, da das Element hierdurch auch den logischen Fokus erhält.  
  
   
  
<a name="Keyboard_Focus"></a>   
## Tastaturfokus  
 Tastaturfokus bezieht sich auf das Element, dem die derzeitige Tastatureingabe gilt.  Auf dem gesamten Desktop kann es nur ein Element mit Tastaturfokus geben.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] weist <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> für das Element, das den Tastaturfokus besitzt, den Wert `true` auf.  Die statische <xref:System.Windows.Input.Keyboard.FocusedElement%2A>\-Eigenschaft in der <xref:System.Windows.Input.Keyboard>\-Klasse ruft das Element ab, auf dem gerade der Tastaturfokus liegt.  
  
 Damit ein Element den Tastaturfokus erhalten kann, müssen die <xref:System.Windows.UIElement.Focusable%2A>\-Eigenschaft und die <xref:System.Windows.UIElement.IsVisible%2A>\-Eigenschaft in den Basiselementen auf `true` festgelegt sein.  Bei einigen Klassen wie der <xref:System.Windows.Controls.Panel>\-Basisklasse ist <xref:System.Windows.UIElement.Focusable%2A> standardmäßig auf `false` festgelegt. Daher müssen Sie <xref:System.Windows.UIElement.Focusable%2A> auf `true` festlegen, wenn diese Elemente in der Lage sein sollen, den Tastaturfokus zu erhalten.  
  
 Der Tastaturfokus kann durch eine Interaktion des Benutzers mit der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] auf ein Element gelegt werden, zum Beispiel, wenn der Benutzer mit der TAB\-TASTE zu einem Element springt oder mit der Maustaste darauf klickt.  Der Tastaturfokus kann auch programmgesteuert über die <xref:System.Windows.Input.Keyboard.Focus%2A>\-Methode in der <xref:System.Windows.Input.Keyboard>\-Klasse bezogen werden.  Die <xref:System.Windows.Input.Keyboard.Focus%2A>\-Methode versucht, den Tastaturfokus auf das angegebene Element zu legen.  Das zurückgegebene Element ist das Element mit dem Tastaturfokus. Dies kann ein anderes als das gewünschte Element sein, falls das alte oder das neue Fokusobjekt die Anforderung blockiert.  
  
 Im folgenden Beispiel wird mit der <xref:System.Windows.Input.Keyboard.Focus%2A>\-Methode der Tastaturfokus auf einen <xref:System.Windows.Controls.Button> gelegt.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Die <xref:System.Windows.UIElement.IsKeyboardFocused%2A>\-Eigenschaft in den Basiselementklassen ruft einen Wert ab, der anzeigt, ob der Tastaturfokus auf dem Element liegt.  Die <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>\-Eigenschaft in den Basiselementklassen ruft einen Wert ab, der anzeigt, ob der Tastaturfokus auf dem Element oder einem seiner sichtbaren untergeordneten Elemente liegt.  
  
 Das Element, das beim Start der Anwendung zuerst den Fokus erhalten soll, muss sich in der visuellen Struktur des ersten von der Anwendung geladenen Fensters befinden, und für das Element müssen <xref:System.Windows.UIElement.Focusable%2A> und <xref:System.Windows.UIElement.IsVisible%2A> auf `true` festgelegt sein.  Am besten platzieren Sie den Anfangsfokus im <xref:System.Windows.FrameworkElement.Loaded>\-Ereignishandler.  Sie können auch einen <xref:System.Windows.Threading.Dispatcher>\-Rückruf verwenden, indem Sie <xref:System.Windows.Threading.Dispatcher.Invoke%2A> oder <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> aufrufen.  
  
<a name="Logical_Focus"></a>   
## Logischer Fokus  
 Der logische Fokus bezieht sich auf das <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=fullName> in einem Fokusbereich.  Bei einem Fokusbereich handelt es sich um ein Element, das das <xref:System.Windows.Input.FocusManager.FocusedElement%2A> innerhalb seines Bereichs verfolgt.  Wenn der Tastaturfokus einen Fokusbereich verlässt, verliert das fokussierte Element den Tastaturfokus, behält jedoch den logischen Fokus.  Wenn der Tastaturfokus in den Fokusbereich zurückkehrt, erhält das fokussierte Element wieder den Tastaturfokus.  Auf diese Weise kann der Tastaturfokus zwischen verschiedenen Fokusbereichen wechseln, wobei sichergestellt ist, dass das fokussierte Element im Fokusbereich den Tastaturfokus wieder erhält, wenn dieser in diesen Fokusbereich zurückkehrt.  
  
 In einer Anwendung kann der logische Fokus auf mehreren Elementen liegen, innerhalb eines bestimmten Fokusbereichs kann jedoch immer nur ein Element den logischen Fokus haben.  
  
 Das Element mit dem Tastaturfokus besitzt auch den logischen Fokus innerhalb seines Fokusbereichs.  
  
 Sie können ein Element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zu einem Fokusbereich machen, indem Sie die angefügte <xref:System.Windows.Input.FocusManager>\-Eigenschaft <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> auf `true` festlegen.  Über Code kann ein Element durch einen Aufruf von <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> in einen Fokusbereich umgewandelt werden.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.StackPanel> in einen Fokusbereich umgewandelt, indem die angefügte <xref:System.Windows.Input.FocusManager.IsFocusScope%2A>\-Eigenschaft festgelegt wird.  
  
 [!code-xml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A> gibt den Fokusbereich für das angegebene Element zurück.  
  
 Folgende Klassen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind standardmäßig Fokusbereiche: <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar> und <xref:System.Windows.Controls.ContextMenu>  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> ruft das fokussierte Element für den angegebenen Fokusbereich ab.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> legt das Element mit Fokus im angegebenen Fokusbereich fest.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> wird in der Regel verwendet, um das Element mit dem Anfangsfokus festzulegen.  
  
 Im folgenden Beispiel wird das fokussierte Element für einen Fokusbereich festgelegt und das Element mit dem Fokus in einem Fokusbereich abgerufen.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## Tastaturnavigation  
 Die <xref:System.Windows.Input.KeyboardNavigation>\-Klasse ist dafür verantwortlich, die Standardnavigation für den Tastaturfokus zu implementieren, wenn eine der Navigationstasten gedrückt wird.  Die Navigationstasten sind: TAB, UMSCHALT\+TAB, STRG\+TAB, STRG\+UMSCHALT\+TAB, NACH\-OBEN\-TASTE, NACH\-UNTEN\-TASTE, NACH\-LINKS\-TASTE und NACH\-RECHTS\-TASTE.  
  
 Das Navigationsverhalten eines Navigationscontainers kann geändert werden, indem Sie die angefügten <xref:System.Windows.Input.KeyboardNavigation>\-Eigenschaften <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A> und <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A> festlegen.  Diese Eigenschaften haben den Typ <xref:System.Windows.Input.KeyboardNavigationMode>. Mögliche Werte sind: <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode> und <xref:System.Windows.Input.KeyboardNavigationMode>.  Der Standardwert ist <xref:System.Windows.Input.KeyboardNavigationMode>. Dies bedeutet, dass das Element kein Navigationscontainer ist.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.Menu> mit verschiedenen <xref:System.Windows.Controls.MenuItem>\-Objekten erstellt.  Die angefügte <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>\-Eigenschaft wird für <xref:System.Windows.Controls.Menu> auf <xref:System.Windows.Input.KeyboardNavigationMode> festgelegt.  Eine Fokusänderung über die TAB\-TASTE im <xref:System.Windows.Controls.Menu> führt in diesem Fall dazu, dass der Fokus vom jeweiligen Element auf das nächste verschoben wird. Wenn das letzte Element erreicht wurde, kehrt der Fokus zum ersten Element zurück.  
  
 [!code-xml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## Programmgesteuerte Fokusnavigation  
 Bei der Arbeit mit dem Fokus stehen folgende zusätzliche [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] zur Verfügung: <xref:System.Windows.UIElement.MoveFocus%2A> und <xref:System.Windows.UIElement.PredictFocus%2A>  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A> legt den Fokus auf das nächste Element in der Anwendung.  <xref:System.Windows.Input.TraversalRequest> wird zur Angabe der Richtung verwendet.  Die an <xref:System.Windows.UIElement.MoveFocus%2A> übergebene <xref:System.Windows.Input.FocusNavigationDirection> gibt die verschiedenen Richtungen für die Fokusverschiebung an, zum Beispiel <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection> und <xref:System.Windows.Input.FocusNavigationDirection>.  
  
 Im folgenden Beispiel wird das fokussierte Element mit <xref:System.Windows.FrameworkElement.MoveFocus%2A> gewechselt.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A> gibt das Objekt zurück, das den Fokus bei einem Fokuswechsel erhalten würde.  Derzeit werden nur <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection> und <xref:System.Windows.Input.FocusNavigationDirection> von <xref:System.Windows.FrameworkElement.PredictFocus%2A> unterstützt.  
  
<a name="Focus_Events"></a>   
## Fokusereignisse  
 Die Ereignisse für den Tastaturfokus sind <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> sowie <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus> und <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.  Diese Ereignisse sind als angefügte Ereignisse in der <xref:System.Windows.Input.Keyboard>\-Klasse definiert, sie sind jedoch in Form von entsprechenden Routingereignissen in den Basisklassenelementen leichter verfügbar.  Weitere Informationen zu Ereignissen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> wird ausgelöst, wenn das Element den Tastaturfokus erhält.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> wird ausgelöst, wenn das Element den Tastaturfokus verliert.  Wenn das <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>\-Ereignis oder das <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent>\-Ereignis behandelt wird und <xref:System.Windows.RoutedEventArgs.Handled%2A> auf `true` festgelegt ist, ändert sich der Fokus nicht.  
  
 Im folgenden Beispiel werden ein <xref:System.Windows.UIElement.GotKeyboardFocus>\-Ereignishandler und ein <xref:System.Windows.UIElement.LostKeyboardFocus>\-Ereignishandler an eine <xref:System.Windows.Controls.TextBox> angefügt.  
  
 [!code-xml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Wenn die <xref:System.Windows.Controls.TextBox> den Tastaturfokus erhält, wird die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft der <xref:System.Windows.Controls.TextBox> auf <xref:System.Windows.Media.Brushes.LightBlue%2A> festgelegt.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Wenn die <xref:System.Windows.Controls.TextBox> den Tastaturfokus verliert, wird die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft der <xref:System.Windows.Controls.TextBox> wieder auf Weiß festgelegt.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Die Ereignisse für den logischen Fokus sind: <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus>.  Diese Ereignisse sind im <xref:System.Windows.Input.FocusManager> als angefügte Ereignisse definiert, der <xref:System.Windows.Input.FocusManager> macht jedoch keine CLR\-Ereigniswrapper verfügbar.  <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> stellen diese Ereignisse auf komfortablere Weise bereit.  
  
## Siehe auch  
 <xref:System.Windows.Input.FocusManager>   
 <xref:System.Windows.UIElement>   
 <xref:System.Windows.ContentElement>   
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md)