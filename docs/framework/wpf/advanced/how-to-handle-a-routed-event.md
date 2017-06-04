---
title: "Gewusst wie: Behandeln eines Routingereignisses | Microsoft Docs"
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
  - "Bubbling von Ereignissen"
  - "Routingereignisse, Behandlung"
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Gewusst wie: Behandeln eines Routingereignisses
Dieses Beispiel zeigt die Funktionsweise von [Bubbling](GTMT)\-Ereignissen und das Schreiben eines Handlers, der die Daten des [Routingereignisses](GTMT) verarbeiten kann.  
  
## Beispiel  
 In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden Elemente in einer [Elementstruktur](GTMT) angeordnet.  Das übergeordnete Element kann sich an der Behandlung von Ereignissen beteiligen, die ursprünglich von untergeordneten Elementen in der Elementstruktur ausgelöst wurden.  Dies ist aufgrund des [Ereignisroutings](GTMT) möglich.  
  
 Routingereignisse verfolgen normalerweise eine der folgenden Routingstrategien: [Bubbling](GTMT) oder [Tunneling](GTMT).  In diesem Beispiel wird das [Bubbling](GTMT)\-Ereignis und das <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=fullName>\-Ereignis verwendet, um das Routing zu verdeutlichen.  
  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Controls.Button>\-Steuerelemente erstellt, und die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Attributsyntax wird verwendet, um einen Ereignishandler an ein gemeinsames übergeordnetes Element anzufügen \(in diesem Beispiel <xref:System.Windows.Controls.StackPanel>\).  Anstatt einzelne Ereignishandler für jedes untergeordnete <xref:System.Windows.Controls.Button>\-Element anzufügen, wird im Beispiel die Attributsyntax verwendet, um den Ereignishandler dem übergeordneten <xref:System.Windows.Controls.StackPanel>\-Element hinzuzufügen.  Dieses Ereignisbehandlungsmuster zeigt, wie Sie das Ereignisrouting als Verfahren zum Reduzieren der Anzahl an Elementen verwenden, an die ein Handler angefügt wurde.  Alle [Bubbling](GTMT)\-Ereignisse für die einzelnen <xref:System.Windows.Controls.Button>\-Elemente werden über das übergeordnete Element geroutet.  
  
 Beachten Sie, dass für das übergeordnete <xref:System.Windows.Controls.StackPanel>\-Element der als Attribut angegebene <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignisname teilweise qualifiziert wird, indem die <xref:System.Windows.Controls.Button>\-Klasse benannt wird.  Die <xref:System.Windows.Controls.Button>\-Klasse ist eine von <xref:System.Windows.Controls.Primitives.ButtonBase> abgeleitete Klasse, deren Memberauflistung über das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis verfügt.  Dieses Teilqualifikationsverfahren zum Anfügen eines Ereignishandlers ist erforderlich, wenn das behandelte Ereignis in der Memberauflistung des Elements nicht vorhanden ist, an das der Routingereignishandler angefügt ist.  
  
 [!code-xml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 Im folgenden Beispiel wird das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis behandelt.  Das Beispiel zeigt, welches Element das Ereignis behandelt und welches Element das Ereignis auslöst.  Der Ereignishandler wird ausgeführt, wenn der Benutzer auf eine Schaltfläche klickt.  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## Siehe auch  
 <xref:System.Windows.RoutedEvent>   
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)   
 [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)