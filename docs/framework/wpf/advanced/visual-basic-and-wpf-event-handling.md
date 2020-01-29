---
title: Behandeln von Ereignissen in Visual Basic
ms.date: 03/30/2017
helpviewer_keywords:
- Visual Basic [WPF], event handlers
- event handlers [WPF], Visual Basic
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
ms.openlocfilehash: 959ef66f41f6c5f06e18a202109fba058c522d1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735408"
---
# <a name="visual-basic-and-wpf-event-handling"></a>Visual Basic- und WPF-Ereignisbehandlung
Speziell für die Microsoft Visual Basic .NET-Sprache können Sie das sprachspezifische `Handles`-Schlüsselwort verwenden, um Ereignishandler Instanzen zuzuordnen, anstatt Ereignishandler mit Attributen anzufügen oder die <xref:System.Windows.UIElement.AddHandler%2A>-Methode zu verwenden. Allerdings weist die `Handles`-Technik für das Anfügen von Handlern an Instanzen einige Einschränkungen auf, da die `Handles`-Syntax einige der spezifischen Funktionen von Routingereignissen des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignissystems nicht unterstützt.  
  
## <a name="using-handles-in-a-wpf-application"></a>Verwenden von „Handles“ in einer WPF-Anwendung  
 Die Ereignishandler, die über `Handles` mit Instanzen und Ereignissen verbunden sind, müssen alle innerhalb der partiellen Klassendefinition der Instanz definiert sein, die auch eine Anforderung für Ereignishandler darstellt, die über Attributwerte für Elemente zugewiesen werden. Sie können nur `Handles` für ein Element auf der Seite angeben, das über einen <xref:System.Windows.FrameworkContentElement.Name%2A>-Eigenschafts Wert (oder eine [x:Name-Direktive](../../../desktop-wpf/xaml-services/xname-directive.md) deklariert) verfügt. Dies liegt daran, dass der <xref:System.Windows.FrameworkContentElement.Name%2A> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] den Instanzverweis erstellt, der zur Unterstützung des instanzverweisverweisformats erforderlich ist, das von der `Handles`-Syntax benötigt wird Das einzige Element, das ohne <xref:System.Windows.FrameworkContentElement.Name%2A> Verweis für `Handles` verwendet werden kann, ist die Stamm Element Instanz, die die partielle Klasse definiert.  
  
 Sie können mehreren Elemente den gleichen Handler zuweisen, indem Sie *Instance.Event*-Verweise nach `Handles` durch Kommas trennen.  
  
 Sie können `Handles` dazu nutzen, um dem gleichen *Instance.Event*-Verweis mehr als einen Handler zuzuweisen. Bemessen Sie der Reihenfolge, in der Handler im `Handles`-Verweis gegeben werden, keine Wichtigkeit zu. Sie können davon ausgehen, dass Handler, die dasselbe Ereignis behandlen, in beliebiger Reihenfolge aufgerufen werden können.  
  
 Um einen Handler zu entfernen, der mit `Handles` in der Deklaration hinzugefügt wurde, können Sie <xref:System.Windows.UIElement.RemoveHandler%2A>abrufen.  
  
 Mithilfe von `Handles` können Sie Handler für Routingereignisse anfügen, solange Sie Handler an Instanzen anfügen, die das behandelte Ereignis in ihren Membertabellen definieren. Für Routing Ereignisse folgen Handler, die mit `Handles` verbunden sind, denselben Routing Regeln wie Handler, die als [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attribute angefügt sind, oder mit der allgemeinen Signatur von <xref:System.Windows.UIElement.AddHandler%2A>. Dies bedeutet Folgendes: Wenn das Ereignis bereits als behandelt markiert ist (die <xref:System.Windows.RoutedEventArgs.Handled%2A>-Eigenschaft in den Ereignisdaten ist `True`), werden Handler, die mit `Handles` verbunden sind, nicht als Antwort auf diese Ereignis Instanz aufgerufen. Das Ereignis kann von Instanzhandlern auf ein anderes Element in der Route oder von der Klassenbehandlung für das aktuelle Element oder frühere Elemente entlang der Route als behandelt markiert werden. Für Eingabeereignisse, die gekoppelte Tunneling-/Bubblingereignisse unterstützen, kann die Tunnelingroute das Ereignispaar als behandelt markiert haben. Weitere Informationen zu Routingereignissen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
## <a name="limitations-of-handles-for-adding-handlers"></a>Einschränkungen von „Handles“ beim Hinzufügen von Handlern  
 `Handles` kann für angefügte Ereignisse nicht auf Handler verweisen. Verwenden Sie die `add`-Accessormethode für das angefügte Ereignis oder *typename.eventname*-Ereignisattribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
 Für Routingereignisse können Sie nur `Handles` dazu verwenden, um Handler für Instanzen zuzuweisen, auf denen das Ereignis in der Instanzmembertabelle vorhanden ist. Mit Routingereignissen kann ein übergeordnetes Element aber im Allgemeinen ein Listener für ein Ereignis aus untergeordneten Elementen sein, selbst wenn dieses Ereignis nicht in der Membertabelle des übergeordneten Elements vorkommt. In der Attributsyntax können Sie dies über die *typename.membername*-Attributform angeben, die beschreibt, welcher Typ tatsächlich das zu behandlende Ereignis definiert. Beispielsweise kann eine übergeordnete `Page` (ohne `Click` Ereignis definiert) auf Schaltflächen Klick Ereignisse lauschen, indem ein Attribut Handler in der Form `Button.Click`zugewiesen wird. `Handles` unterstützt aber nicht die Form *typename.membername*, da es eine in Konflikt stehende *Instance.Event*-Form unterstützen muss. Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
 `Handles` kann keine Handler anfügen, die für Ereignisse aufgerufen werden, die bereits als behandelt markiert sind. Stattdessen müssen Sie Code verwenden und die `handledEventsToo` Überladung von <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>aufrufen.  
  
> [!NOTE]
> Verwenden Sie die `Handles`-Syntax in Visual Basic Code nicht, wenn Sie einen Ereignishandler für das gleiche Ereignis in XAML angeben. In diesem Fall wird der Ereignishandler zweimal aufgerufen.  
  
## <a name="how-wpf-implements-handles-functionality"></a>So implementiert WPF die „Handles“-Funktionalität  
 Wenn eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seite kompiliert wird, deklariert die zwischen Datei `Friend` `WithEvents` Verweise auf jedes Element auf der Seite, das einen <xref:System.Windows.FrameworkContentElement.Name%2A> Eigenschaften Satz (oder eine [x:Name-Direktive](../../../desktop-wpf/xaml-services/xname-directive.md) deklariert) aufweist. Jede benannte Instanz ist potenziell ein Element, das an einem Handler mit `Handles` zugewiesen werden kann.  
  
> [!NOTE]
> In Visual Studio kann IntelliSense Ihnen den Abschluss zeigen, für den Elemente für einen `Handles` Verweis in einer Seite verfügbar sind. Dies kann jedoch einen Kompilierungsschritt dauern, sodass die Zwischendatei alle `Friends`-Verweise auffüllen kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.UIElement.AddHandler%2A>
- [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
