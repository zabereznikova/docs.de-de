---
title: 'Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 47ce0d951df39c7b60aa2a543baf845f5471de6c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460307"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung
## <a name="example"></a>Beispiel
 Dieses Beispiel zeigt, wie in der [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Bindungsquelle angegebene Namespaces behandelt werden.

 Wenn Ihre [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten die folgende [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace-Definition haben:

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 Sie können das <xref:System.Windows.Data.XmlNamespaceMapping>-Element verwenden, um den Namespace einem <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>zuzuordnen, wie im folgenden Beispiel gezeigt. Anschließend können Sie den <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> verwenden, um auf den [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace zu verweisen. Der <xref:System.Windows.Controls.ListBox> in diesem Beispiel zeigt den *Titel* und *DC: Date* der einzelnen *Elemente*an.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 Beachten Sie, dass der <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, den Sie angeben, nicht mit dem in der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle verwendeten identisch sein muss. Wenn das Präfix in der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle geändert wird, funktioniert Ihre Zuordnung weiterhin.

 In diesem Beispiel stammen die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten von einem Webdienst, aber das <xref:System.Windows.Data.XmlNamespaceMapping> Element funktioniert auch mit Inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] oder [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten in einer eingebetteten Datei.

## <a name="see-also"></a>Siehe auch

- [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
