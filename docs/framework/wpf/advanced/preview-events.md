---
title: Vorschauereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- Preview events [WPF]
- suppressing events [WPF]
- events [WPF], Preview
- events [WPF], suppressing
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
ms.openlocfilehash: 95514cfce88764d92d690fb9c0a51c667a49683b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356337"
---
# <a name="preview-events"></a>Vorschauereignisse
Vorschauereignisse, auch bekannt als Tunneling-Ereignisse, sind die Routingereignisse übertragen, in denen die Richtung der Route aus den Anwendungsstamm für das Element, das das Ereignis ausgelöst hat, und wird als Quelle in den Ereignisdaten gemeldet. Nicht alle Ereignisszenarien zu unterstützen oder erfordern Vorschauereignisse; Dieses Thema beschreibt die Situationen, in denen Vorschauereignisse vorhanden wie Anwendungen oder Komponenten, die sie behandeln soll, und die Fälle, in denen Erstellen von Vorschau-Ereignissen in benutzerdefinierten Komponenten oder Klassen geeignet sein könnte.  
  
## <a name="preview-events-and-input"></a>Vorschauereignisse und Eingabe  
 Wenn Sie Preview behandeln Ereignisse im Allgemeinen vorsichtig sein, behandelt markieren die Ereignisse im Daten. Behandeln ein Vorschauereignis auf ein beliebiges Element als das Element, das ausgelöst hat (das Element, das als Quelle in den Ereignisdaten gemeldet wird) verfügt über die Auswirkungen der erhält kein Element der Möglichkeit zum Behandeln des Ereignisses, das es ausgelöst hat. Manchmal ist dies das gewünschte Ergebnis, insbesondere, wenn die betreffenden Elemente in Beziehungen innerhalb der Zusammensetzung eines Steuerelements vorhanden sind.  
  
 Für Eingabeereignisse teilen sich insbesondere Vorschauereignisse auch Ereignisinstanzen-Daten mit den entsprechenden bubbling-Ereignis. Wenn Sie einen Vorschauhandler für Event-Klasse verwenden, um das Eingabeereignis verarbeitet zu markieren, wird das Eingabeereignis bubbling-Klassenhandler nicht aufgerufen werden. Oder, wenn Sie einen Vorschau-Instanz-Ereignishandler verwenden, um das Ereignis als behandelt zu markieren, Handler für das bubbling-Ereignis werden nicht in der Regel aufgerufen werden. Klassen- oder Instanzhandler können registriert oder angefügt, mit der Option, die aufgerufen werden, selbst wenn das Ereignis als behandelt markiert, aber diese Methode normalerweise nicht verwendet wird.  
  
 Weitere Informationen zu Klassenbehandlung und wie deren Beziehung zu Vorschauereignisse finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).  
  
### <a name="working-around-event-suppression-by-controls"></a>Umgehen der Ereignisunterdrückung von Steuerelementen  
 Ein Szenario, in denen Vorschauereignisse häufig verwendet werden, ist für zusammengesetzte Steuerelement Behandlung von Eingabeereignissen. In einigen Fällen unterdrückt der Autor des Steuerelements ein bestimmtes Ereignis aus, die aus ihrer Kontrolle, z. B. um ein Ereignis zu ersetzen, die Informationen enthält, oder ein spezifischeres Verhalten impliziert stammen. Z. B. eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> unterdrückt <xref:System.Windows.UIElement.MouseLeftButtonDown> und <xref:System.Windows.UIElement.MouseRightButtonDown> bubbling-Ereignisse ausgelöst werden, indem die <xref:System.Windows.Controls.Button> oder die zusammengesetzten Elemente und die Maus erfasst und Auslösen von eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis, das immer ausgelöst wird, indem Sie die <xref:System.Windows.Controls.Button> selbst. Das Ereignis und seine Daten weiterhin entlang der Route, aber da die <xref:System.Windows.Controls.Button> markiert die Daten als <xref:System.Windows.RoutedEventArgs.Handled%2A>, nur einen Handler für das Ereignis aus, die ausdrücklich angegeben, sie fungieren soll, der `handledEventsToo` Fall aufgerufen werden.  Wenn andere Elemente für das Stammverzeichnis Ihrer Anwendung immer noch eine Möglichkeit, ein Steuerelement unterdrückt-Ereignis zu behandeln, ist eine Alternative zum Anfügen von Handlern in Code mit `handledEventsToo` als angegebenen `true`. Aber häufig ein einfacheres Verfahren zum Ändern der routing Richtung, die Sie behandeln, um die Vorschau-Darstellung ein Eingabeereignis zu werden. Z. B. wenn ein Steuerelement unterdrückt <xref:System.Windows.UIElement.MouseLeftButtonDown>, versuchen Sie es Anfügen eines Handlers für <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> stattdessen. Dieses Verfahren funktioniert nur für Eingabeereignisse Basiselement wie z. B. <xref:System.Windows.UIElement.MouseLeftButtonDown>. Diese Eingabeereignisse Tunneling/Bubbling-Eingabeereignispaare verwenden, lösen beide Ereignisse und Freigeben von Daten für das Ereignis.  
  
 Jede dieser Techniken wurde entweder Nebenwirkungen oder Einschränkungen. Den Nebeneffekt, dass der Behandlung des Ereignisses für die Vorschau ist, dass die Behandlung des Ereignisses an diesem Punkt kann deaktiviert werden, Handler, die Sie voraussichtlich die bubbling-Ereignis zu behandeln, und daher die Einschränkung besteht darin, dass es in der Regel keine gute Idee, markieren das Ereignis als behandelt zwar immer noch auf die Previ Neues Teil der Route. Die Beschränkung auf die `handledEventsToo` Technik ist, dass Sie nicht angeben einer `handledEventsToo` Ereignishandler in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als Attribut, müssen Sie den Ereignishandler im Code registrieren, nach dem erhalten eines Objektverweis auf das Element ist, in dem der Handler angefügt werden.  
  
## <a name="see-also"></a>Siehe auch
- [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
