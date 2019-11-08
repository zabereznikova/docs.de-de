---
title: 'Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740574"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung
## <a name="example"></a>Beispiel
 In diesem Beispiel wird gezeigt, wie in der XML-Bindungs Quelle angegebene Namespaces behandelt werden.

 Wenn die XML-Daten die folgende XML-Namespace Definition haben:

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 Sie können das <xref:System.Windows.Data.XmlNamespaceMapping>-Element verwenden, um den Namespace einem <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>zuzuordnen, wie im folgenden Beispiel gezeigt. Anschließend können Sie den <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> verwenden, um auf den XML-Namespace zu verweisen. Der <xref:System.Windows.Controls.ListBox> in diesem Beispiel zeigt den *Titel* und *DC: Date* der einzelnen *Elemente*an.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 Beachten Sie, dass die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, die Sie angeben, nicht mit der in der XML-Quelle verwendeten identisch sein muss. Wenn das Präfix in der XML-Quelle geändert wird, funktioniert Ihre Zuordnung weiterhin.

 In diesem speziellen Beispiel stammen die XML-Daten aus einem Webdienst, aber das <xref:System.Windows.Data.XmlNamespaceMapping>-Element funktioniert auch mit XML-Inline Daten oder XML-Daten in einer eingebetteten Datei.

## <a name="see-also"></a>Siehe auch

- [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
