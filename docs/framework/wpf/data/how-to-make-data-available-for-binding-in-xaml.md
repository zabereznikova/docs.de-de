---
title: 'Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden'
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
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c342f0d635a9220a88a2af79c76e2c1580dee2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden
In diesem Artikel werden die verschiedenen Möglichkeiten können Sie Daten verfügbar machen für die Bindung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], abhängig von den Anforderungen Ihrer Anwendung.  
  
## <a name="example"></a>Beispiel  
 Ist eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekt aus binden möchten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], eine Möglichkeit, Sie können das Objekt verfügbar machen, für die Bindung bezieht sich auf die als Ressource zu definieren, und weisen Sie ihm eine `x:Key`. Im folgenden Beispiel haben Sie eine `Person` Objekt mit der eine Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`. Die `Person` Objekt ist im Namespace namens definiert `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 Anschließend können Sie auf das Objekt im binden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider> -Klasse, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 Sie definieren die Bindung die gleiche Weise:  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 In diesem speziellen Beispiel ist das Ergebnis identisch: Sie haben eine <xref:System.Windows.Controls.TextBlock> mit dem Textinhalt `Joe`. Allerdings die <xref:System.Windows.Data.ObjectDataProvider> -Klasse bietet eine Funktionalität, z. B. die Fähigkeit, auf das Ergebnis einer Methode zu binden. Sie können auch mithilfe der <xref:System.Windows.Data.ObjectDataProvider> Klasse, wenn Sie die Funktionalität benötigen.  
  
 Jedoch wenn Sie auf ein Objekt binden, der bereits erstellt wurde, müssen Sie legen die `DataContext` im Code, wie im folgenden Beispiel.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung unter Verwendung der <xref:System.Windows.Data.XmlDataProvider> Klasse, finden Sie unter [Binden mit XML-Daten mithilfe einer XMLDataProvider und XPath-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung unter Verwendung der <xref:System.Windows.Data.ObjectDataProvider> Klasse, finden Sie unter [binden, "XDocument" oder "XElement" mit LINQ für XML-Abfrageergebnissen](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Informationen über die verschiedenen Methoden können Sie angeben, die Daten, die Sie möchten binden, finden Sie unter [geben die Bindungsquelle](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md). Informationen zum welche Arten von Daten an Sie gebunden werden können, oder eine eigene Implementierung [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekte für die Bindung, finden Sie unter [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
