---
title: "Gewusst wie: Binden an XDocument, XElement oder LINQ f&#252;r XML-Abfrageergebnisse | Microsoft Docs"
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
  - "Datenbindung [WPF], Binden an XDocument"
  - "Datenbindung [WPF], Binden an XElement"
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Gewusst wie: Binden an XDocument, XElement oder LINQ f&#252;r XML-Abfrageergebnisse
In diesem Beispiel wird veranschaulicht, wie XML\-Daten mit <xref:System.Xml.Linq.XDocument> an ein <xref:System.Windows.Controls.ItemsControl> gebunden werden.  
  
## Beispiel  
 Der folgende XAML\-Code definiert ein <xref:System.Windows.Controls.ItemsControl> und schließt eine Datenvorlage für Daten vom Typ `Planet` in den XML\-Namespace `http://planetsNS` ein.  Ein XML\-Datentyp, der in einem Namespace definiert ist, muss den Namespace in geschweiften Klammern enthalten. An einer Position, an der XAML\-Markuperweiterungen auftreten können, muss dem Namespace eine Escapesequenz mit geschweiften Klammern vorangestellt werden.  Dieser Code wird an dynamische Eigenschaften gebunden, die der <xref:System.Xml.Linq.XContainer.Element%2A>\-Methode und der <xref:System.Xml.Linq.XElement.Attribute%2A>\-Methode der <xref:System.Xml.Linq.XElement>\-Klasse entsprechen.  Dynamische Eigenschaften ermöglichen die Bindung von XAML an dynamische Eigenschaften, die die Namen von Methoden gemeinsam verwenden.  Weitere Informationen dazu finden Sie unter [Dynamische Eigenschaften in LINQ to XML](../Topic/LINQ%20to%20XML%20Dynamic%20Properties.md).  Beachten Sie, dass die XML\-Standardnamespacedeklaration nicht für Attributnamen gilt.  
  
 [!code-xml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 Der folgende C\#\-Code ruft <xref:System.Xml.Linq.XDocument.Load%2A> auf und legt den StackPanel\-Datenkontext auf alle Unterelemente des Elements mit dem Namen `SolarSystemPlanets` im XML\-Namespace `http://planetsNS` fest.  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 XML\-Daten können mit <xref:System.Windows.Data.ObjectDataProvider> als XAML\-Ressource gespeichert werden.  Ein vollständiges Beispiel finden Sie unter [Quellcode in der Datei 'L2DBForm.xaml'](../Topic/L2DBForm.xaml%20Source%20Code.md).  Im folgenden Beispiel wird gezeigt, wie der Datenkontext in Code auf eine Objektressource festgelegt werden kann.  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 Die dynamischen Eigenschaften, die <xref:System.Xml.Linq.XContainer.Element%2A> und <xref:System.Xml.Linq.XElement.Attribute%2A> zugeordnet sind, stellen Flexibilität innerhalb von XAML bereit.  Der Code kann auch an die Ergebnisse einer LINQ für XML\-Abfrage gebunden werden.  In diesem Beispiel erfolgt die Bindung an die nach einem Elementwert sortierten Abfrageergebnisse.  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## Siehe auch  
 [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Übersicht über die WPF\-Datenbindung mit LINQ to XML](../Topic/WPF%20Data%20Binding%20with%20LINQ%20to%20XML%20Overview.md)   
 [Beispiel für die WPF\-Datenbindung mit LINQ to XML](../Topic/WPF%20Data%20Binding%20Using%20LINQ%20to%20XML%20Example.md)   
 [Dynamische Eigenschaften in LINQ to XML](../Topic/LINQ%20to%20XML%20Dynamic%20Properties.md)