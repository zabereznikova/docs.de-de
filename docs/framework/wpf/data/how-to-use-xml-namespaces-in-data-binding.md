---
title: 'Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f98d174fd0bd8ea28c7b72cec25b5b16f2b76c51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie in der [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Bindungsquelle angegebene Namespaces behandelt werden.  
  
 Wenn Ihre [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten die folgende [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace-Definition haben:  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 Können Sie die <xref:System.Windows.Data.XmlNamespaceMapping> Element zuordnen den Namespace, der eine <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, wie im folgenden Beispiel. Anschließend können Sie die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> zum Verweisen auf die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace. Die <xref:System.Windows.Controls.ListBox> in diesem Beispiel zeigt die *Titel* und *DC: Date* jedes *Element*.  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 Beachten Sie, dass die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> Sie angeben, müssen nicht übereinstimmen verwendet der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle; Wenn das Präfix in geändert wird. die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle, die die Zuordnung weiterhin funktioniert.  
  
 In diesem speziellen Beispiel der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten stammen aus einem Webdienst, aber die <xref:System.Windows.Data.XmlNamespaceMapping> Element funktioniert auch mit Inline- [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] oder [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten in einer eingebetteten Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
