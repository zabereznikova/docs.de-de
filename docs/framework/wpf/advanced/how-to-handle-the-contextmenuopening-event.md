---
title: 'Vorgehensweise: Behandeln des ContextMenuOpening-Ereignisses'
ms.date: 03/30/2017
helpviewer_keywords:
- ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
ms.openlocfilehash: 65a1e34d5b078c49bf59c2d9787812940c9a7494
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340398"
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>Vorgehensweise: Behandeln des ContextMenuOpening-Ereignisses
Die <xref:System.Windows.FrameworkElement.ContextMenuOpening> -Ereignis behandelt werden, in einer Anwendung anpassen, entweder ein vorhandenes Kontext vor oder im Menü zu unterdrücken, die andernfalls durch Festlegen von angezeigt werden würden die <xref:System.Windows.RoutedEventArgs.Handled%2A> Eigenschaft `true` in den Ereignisdaten. Der Hauptgrund für die Einstellung <xref:System.Windows.RoutedEventArgs.Handled%2A> zu `true` in der Daten befindet, klicken Sie im Menü vollständig durch einen neuen ersetzt <xref:System.Windows.Controls.ContextMenu> Objekt, der in einigen Fällen erfordert der Vorgang abgebrochen wird, und starten eine neue Open. Wenn Sie Handler für Schreiben der <xref:System.Windows.FrameworkElement.ContextMenuOpening> -Ereignis, sollten Sie Bedenken der Probleme mit der zeitsteuerung zwischen eine <xref:System.Windows.Controls.ContextMenu> Steuerelement und der Dienst, der für das Öffnen und die Position des Kontextmenüs für Steuerelemente in der Regel zuständig ist. In diesem Thema veranschaulicht einige der Codetechniken für verschiedene Szenarien öffnen Kontextmenü, und zeigt einen Fall, in dem das Problem der zeitlichen Steuerung ins Spiel kommt.  
  
 Es gibt mehrere Szenarios für die Behandlung der <xref:System.Windows.FrameworkElement.ContextMenuOpening> Ereignis:  
  
-   Anpassen von die Menüelemente vor der Anzeige.  
  
-   Ersetzen das gesamte Menü vor der Anzeige.  
  
-   Vollständig unterdrücken vorhandenen Kontextmenü, und kein Kontextmenü angezeigt.  
  
## <a name="example"></a>Beispiel  
  
## <a name="adjusting-the-menu-items-before-display"></a>Anpassen der Menüelemente vor der Anzeige  
 Anpassen von den vorhandenen Menüelementen ist recht einfach gehalten und ist wahrscheinlich das gängigste Szenario. Sie können hierzu um addieren oder subtrahieren Kontextmenüoptionen, die als Reaktion auf die aktuelle Zustandsinformationen in Ihrer Anwendung oder bestimmte Statusinformationen, die als Eigenschaft für das Objekt verfügbar ist, in dem das Kontextmenü angefordert wird.  
  
 Die allgemeine Vorgehensweise zum Abrufen der Quelle des Ereignisses, die das bestimmte Steuerelement geklickt wurde, und ist die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft aus. In der Regel überprüfen möchten die <xref:System.Windows.Controls.ItemsControl.Items%2A> -Auflistung, um festzustellen welche Kontextmenüelemente bereits vorhanden sind, klicken Sie im Menü, und klicken Sie dann hinzufügen oder entfernen entsprechende neue <xref:System.Windows.Controls.MenuItem> von Elementen in oder aus der Auflistung.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>Ersetzen das gesamte Menü vor der Anzeige  
 Eine alternative Szenario ist, wenn Sie das Kontextmenü für die gesamte ersetzen möchten. Sie können natürlich auch verwenden eine Variation des vorherigen Codes auf jedes Element von einem vorhandenen Kontextmenü zu entfernen und Hinzufügen von neuen Element 0 (null) ab. Aber die intuitivere Ansatz zum Ersetzen aller Elemente im Kontextmenü zum Erstellen eines neuen <xref:System.Windows.Controls.ContextMenu>mit Elementen zu füllen, und legen Sie dann die <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> Eigenschaft eines Steuerelements auf das neue <xref:System.Windows.Controls.ContextMenu>.  
  
 Im folgenden ist der einfache Handler-Code zum Ersetzen einer <xref:System.Windows.Controls.ContextMenu>. Der Code verweist auf eine benutzerdefinierte `BuildMenu` -Methode, die getrennt ist, da sie aufgerufen wird von mehr als einer der Beispiel-Handler.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Allerdings bei Verwendung von diese Art der Handler für <xref:System.Windows.FrameworkElement.ContextMenuOpening>, Sie können möglicherweise ein Problem der zeitlichen Steuerung bereitstellen, wenn das Objekt, das Sie, in dem Festlegen die <xref:System.Windows.Controls.ContextMenu> verfügt nicht über einen bereits vorhandenen Kontextmenü. Wenn ein Benutzer ein Steuerelement, mit der rechten Maustaste <xref:System.Windows.FrameworkElement.ContextMenuOpening> wird ausgelöst, selbst wenn die vorhandene <xref:System.Windows.Controls.ContextMenu> ist leer oder null. Aber in diesem Fall alle neuen <xref:System.Windows.Controls.ContextMenu> Sie festlegen, auf dem Quellcomputer Element zu spät empfangen, um angezeigt zu werden. Auch wenn der Benutzer wird der rechten Maustaste ein zweites Mal auf dieses Mal die neue <xref:System.Windows.Controls.ContextMenu> angezeigt wird, der Wert nicht Null ist, und Ihre Handler ordnungsgemäß ersetzen und klicken Sie im Menü angezeigt, wenn der Handler für ein zweites Mal ausgeführt wird. Dies deutet darauf hin, zwei mögliche problemumgehungen:  
  
1. Stellen Sie sicher, die <xref:System.Windows.FrameworkElement.ContextMenuOpening> Handler, die immer für Steuerelemente, die über mindestens einen Platzhalter ausführen <xref:System.Windows.Controls.ContextMenu> verfügbar ist, die mit dem Ereignishandlercode ersetzt werden sollen. In diesem Fall können Sie trotzdem den Handler, der im vorherigen Beispiel gezeigt verwenden, aber Sie möchten in der Regel weisen Sie einen Platzhalter <xref:System.Windows.Controls.ContextMenu> im anfänglichen Markup:  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2. Vorausgesetzt, dass der ursprüngliche <xref:System.Windows.Controls.ContextMenu> Wert kann null sein, basierend auf einer vorläufigen Logik. Sie können entweder <xref:System.Windows.Controls.ContextMenu> für Null oder ein Flag in Ihrem Code zu überprüfen, ob der Handler wurde mindestens einmal ausgeführt. Da Sie davon ausgehen, dass die <xref:System.Windows.Controls.ContextMenu> geht es um werden angezeigt, den Handler an und legt dann <xref:System.Windows.RoutedEventArgs.Handled%2A> zu `true` in den Ereignisdaten. Auf der <xref:System.Windows.Controls.ContextMenuService> , die verantwortlich für die Anzeige im Menü Kontext ist eine `true` Wert für <xref:System.Windows.RoutedEventArgs.Handled%2A> in dieser Daten eine Anforderung zum Abbrechen der Anzeige für das Kontextmenü / zum Steuerelement-Kombination, die das Ereignis ausgelöst hat darstellt.  
  
 Nun, da Sie das Kontextmenü für die potenziell verdächtige unterdrückt haben, ist der nächste Schritt, geben Sie eine neue Methode, klicken Sie dann anzuzeigen. Einrichten der neuen im Grunde identisch mit der vorherigen Handler: Sie erstellen ein neues <xref:System.Windows.Controls.ContextMenu> und legen Sie die Steuerelement-Quelle <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> Eigenschaft mit. Der zusätzliche Schritt ist, dass Sie jetzt die Anzeige des Kontextmenüs, erzwingen müssen, da Sie beim ersten Versuch unterdrückt. Um die Anzeige zu erzwingen, legen Sie die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> Eigenschaft `true` im Ereignishandler. Seien Sie vorsichtig, wenn Sie dies tun, da löst aus, öffnen das Kontextmenü im Handler der <xref:System.Windows.FrameworkElement.ContextMenuOpening> Ereignis wird erneut. Wenn Sie Ihren Handler erneut eingeben, wird er endlos rekursiv. Aus diesem Grund Sie immer zu prüfen müssen, ist `null` , oder verwenden Sie ein Flag, wenn Sie ein Kontextmenü öffnen, die sich innerhalb einer <xref:System.Windows.FrameworkElement.ContextMenuOpening> -Ereignishandler.  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>Unterdrücken vorhandenen Kontextmenü, und kein Kontextmenü angezeigt  
 Das letzte Szenario, schreiben einen Handler, der ein Menü völlig unterdrückt ist ungewöhnlich. Wenn ein bestimmtes Steuerelement kein Kontextmenü angezeigt werden soll, sind wahrscheinlich besser Möglichkeiten zum gewährleisten dies durch das Menü unterdrücken, sondern nur, wenn ein Benutzer es anfordert. Aber wenn Sie den Handler So unterdrücken ein Kontextmenü, und zeigen nichts verwenden möchten, legen Sie Ihr Handler sollte einfach <xref:System.Windows.RoutedEventArgs.Handled%2A> zu `true` in den Ereignisdaten. Die <xref:System.Windows.Controls.ContextMenuService> , verantwortlich ist, für das Anzeigen eines Kontextmenüs die Ereignisdaten des Ereignisses überprüft, es auf dem Steuerelement ausgelöst. Wenn das Ereignis markiert wurde <xref:System.Windows.RoutedEventArgs.Handled%2A> an einer beliebigen Stelle entlang der Route, klicken Sie dann die Aktion des Öffnens Kontextmenüs, die das Ereignis initiiert hat unterdrückt wird.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>
- [Übersicht über Basiselemente](base-elements-overview.md)
- [Übersicht über ContextMenu](../controls/contextmenu-overview.md)
