---
title: "Visual Basic- und WPF-Ereignisbehandlung | Microsoft Docs"
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
  - "Ereignishandler, Visual Basic"
  - "Visual Basic, Ereignishandler"
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Visual Basic- und WPF-Ereignisbehandlung
Für die [!INCLUDE[TLA#tla_visualbnet](../../../../includes/tlasharptla-visualbnet-md.md)]\-Sprache können Sie das sprachspezifische `Handles`\-Schlüsselwort verwenden, um Instanzen Ereignishandler zuzuordnen, anstatt Ereignishandlern Attribute anzufügen oder die <xref:System.Windows.UIElement.AddHandler%2A>\-Methode zu verwenden.  Das `Handles`\-Verfahren für das Anfügen von Handlern an Instanzen unterliegt jedoch einigen Einschränkungen, da die `Handles`\-Syntax einige der spezifischen [Routingereignis](GTMT)\-Features des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignissystems nicht unterstützen kann.  
  
## Verwenden von "Handles" in einer WPF\-Anwendung  
 Die Ereignishandler, die über `Handles` mit Instanzen und Ereignissen verbunden sind, müssen alle innerhalb der partiellen Klassendeklaration der Instanz definiert sein. Dies gilt auch für Ereignishandler, die über Attributwerte für Elemente zugewiesen sind.  Sie können nur `Handles` für ein Element auf einer Seite angeben, das einen <xref:System.Windows.FrameworkContentElement.Name%2A>\-Eigenschaftswert hat \(oder für das [x:Name\-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md) deklariert ist\).  Das liegt daran, dass die <xref:System.Windows.FrameworkContentElement.Name%2A>\-Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] den Instanzverweis erstellt, der erforderlich ist, um das durch die `Handles`\-Syntax geforderte *Instance.Event*\-Verweisformat zu unterstützen.  Das einzige Element, das für `Handles` ohne einen <xref:System.Windows.FrameworkContentElement.Name%2A>\-Verweis verwendet werden kann, ist die Stammelementinstanz, die die partielle Klasse definiert.  
  
 Sie können mehreren Elementen den gleichen Handler zuweisen, indem Sie *Instance.Event*\-Verweise nach `Handles` durch Kommas trennen.  
  
 Sie können `Handles` verwenden, um dem gleichen *Instance.Event*\-Verweis mehrere Handler zuzuweisen.  Die Reihenfolge, in der die Handler im `Handles`\-Verweis angegeben sind, spielt keine Rolle. Sie sollten davon ausgehen, dass Handler, die dasselbe Ereignis behandeln, in beliebiger Reihenfolge aufgerufen werden können.  
  
 Um einen Handler zu entfernen, der mit `Handles` in der Deklaration hinzugefügt wurde, können Sie <xref:System.Windows.UIElement.RemoveHandler%2A> aufrufen.  
  
 Sie können `Handles` verwenden, um Handler für [Routingereignisse](GTMT) anzufügen, solange Sie Handler an Instanzen anfügen, die das zu behandelnde Ereignis in ihren Membertabellen definieren.  Für [Routingereignisse](GTMT) beachten Handler, die mit `Handles` angefügt sind, dieselben Routingregeln wie Handler, die als [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Attribute oder mit der <xref:System.Windows.UIElement.AddHandler%2A>\-Common\-Signatur angefügt werden.  Wenn das Ereignis bereits als behandelt markiert ist \(die <xref:System.Windows.RoutedEventArgs.Handled%2A>\-Eigenschaft in den Ereignisdaten ist `True`\), werden Handler, die mit `Handles` angefügt sind, nicht als Reaktion auf diese Ereignisinstanz aufgerufen.  Das Ereignis könnte durch Instanzhandler für andere Elemente auf der Route oder durch die Klassenbehandlung des aktuellen Elements oder eines früheren Elements auf der Route als behandelt markiert werden.  Bei Eingabeereignissen, die Tunneling\-Bubbling\-Ereignispaare unterstützen, kann die Tunneling\-Route das Ereignispaar als behandelt markiert haben.  Weitere Informationen zu Routingereignissen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## Einschränkungen für "Handles" beim Hinzufügen von Handlern  
 `Handles` können nicht auf Handler für [angefügte Ereignisse](GTMT) verweisen.  Für das angefügte Ereignis müssen die `add`\-Accessormethode oder *typename.eventname*\-Ereignisattribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet werden.  Ausführliche Informationen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Für [Routingereignisse](GTMT) können Sie nur `Handles` verwenden, um Handler für Instanzen zuzuweisen, wenn das Ereignis in der Instanzmembertabelle vorhanden ist.  Bei Routingereignissen im Allgemeinen kann jedoch ein übergeordnetes Element als Listener für Ereignisse aus untergeordneten Elementen fungieren, auch wenn das übergeordnete Element dieses Ereignis nicht in seiner Membertabelle hat.  In der Attributsyntax können Sie dies über eine *typename.membername*\-Attributform angeben, die festlegt, welcher Typ tatsächlich das Ereignis definiert, das Sie behandeln möchten.  So kann beispielsweise eine übergeordnete `Page` \(für die kein `Click`\-Ereignis definiert ist\) Klickereignisse der Schaltflächen überwachen, indem ein Attributhandler in der `Button.Click`\-Form zugewiesen wird.  `Handles` unterstützt jedoch die *typename.membername*\-Form nicht, da es eine *Instance.Event*\-Form unterstützen muss, das im Konflikt dazu steht.  Ausführliche Informationen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 `Handles` können keine Handler anfügen, die für Ereignisse aufgerufen werden, die bereits als behandelt gekennzeichnet sind.  Stattdessen müssen Sie Code verwenden und die `handledEventsToo`\-Überladung von <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> aufrufen.  
  
> [!NOTE]
>  Verwenden Sie die `Handles`\-Syntax nicht im [!INCLUDE[vb_current_short](../../../../includes/vb-current-short-md.md)]\-Code, wenn Sie einen Ereignishandler für das gleiche Ereignis in XAML angeben.  In diesem Fall wird der Ereignishandler zweimal  aufgerufen.  
  
## Implementieren der "Handles"\-Funktionalität in WPF  
 Wenn eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Seite kompiliert wird, deklariert die Zwischendatei `Friend` `WithEvents`\-Verweise für jedes Element einer Seite, für das eine <xref:System.Windows.FrameworkContentElement.Name%2A>\-Eigenschaft festgelegt wurde \(oder für das [x:Name\-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md) deklariert wurde\).  Jede benannte Instanz ist potenziell ein Element, das über `Handles` einem Handler zugewiesen werden kann.  
  
> [!NOTE]
>  Innerhalb von [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] kann [!INCLUDE[TLA2#tla_intellisense](../../../../includes/tla2sharptla-intellisense-md.md)] den Abschluss für die Elemente zeigen, die für einen `Handles`\-Verweis in einer Seite verfügbar sind.  Dies kann jedoch einen Kompilierungsschritt in Anspruch nehmen, da die Zwischendatei alle `Friends`\-Verweise ausfüllen muss.  
  
## Siehe auch  
 <xref:System.Windows.UIElement.AddHandler%2A>   
 [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)