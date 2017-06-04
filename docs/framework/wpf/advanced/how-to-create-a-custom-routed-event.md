---
title: "Gewusst wie: Erstellen eines benutzerdefinierten Routingereignisses | Microsoft Docs"
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
  - "Erstellen, Routingereignisse"
  - "Ereignisse, Routing"
  - "Routingereignisse, Erstellen"
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Erstellen eines benutzerdefinierten Routingereignisses
Damit Ihr benutzerdefiniertes Ereignis das [Ereignisrouting](GTMT) unterstützt, müssen Sie mithilfe der <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>\-Methode ein <xref:System.Windows.RoutedEvent> registrieren.  Dieses Beispiel zeigt die Grundlagen der Erstellung eines benutzerdefinierten Routingereignisses.  
  
## Beispiel  
 Wie im folgenden Beispiel gezeigt, registrieren Sie zuerst ein <xref:System.Windows.RoutedEvent>, indem Sie die <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>\-Methode verwenden.  Der Konvention nach muss der statische Feldname <xref:System.Windows.RoutedEvent> auf das Suffix ***Event*** enden.  In diesem Beispiel hat das Ereignis den Namen `Tap`, und die Routingstrategie für das Ereignis lautet <xref:System.Windows.RoutingStrategy>.  Nach dem Registrierungsaufruf können Sie für das Ereignis [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Ereignisaccessoren zum Hinzufügen und Entfernen angeben.  
  
 Beachten Sie, dass, obwohl das Ereignis in diesem Beispiel mithilfe der virtuellen `OnTap`\-Methode ausgelöst wird, es von Ihren jeweiligen Anforderungen abhängt, wie Sie das Ereignis auslösen und wie das Ereignis auf Änderungen reagiert.  
  
 Beachten Sie auch, dass in diesem Beispiel praktisch eine gesamte Unterklasse von <xref:System.Windows.Controls.Button> implementiert wird. Diese Unterklasse wird als separate Assembly erstellt und dann auf einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Seite als benutzerdefinierte Klasse instanziiert.  Auf diese Weise soll veranschaulicht werden, dass als Unterklassen implementierte Steuerelemente in Strukturen eingefügt werden können, die sich aus anderen Steuerelementen zusammensetzen, und dass benutzerdefinierte Ereignisse dieser Steuerelemente in diesem Fall über dieselben Ereignisroutingfunktionen wie systemeigene [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Elemente verfügen.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Tunneling\-Ereignisse werden auf dieselbe Weise erstellt, wobei <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> im Registrierungsaufruf jedoch auf <xref:System.Windows.RoutingStrategy> gesetzt ist.  Der Konvention nach werden Tunneling\-Ereignisse in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mit dem Präfix "Preview" versehen.  
  
 Ein Beispiel zur Funktionsweise von Bubbling\-Ereignissen finden Sie unter [Behandeln eines Routingereignisses](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).  
  
## Siehe auch  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md)