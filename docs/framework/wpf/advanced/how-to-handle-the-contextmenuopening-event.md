---
title: 'Gewusst wie: Behandeln des ContextMenuOpening -Ereignisses'
ms.date: 03/30/2017
helpviewer_keywords:
- ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
ms.openlocfilehash: ab4c4867981cd318738b7404d76f2f5932bb9059
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547484"
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>Gewusst wie: Behandeln des ContextMenuOpening -Ereignisses
Die <xref:System.Windows.FrameworkElement.ContextMenuOpening> -Ereignis behandelt werden, in einer Anwendung anpassen entweder ein vorhandenes Kontextmenü vor um anzuzeigen, oder klicken Sie im Menü zu unterdrücken, die andernfalls durch die Einstellung angezeigt werden soll die <xref:System.Windows.RoutedEventArgs.Handled%2A> Eigenschaft `true` in den Ereignisdaten. Die häufiger Grund für die Einstellung <xref:System.Windows.RoutedEventArgs.Handled%2A> auf `true` im Ereignis Daten sind, klicken Sie im Menü vollständig durch ein neues ersetzt <xref:System.Windows.Controls.ContextMenu> -Objekt, der in einigen Fällen erfordert der Vorgang abgebrochen wird, und starten eine neue geöffnet. Wenn Sie Handler schreiben der <xref:System.Windows.FrameworkElement.ContextMenuOpening> Ereignis, Sie sollten Probleme mit den Zeitabläufen zwischen beachtet werden ein <xref:System.Windows.Controls.ContextMenu> -Steuerelement und dem Dienst, der für das Öffnen und die Position des Kontextmenüs für Steuerelemente im Allgemeinen zuständig ist. Dieses Thema veranschaulicht einige der Methoden Code für verschiedene Szenarien des Öffnens Kontextmenü und veranschaulicht einen Fall, in dem das Problem der zeitlichen Steuerung eine sprachbasierte stammen.  
  
 Es gibt mehrere Szenarien für die Behandlung der <xref:System.Windows.FrameworkElement.ContextMenuOpening> Ereignis:  
  
-   Anpassen der Menüelemente vor der Anzeige.  
  
-   Ersetzen das gesamte Menü vor der Anzeige.  
  
-   Vollständig unterdrücken vorhandene Kontextmenü, und kein Kontextmenü angezeigt.  
  
## <a name="example"></a>Beispiel  
  
## <a name="adjusting-the-menu-items-before-display"></a>Anpassen der Menüelemente vor der Anzeige  
 Anpassen der vorhandenen Menüelemente ist recht einfach gehalten und ist wahrscheinlich das häufigste Szenario. Sie können dies zum addieren oder subtrahieren als Antwort auf die aktuelle Statusinformationen in der Anwendung oder bestimmte Statusinformationen, die als Eigenschaft für das Objekt verfügbar ist, in dem im Kontextmenü den Befehl angefordert wird (Kontextmenüoptionen) vornehmen.  
  
 Das allgemeine Verfahren ist, um die Quelle des Ereignisses, das das Steuerelement bestimmte, geklickt wurde, und erhalten die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft daraus. In der Regel überprüfen möchten die <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung finden Sie unter welche Kontextmenüelemente bereits vorhanden sind, klicken Sie im Menü, und klicken Sie dann hinzufügen oder entfernen entsprechende neue <xref:System.Windows.Controls.MenuItem> von Elementen in oder aus der Auflistung.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>Ersetzen des gesamten Menüs vor der Anzeige  
 Eine alternative Szenario ist das gesamte Kontextmenü ersetzen soll. Natürlich auch können Sie eine Variation des vorangehenden Codes entfernen Sie jedes Element der vorhandenen Kontextmenüs und neue hinzufügen, beginnend mit 0 (null)-Element. Die intuitivere Vorgehensweise zum Ersetzen aller Elemente im Kontextmenü besteht jedoch zum Erstellen eines neuen <xref:System.Windows.Controls.ContextMenu>mit Elementen zu füllen, und legen Sie dann die <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> Eigenschaft eines Steuerelements auf das neue <xref:System.Windows.Controls.ContextMenu>.  
  
 Folgender Ausdruck ist der einfache Handlercode zum Ersetzen einer <xref:System.Windows.Controls.ContextMenu>. Der Code verweist auf ein benutzerdefiniertes `BuildMenu` -Methode, die ausgelagert wird, da sie aufgerufen wird, um mehr als eins der Beispiel-Handler.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Jedoch bei Verwendung dieses Format der Handler für <xref:System.Windows.FrameworkElement.ContextMenuOpening>, Sie können möglicherweise ein Problem der zeitlichen Steuerung bereitstellen, wenn das Objekt, das Sie, in dem Festlegen die <xref:System.Windows.Controls.ContextMenu> verfügt nicht über eine bereits vorhandene Kontextmenü. Wenn ein Benutzer ein Steuerelement klickt <xref:System.Windows.FrameworkElement.ContextMenuOpening> wird ausgelöst, selbst wenn die vorhandene <xref:System.Windows.Controls.ContextMenu> ist leer oder null. Aber in diesem Fall nach Belieben neue <xref:System.Windows.Controls.ContextMenu> Sie festlegen, in der Quelle Element zu spät eintrifft, um angezeigt zu werden. Auch wenn der Benutzer auf ein zweites Mal auftritt, dieses Mal Ihr neues <xref:System.Windows.Controls.ContextMenu> angezeigt wird, der Wert ist ungleich Null, und die Handler ordnungsgemäß ersetzen und zeigt das Menü, wenn der Handler ein zweites Mal ausgeführt wird. Dadurch ergibt sich zwei mögliche problemumgehungen:  
  
1.  Sicher, dass <xref:System.Windows.FrameworkElement.ContextMenuOpening> Handler immer für Steuerelemente, die über mindestens einen Platzhalter ausführen <xref:System.Windows.Controls.ContextMenu> verfügbar, die vom Handlercode ersetzt werden sollen. In diesem Fall können Sie weiterhin den Handler, die im vorherigen Beispiel dargestellt, aber Sie in der Regel einen Platzhalter zuweisen möchten <xref:System.Windows.Controls.ContextMenu> im anfänglichen Markup:  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  Vorausgesetzt, dass der ursprüngliche <xref:System.Windows.Controls.ContextMenu> Wert kann null sein, basierend auf einer vorläufigen Logik. Sie können entweder <xref:System.Windows.Controls.ContextMenu> für Null oder ein Flag in Ihrem Code zu überprüfen, ob der Handler wurde mindestens einmal ausgeführt. Da Sie davon, die ausgehen die <xref:System.Windows.Controls.ContextMenu> geht es um werden angezeigt, den Handler und legt dann <xref:System.Windows.RoutedEventArgs.Handled%2A> auf `true` in den Ereignisdaten. Um die <xref:System.Windows.Controls.ContextMenuService> , die dient zur Anzeige der Kontext des Menüs, eine `true` Wert für <xref:System.Windows.RoutedEventArgs.Handled%2A> im Ereignis Daten stellt eine Anforderung zum Abbrechen der Anzeige für das Kontextmenü / steuern Kombination, die das Ereignis ausgelöst hat.  
  
 Nun, da Sie potenziell verdächtige Kontextmenü unterdrückt haben, ist der nächste Schritt, geben Sie eine neue zeigen Sie es. Einrichten des neuen eine im Grunde identisch mit der vorherigen Handler ist: Sie erstellen ein neues <xref:System.Windows.Controls.ContextMenu> und legen Sie die Steuerelement-Quelle <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> Eigenschaft mit dem sie. Der zusätzliche Schritt ist, müssen Sie jetzt die Anzeige des Kontextmenüs, zwingen, da Sie beim ersten Versuch unterdrückt. Um die Anzeige zu erzwingen, legen Sie die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> Eigenschaft `true` innerhalb der Handler. Vorsichtig sein, wenn Sie dies tun, da löst aus, öffnen das Kontextmenü im Handler der <xref:System.Windows.FrameworkElement.ContextMenuOpening> Ereignis erneut. Wenn Sie den Handler erneut ausführen, wird er endlos rekursiv. Daher müssen Sie immer zu suchende `null` oder ein Flag verwenden, wenn Sie ein Kontextmenü, innerhalb Öffnen einer <xref:System.Windows.FrameworkElement.ContextMenuOpening> -Ereignishandler.  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>Unterdrücken vorhandene Kontextmenü, und kein Kontextmenü angezeigt  
 Das abschließende Szenario, schreiben einen Ereignishandler, der ein Menü völlig unterdrückt ist ungewöhnlich. Wenn ein bestimmtes Steuerelement nicht wird ein Kontextmenü anzuzeigen erwartet, sind wahrscheinlich besser Möglichkeiten, dies als indem Sie im Menü unterdrücken, sondern nur, wenn ein Benutzer fordert zu gewährleisten. Wenn jedoch den Handler verwenden, um ein Kontextmenü zu unterdrücken und nichts angezeigt werden sollen, legen Sie der Handler sollten einfach <xref:System.Windows.RoutedEventArgs.Handled%2A> auf `true` in den Ereignisdaten. Die <xref:System.Windows.Controls.ContextMenuService> , die ist verantwortlich für das Anzeigen eines Kontextmenüs die Ereignisdaten des Ereignisses sucht es für das Steuerelement ausgelöst. Wenn das Ereignis markiert wurde <xref:System.Windows.RoutedEventArgs.Handled%2A> an einer beliebigen Stelle entlang der Route dann Aktion des Kontextmenüs öffnen, die das Ereignis initiiert wird unterdrückt.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>  
 [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [Übersicht über ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)
