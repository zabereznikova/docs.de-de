---
title: "Gewusst wie: Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b39c45a7c85155a0fb46e8e176da5979e52e6e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>Gewusst wie: Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse
Dieses Beispiel veranschaulicht das Binden von XML-Daten in eine <xref:System.Windows.Controls.ItemsControl> mit <xref:System.Xml.Linq.XDocument>.  
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code definiert eine <xref:System.Windows.Controls.ItemsControl> und enthält eine Datenvorlage für Daten vom Typ `Planet` in der `http://planetsNS` XML-Namespace. Ein XML-Datentyp, der in einem Namespace definiert ist, muss den Namespace in geschweiften Klammern enthalten. An einer Position, an der XAML-Markuperweiterungen auftreten können, muss dem Namespace eine Escapesequenz mit geschweiften Klammern vorangestellt werden. Dieser Code bindet an dynamische Eigenschaften entsprechen den <xref:System.Xml.Linq.XContainer.Element%2A> und <xref:System.Xml.Linq.XElement.Attribute%2A> Methoden die <xref:System.Xml.Linq.XElement> Klasse. Dynamische Eigenschaften ermöglichen die Bindung von XAML an dynamische Eigenschaften, die die Namen von Methoden gemeinsam verwenden. Weitere Informationen dazu finden Sie unter [Dynamische Eigenschaften in LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties). Beachten Sie, dass die XML-Standardnamespacedeklaration nicht für Attributnamen gilt.  
  
 [!code-xaml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 Die folgende C#-Code ruft <xref:System.Xml.Linq.XDocument.Load%2A> und legt den StackPanel-Datenkontext auf alle untergeordneten Elemente des Elements mit dem Namen `SolarSystemPlanets` in der `http://planetsNS` XML-Namespace.  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 XML-Daten gespeichert werden können, als eine XAML-Ressource mit <xref:System.Windows.Data.ObjectDataProvider>. Ein vollständiges Beispiel finden Sie unter [Quellcode in der Datei ‚L2DBForm.xaml‘](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e). Im folgenden Beispiel wird gezeigt, wie der Datenkontext in Code auf eine Objektressource festgelegt werden kann.  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 Die dynamischen Eigenschaften, die zugeordnet <xref:System.Xml.Linq.XContainer.Element%2A> und <xref:System.Xml.Linq.XElement.Attribute%2A> bieten Flexibilität innerhalb von XAML. Der Code kann auch an die Ergebnisse einer LINQ to XML-Abfrage gebunden werden. In diesem Beispiel erfolgt die Bindung an die nach einem Elementwert sortierten Abfrageergebnisse.  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Übersicht über WPF-Datenbindung mit LINQ to XML](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)  
 [Beispiel für die WPF-Datenbindung mit LINQ to XML](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)  
 [Dynamische Eigenschaften in LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties)
