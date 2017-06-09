---
title: "Vorschauereignisse | Microsoft Docs"
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
  - "Ereignisse, Vorschau"
  - "Ereignisse, Unterdrücken"
  - "Vorschau-Ereignisse"
  - "Unterdrücken von Ereignissen"
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Vorschauereignisse
Vorschauereignisse, auch als Tunneling\-Ereignisse bezeichnet, sind Routingereignisse, bei denen die Richtung der Route vom Anwendungsstamm zum Element verläuft, das das Ereignis ausgelöst hat und als Quelle in den Ereignisdaten genannt wird.  Nicht alle Ereignisszenarien unterstützen oder erfordern Vorschauereignisse. In diesem Thema werden die Situationen beschrieben, in denen Vorschauereignisse existieren, es wird erläutert, wie Anwendungen oder Komponenten sie behandeln sollten, und es werden Fälle genannt, in denen das Erstellen von Vorschauereignissen in benutzerdefinierten Komponenten oder Klassen angemessen sein kann.  
  
## Vorschauereignisse und Eingaben  
 Beim allgemeinen Umgang mit Vorschauereignissen sollten Sie beim Markieren von in den Ereignisdaten behandelten Ereignissen vorsichtig sein.  Wenn ein Vorschauereignis auf einem anderen Element behandelt wird als dem Element, das es ausgelöst hat \(das Element, das als Quelle in den Ereignisdaten angegeben wird\), erhält kein Element die Möglichkeit, das Ereignis zu behandeln, das es ausgelöst hat.  In einigen Fällen ist dies das gewünschte Ergebnis, insbesondere dann, wenn die betroffenen Elemente Teil von Beziehungen innerhalb der Zusammensetzung eines Steuerelements sind.  
  
 Besonders für Eingabeereignisse werden Ereignisdateninstanzen auch für Vorschauereignisse mit dem entsprechenden Bubbling\-Ereignis freigegeben.  Wenn Sie einen Vorschauereignis\-Klassenhandler zum Markieren des behandelten Eingabeereignisses verwenden, wird der Klassenhandler für das Bubbling\-Eingabeereignis nicht aufgerufen.  Oder, wenn Sie einen Vorschauereignis\-Instanzhandler zum Markieren des behandelten Eingabeereignisses verwenden, werden die Handler für das Bubbling\-Ereignis in der Regel nicht aufgerufen.  Klassen\- oder Instanzhandler können registriert werden oder es kann ihnen eine Option angefügt werden, die ausgeführt wird, auch wenn das Ereignis als behandelt markiert ist. Dieses Verfahren wird gewöhnlich jedoch nicht verwendet.  
  
 Weitere Informationen über Klassenbehandlung und darüber, wie diese mit Vorschauereignissen in Beziehung steht, finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
### Umgehen von Ereignisunterdrückung durch Steuerelemente  
 Ein Szenario, bei dem Vorschauereignisse im Allgemeinen verwendet werden, ist die zusammengesetzte Steuerelementbehandlung von Eingabeereignissen.  Gelegentlich unterdrückt der Autor des Steuerelements, dass ein bestimmtes Ereignis von diesem Steuerelement ausgelöst wird, beispielsweise um ein komponentendefiniertes Ereignis zu ersetzen, das mehr Informationen enthält oder ein spezifischeres Verhalten impliziert.  Beispielsweise unterdrückt ein [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-<xref:System.Windows.Controls.Button> <xref:System.Windows.UIElement.MouseLeftButtonDown>\-Bubbling\-Ereignisse und <xref:System.Windows.UIElement.MouseLeftButtonDown>\-Bubbling\-Ereignisse, die von dem <xref:System.Windows.Controls.Button> oder seinen zusammengesetzten Elementen ausgelöst werden, um stattdessen die Maus zu erfassen und ein <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis auszulösen, das stets von dem <xref:System.Windows.Controls.Button> selbst ausgelöst wird.  Das Ereignis und seine Daten bestehen noch auf der Route, da jedoch der <xref:System.Windows.Controls.Button> die Ereignisdaten als <xref:System.Windows.RoutedEventArgs.Handled%2A> markiert, werden nur Handler für das Ereignis ausgelöst, die spezifisch angegeben haben, dass sie im `handledEventsToo`\-Fall verwendet werden sollen.  Wenn andere Elemente im Bereich des Stamms Ihrer Anwendung noch immer versuchen, ein durch Steuerelemente unterdrücktes Ereignis zu behandeln, können Sie Handler in Code anfügen, wobei für `handledEventsToo` `true` festgelegt ist.  Oftmals ist es jedoch einfacher, die von Ihnen behandelte Routingrichtung zu ändern, sodass sie die Vorschauentsprechung eines Eingabeereignisses darstellt.  Wenn z. B. ein Steuerelement <xref:System.Windows.UIElement.MouseLeftButtonDown> unterdrückt, versuchen Sie, stattdessen einen Handler für <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> anzufügen.  Diese Technik funktioniert nur für Basiselement\-Eingabeereignisse wie <xref:System.Windows.UIElement.MouseLeftButtonDown>.  Diese Eingabeereignisse verwenden Tunnel\-\/Bubbling\-Paare, lösen beide Ereignisse aus und geben die Ereignisdaten frei.  
  
 Jede dieser Techniken hat entweder Nebeneffekte oder Einschränkungen.  Der Nebeneffekt der Behandlung des Vorschauereignisses besteht darin, dass durch das Behandeln des Ereignisses zu diesem Zeitpunkt möglicherweise Handler deaktiviert werden, die erwarten, das Bubbling\-Ereignis zu behandeln. Die Einschränkung besteht daher darin, dass es in der Regel nicht ratsam ist, das behandelte Ereignis zu markieren, während es sich noch im Vorschaubereich der Route befindet.  Die Einschränkung der `handledEventsToo`\-Technik besteht darin, dass Sie keinen `handledEventsToo`\-Handler in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als Attribut angeben können. Sie müssen den Ereignishandler in Code registrieren, nachdem Sie einen Objektverweis auf das Element abgerufen haben, an das der Handler angefügt werden soll.  
  
## Siehe auch  
 [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)