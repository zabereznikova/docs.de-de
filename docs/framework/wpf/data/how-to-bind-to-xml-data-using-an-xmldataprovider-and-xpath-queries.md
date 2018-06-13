---
title: 'Gewusst wie: Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen'
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: bb8eb727fb6614440721c4d34a7d1828182d2f14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557445"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Gewusst wie: Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen
In diesem Beispiel wird gezeigt, wie zum Binden an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Daten mithilfe einer <xref:System.Windows.Data.XmlDataProvider>.  
  
 Mit einem <xref:System.Windows.Data.XmlDataProvider>, die zugrunde liegenden Daten, die über die Datenbindung in der Anwendung zugegriffen werden können, kann Strukturen von werden [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Knoten. Das heißt, eine <xref:System.Windows.Data.XmlDataProvider> bietet eine einfache Möglichkeit, verwenden Sie die Strukturen der [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Knoten als Bindungsquelle.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Daten direkt als eingebettet ein [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] *Dateninsel* innerhalb der <xref:System.Windows.FrameworkElement.Resources%2A> Abschnitt. Eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Dateninsel muss mit `<x:XData>`-Tags umschlossen sein und immer über einen einzelnen Stammknoten, in diesem Beispiel *Inventory*, verfügen.  
  
> [!NOTE]
>  Der Stammknoten der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten verfügt über ein **xmlns**-Attribut, das den [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace auf eine leere Zeichenfolge festlegt. Dies ist eine Anforderung für die Anwendung von XPath-Abfragen auf eine Dateninsel, die sich inline innerhalb der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seite befindet. In diesem Inlinefall der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], und somit die Dateninsel erbt die <xref:System.Windows> Namespace. Aus diesem Grund müssen Sie den Namespace zu verhindern, dass XPath-Abfragen qualifiziert werden, indem leere Festlegen der <xref:System.Windows> -Namespace, der fehlgeleiteten Abfragen führen würde.  
  
 [!code-xaml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Wie in diesem Beispiel veranschaulicht, müssen Sie zur Erstellung derselben Bindungsdeklaration in Attributsyntax die Sonderzeichen ordnungsgemäß mit einem Escapezeichen versehen. Weitere Informationen hierzu finden Sie unter [XML-Zeichenentitäten und XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 Die <xref:System.Windows.Controls.ListBox> zeigt die folgenden Elemente aus, wenn dieses Beispiel ausgeführt wird. Das sind die *Title*-Angaben aller Elemente unter *Books*, deren *Stock-Wert* entweder *out* (vergriffen) lautet oder einen *Number*-Wert von 3 bzw. größer gleich 8 aufweist. Beachten Sie, dass keine *CD* Elemente werden zurückgegeben, da die <xref:System.Windows.Data.XmlDataProvider.XPath%2A> festgelegten Wert, auf die <xref:System.Windows.Data.XmlDataProvider> gibt an, dass nur die *Bücher* Elemente verfügbar gemacht werden sollen (im Wesentlichen einen Filter festlegen).  
  
 ![XPath-Beispiel](../../../../docs/framework/wpf/data/media/xpathexample.PNG "XPathExample")  
  
 In diesem Beispiel werden die Buchtitel angezeigt, da die <xref:System.Windows.Data.Binding.XPath%2A> von der <xref:System.Windows.Controls.TextBlock> Bindung in der <xref:System.Windows.DataTemplate> auf festgelegt ist "*Titel*". Wenn Sie z. B. den Wert eines Attributs anzeigen möchten die *ISBN*, legen Sie den <xref:System.Windows.Data.Binding.XPath%2A> Wert "`@ISBN`".  
  
 Die **XPath**-Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden von der XmlNode.SelectNodes-Methode behandelt. Sie können die **XPath**-Abfragen ändern, um andere Ergebnisse abzurufen. Hier sind einige Beispiele für die <xref:System.Windows.Data.Binding.XPath%2A> Abfragen auf die Grenze <xref:System.Windows.Controls.ListBox> aus dem vorherigen Beispiel:  
  
-   `XPath="Book[1]"` gibt das erste Buchelement ("XML in Action") zurück. Beachten Sie, dass **XPath**-Indizes auf 1 und nicht auf 0 basieren.  
  
-   `XPath="Book[@*]"` gibt alle Buchelemente mit beliebigen Attributen zurück.  
  
-   `XPath="Book[last()-1]"` gibt das vorletzte Buchelement („Introducing Microsoft .NET“) zurück.  
  
-   `XPath="*[position()>3]"` gibt außer den ersten 3 Buchelementen alle Buchelemente zurück.  
  
 Beim Ausführen einer **XPath** abzufragen, es gibt eine <xref:System.Xml.XmlNode> oder eine Liste von XmlNodes. <xref:System.Xml.XmlNode> ist eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] -Objekt, d. h., Sie können die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft zum Binden an die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Eigenschaften. Betrachten Sie erneut das vorherige Beispiel. Wenn der Rest des Beispiels unverändert bleibt, und Sie ändern die <xref:System.Windows.Controls.TextBlock> an die folgenden binden, sehen Sie die Namen der zurückgegebenen XmlNodes in der <xref:System.Windows.Controls.ListBox>. In diesem Fall lautet der Name aller zurückgegebenen Knoten *Book*.  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 In bestimmten Anwendungen ist das Einbetten von [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] als Dateninsel in die Quelle der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seite nicht geeignet, da zur Kompilierzeit der genaue Inhalt der Daten bekannt sein muss. Aus diesem Grund wird das Abrufen von Daten aus einer externen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datei ebenso unterstützt, was im folgenden Beispiel veranschaulicht wird:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Wenn die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten befinden sich in einem [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] , würde definieren Sie den Zugriff auf die Daten durch Zuweisen eines geeigneten [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] auf die <xref:System.Windows.Data.XmlDataProvider.Source%2A> -Attribut wie folgt:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Data.ObjectDataProvider>  
 [Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)  
 [Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
