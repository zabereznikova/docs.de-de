---
title: 'Vorgehensweise: Verwenden von XML-Namespaces bei der Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 38bf6e8f88b0325193d49148cd6c33031f7b0a6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149993"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Vorgehensweise: Verwenden von XML-Namespaces bei der Datenbindung
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie in der [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Bindungsquelle angegebene Namespaces behandelt werden.  
  
 Wenn Ihre [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten die folgende [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace-Definition haben:  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 Können Sie die <xref:System.Windows.Data.XmlNamespaceMapping> -Element zuordnen den Namespace, der eine <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, wie im folgenden Beispiel. Anschließend können Sie die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> zum Verweisen auf die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace. Die <xref:System.Windows.Controls.ListBox> in diesem Beispiel zeigt die *Titel* und *DC: Date* aller *Element*.  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 Beachten Sie, dass die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> Sie angeben, muss keine der im verwendeten übereinstimmen der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Datenquellenobjekt; Wenn das Präfix in ändert sich die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle, die die Zuordnung weiterhin funktioniert.  
  
 In diesem Beispiel ist die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten stammen aus einem Webdienst, aber die <xref:System.Windows.Data.XmlNamespaceMapping> Element funktioniert auch mit Inline- [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] oder [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten in einer eingebetteten Datei.  
  
## <a name="see-also"></a>Siehe auch

- [Binden an XML-Daten mithilfe der XMLDataProvider-Klasse und mithilfe von XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht über die Datenbindung](data-binding-overview.md)
- [Gewusst wie-Themen](data-binding-how-to-topics.md)
