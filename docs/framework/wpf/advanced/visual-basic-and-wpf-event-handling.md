---
title: Visual Basic- und WPF-Ereignisbehandlung
ms.date: 03/30/2017
helpviewer_keywords:
- Visual Basic [WPF], event handlers
- event handlers [WPF], Visual Basic
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
ms.openlocfilehash: 8b4601ea4034068ccdb4bfe0744f658586d74ece
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582227"
---
# <a name="visual-basic-and-wpf-event-handling"></a>Visual Basic- und WPF-Ereignisbehandlung
Für die Sprache von Microsoft Visual Basic .NET gesagt können Sie die sprachspezifischen `Handles` Instanzen, anstatt Ereignishandlern Attribute anzufügen oder mithilfe von Ereignishandlern zuzuordnende Schlüsselwort der <xref:System.Windows.UIElement.AddHandler%2A> Methode. Allerdings weist die `Handles`-Technik für das Anfügen von Handlern an Instanzen einige Einschränkungen auf, da die `Handles`-Syntax einige der spezifischen Funktionen von Routingereignissen des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignissystems nicht unterstützt.  
  
## <a name="using-handles-in-a-wpf-application"></a>Verwenden von „Handles“ in einer WPF-Anwendung  
 Die Ereignishandler, die über `Handles` mit Instanzen und Ereignissen verbunden sind, müssen alle innerhalb der partiellen Klassendefinition der Instanz definiert sein, die auch eine Anforderung für Ereignishandler darstellt, die über Attributwerte für Elemente zugewiesen werden. Sie können nur angeben `Handles` für ein Element auf der Seite, die eine <xref:System.Windows.FrameworkContentElement.Name%2A> -Eigenschaftswert (oder [X: Name Directive](../../../../docs/framework/xaml-services/x-name-directive.md) deklariert). Grund hierfür ist die <xref:System.Windows.FrameworkContentElement.Name%2A> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] den Instanzverweis erstellt, die erforderlich ist, unterstützt die *Instance.Event* erforderlich die `Handles` Syntax. Das einzige Element, das für verwendet werden kann `Handles` ohne eine <xref:System.Windows.FrameworkContentElement.Name%2A> Verweis ist die Stammelementinstanz, die die partielle Klasse definiert.  
  
 Sie können mehreren Elemente den gleichen Handler zuweisen, indem Sie *Instance.Event*-Verweise nach `Handles` durch Kommas trennen.  
  
 Sie können `Handles` dazu nutzen, um dem gleichen *Instance.Event*-Verweis mehr als einen Handler zuzuweisen. Bemessen Sie der Reihenfolge, in der Handler im `Handles`-Verweis gegeben werden, keine Wichtigkeit zu. Sie können davon ausgehen, dass Handler, die dasselbe Ereignis behandlen, in beliebiger Reihenfolge aufgerufen werden können.  
  
 Um einen Ereignishandler zu entfernen, die mit hinzugefügten `Handles` in der Deklaration können Sie aufrufen <xref:System.Windows.UIElement.RemoveHandler%2A>.  
  
 Mithilfe von `Handles` können Sie Handler für Routingereignisse anfügen, solange Sie Handler an Instanzen anfügen, die das behandelte Ereignis in ihren Membertabellen definieren. Für Routingereignisse mit angefügte Ereignishandler `Handles` befolgen Sie dieselben Routingregeln wie Handler, die als angefügt sind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attribute oder mit der gemeinsamen Signatur <xref:System.Windows.UIElement.AddHandler%2A>. Dies bedeutet, dass das Ereignis bereits als behandelt markiert ist (die <xref:System.Windows.RoutedEventArgs.Handled%2A> -Eigenschaft in den Ereignisdaten ist `True`), und klicken Sie dann mit der Handler angefügt `Handles` nicht als Antwort auf diese Ereignisinstanz aufgerufen werden. Das Ereignis kann von Instanzhandlern auf ein anderes Element in der Route oder von der Klassenbehandlung für das aktuelle Element oder frühere Elemente entlang der Route als behandelt markiert werden. Für Eingabeereignisse, die gekoppelte Tunneling-/Bubblingereignisse unterstützen, kann die Tunnelingroute das Ereignispaar als behandelt markiert haben. Weitere Informationen zu Routingereignissen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="limitations-of-handles-for-adding-handlers"></a>Einschränkungen von „Handles“ beim Hinzufügen von Handlern  
 `Handles` kann für angefügte Ereignisse nicht auf Handler verweisen. Verwenden Sie die `add`-Accessormethode für das angefügte Ereignis oder *typename.eventname*-Ereignisattribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Für Routingereignisse können Sie nur `Handles` dazu verwenden, um Handler für Instanzen zuzuweisen, auf denen das Ereignis in der Instanzmembertabelle vorhanden ist. Mit Routingereignissen kann ein übergeordnetes Element aber im Allgemeinen ein Listener für ein Ereignis aus untergeordneten Elementen sein, selbst wenn dieses Ereignis nicht in der Membertabelle des übergeordneten Elements vorkommt. In der Attributsyntax können Sie dies über die *typename.membername*-Attributform angeben, die beschreibt, welcher Typ tatsächlich das zu behandlende Ereignis definiert. Z. B. ein übergeordnetes Element `Page` (ohne `Click` definiertes Ereignis) Klickereignisse überwachen können, indem ein Attributhandler in Form zuweisen `Button.Click`. `Handles` unterstützt aber nicht die Form *typename.membername*, da es eine in Konflikt stehende *Instance.Event*-Form unterstützen muss. Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 `Handles` kann keine Handler anfügen, die für Ereignisse aufgerufen werden, die bereits als behandelt markiert sind. Sie müssen stattdessen Code, und rufen die `handledEventsToo` Überladung der <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>.  
  
> [!NOTE]
>  Verwenden Sie nicht die `Handles` -Syntax in Visual Basic-Code, wenn Sie einen Ereignishandler für das gleiche Ereignis in XAML angeben. In diesem Fall wird der Ereignishandler zweimal aufgerufen.  
  
## <a name="how-wpf-implements-handles-functionality"></a>So implementiert WPF die „Handles“-Funktionalität  
 Wenn eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Seite kompiliert wurde, deklariert die Zwischendatei `Friend` `WithEvents` -Verweise auf jedes Element auf der Seite, die eine <xref:System.Windows.FrameworkContentElement.Name%2A> Eigenschaftensatz (oder [X: Name Directive](../../../../docs/framework/xaml-services/x-name-directive.md) deklariert). Jede benannte Instanz ist potenziell ein Element, das an einem Handler mit `Handles` zugewiesen werden kann.  
  
> [!NOTE]
>  In [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] kann [!INCLUDE[TLA2#tla_intellisense](../../../../includes/tla2sharptla-intellisense-md.md)] Ihnen eine Auto-Vervollständigung für alle Elemente anbieten, die für einen `Handles`-Verweis verfügbar sind. Dies kann jedoch einen Kompilierungsschritt dauern, sodass die Zwischendatei alle `Friends`-Verweise auffüllen kann.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.UIElement.AddHandler%2A>
- [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)
- [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
