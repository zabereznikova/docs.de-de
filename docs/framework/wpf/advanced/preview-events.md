---
title: Vorschauereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Preview events [WPF]
- suppressing events [WPF]
- events [WPF], Preview
- events [WPF], suppressing
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a258a0e145e9a24e6e87bb511fdbd6166422a656
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="preview-events"></a>Vorschauereignisse
Vorschauereignisse, auch bekannt als Tunneling-Ereignisse, sind Routingereignisse übertragen werden, in denen die Richtung der Route aus den Anwendungsstamm für das Element, das das Ereignis ausgelöst hat, und wird als Quelle in den Ereignisdaten gemeldet. Nicht alle Ereignisszenarien unterstützen oder erfordern Vorschauereignisse; Dieses Thema beschreibt die Situationen, in denen Vorschauereignisse vorhanden wie Anwendungen oder Komponenten, die sie behandeln soll, sowie die Fälle, die, in dem Vorschauereignisse in benutzerdefinierten Komponenten oder Klassen erstellen geeignet sein könnte.  
  
## <a name="preview-events-and-input"></a>Vorschauereignisse und Eingabe  
 Wenn Sie die Vorschau behandeln Ereignisse im Allgemeinen vorsichtig sein behandelt markieren die Ereignisse im Daten. Behandlung von einer Preview-Ereignis für jedes Element außer ist das Element, das ausgelöst (das Element, das als Quelle in den Ereignisdaten gemeldet wird) die Wirkung nicht und bietet ein Element die Chance, das Ereignis zu behandeln, das sie stammt. In einigen Fällen ist dies das gewünschte Ergebnis, insbesondere, wenn die betreffenden Elemente in Beziehungen innerhalb der die Zusammensetzung eines Steuerelements vorhanden sind.  
  
 Für Eingabeereignisse teilen sich insbesondere Vorschauereignisse auch Daten von Ereignisinstanzen mit den entsprechenden bubbling-Ereignis. Wenn Sie einen Preview-Klasse-Ereignishandler verwenden, um das Eingabeereignis verarbeitet zu markieren, wird die bubbling Eingabeereignis Klassenhandler nicht aufgerufen werden. Oder, wenn Sie einen Vorschau Instanz Ereignishandler verwenden, um das Ereignis als behandelt markiert, Handler für das bubbling-Ereignis werden nicht in der Regel aufgerufen werden. Klasse oder Instanzhandler können registriert oder angefügt, mit der Option, die aufgerufen werden, selbst wenn das Ereignis als behandelt markiert, aber diese Technik wird im Allgemeinen nicht verwendet werden.  
  
 Weitere Informationen zu Klassenbehandlung und wie in Bezug auf die Vorschau-Ereignissen finden Sie unter [Routingereignisse als bearbeitete sowie die Behandlung von Klasse markieren](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
### <a name="working-around-event-suppression-by-controls"></a>Umgehen der Ereignisunterdrückung von Steuerelementen  
 Ein Szenario, in dem Vorschauereignisse häufig verwendet werden, ist für zusammengesetztes Steuerelement Handhabung von Eingabeereignissen. In manchen Fällen unterdrückt der Autor des Steuerelements, ein bestimmten Ereignisses vom ursprünglichen ihre Steuerelement möglicherweise um eine Komponente definiertes Ereignis zu ersetzen, den enthält mehr Informationen oder ein spezifische Verhalten impliziert. Z. B. eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> unterdrückt <xref:System.Windows.UIElement.MouseLeftButtonDown> und <xref:System.Windows.UIElement.MouseLeftButtonDown> bubbling-Ereignisse ausgelöst werden, indem Sie die <xref:System.Windows.Controls.Button> oder seinen zusammengesetzten Elementen zugunsten die Maus erfasst und durch das Auslösen einer <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis, das immer ausgelöst wird, indem Sie die <xref:System.Windows.Controls.Button> selbst. Das Ereignis und seine Daten weiterhin entlang der Route, aber da die <xref:System.Windows.Controls.Button> markiert die Daten für das Ereignis als <xref:System.Windows.RoutedEventArgs.Handled%2A>, nur einen Handler für das Ereignis, das speziell angegeben sie einnehmen sollte der `handledEventsToo` -Fall verwendet werden.  Wenn andere Elemente für das Stammverzeichnis der Anwendung weiterhin Gelegenheit zum Behandeln eines Ereignisses Steuerelement unterdrückt, ist eine Alternative zum Ereignishandler im Code mit Anfügen `handledEventsToo` als angegebenen `true`. Jedoch ist häufig eine einfachere Möglichkeit zum Ändern der routing Richtung, die Sie behandeln, um die Vorschau-Entsprechung des ein Eingabeereignis werden. Z. B. wenn ein Steuerelement unterdrückt <xref:System.Windows.UIElement.MouseLeftButtonDown>, versuchen, einen Handler für Anfügen <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> stattdessen. Dieses Verfahren kann nur für Basiselement Eingabeereignisse wie <xref:System.Windows.UIElement.MouseLeftButtonDown>. Diese Eingabeereignisse verwenden Tunnel/Blase-Paare, beide Ereignisse auslösen und Freigeben von Daten für das Ereignis.  
  
 Jede dieser Techniken verfügt über Nebeneffekte oder Einschränkungen. Die Behandlung des Ereignisses Preview Nebeneffekt ist, dass die Behandlung des Ereignisses an diesem Punkt kann deaktiviert werden, Ereignishandler, die Sie voraussichtlich bubbling-Ereignis zu behandeln und ist daher die Einschränkung, die in der Regel keine ist eine gute Idee, markieren das Ereignis verarbeitet, während er sich weiterhin auf die Previ befindet EW-Teil der Route. Die Einschränkung für die `handledEventsToo` Technik ist, dass Sie nicht festlegen können eine `handledEventsToo` Ereignishandler in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als Attribut, müssen Sie den Ereignishandler im Code registrieren, nach dem Erhalt eines Objektverweis auf das Element ist, in dem der Handler angefügt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
