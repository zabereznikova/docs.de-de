---
title: 'Vorgehensweise: Binden an XML-Daten mithilfe der XMLDataProvider-Klasse und mithilfe von XPath-Abfragen'
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: dc4fb2d5f0c48c077d2ff7ca5e5269ce5cba71e5
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400499"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Vorgehensweise: Binden an XML-Daten mithilfe der XMLDataProvider-Klasse und mithilfe von XPath-Abfragen
In diesem Beispiel wird gezeigt, wie [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] eine <xref:System.Windows.Data.XmlDataProvider>Bindung an Daten mithilfe von hergestellt wird.  
  
 Bei kann es sich bei den zugrunde liegenden Daten, auf die über die Datenbindung in der Anwendung zugegriffen werden [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] kann ,umeinebeliebigeStrukturvonKnotenhandeln.<xref:System.Windows.Data.XmlDataProvider> Mit anderen Worten: eine <xref:System.Windows.Data.XmlDataProvider> stellt eine bequeme Möglichkeit dar, jede [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Knoten Struktur als Bindungs Quelle zu verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Daten direkt als [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] *Daten Insel* innerhalb des <xref:System.Windows.FrameworkElement.Resources%2A> -Abschnitts eingebettet. Eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Dateninsel muss mit `<x:XData>`-Tags umschlossen sein und immer über einen einzelnen Stammknoten, in diesem Beispiel *Inventory*, verfügen.  
  
> [!NOTE]
>  Der Stammknoten der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten verfügt über ein **xmlns**-Attribut, das den [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace auf eine leere Zeichenfolge festlegt. Dies ist eine Anforderung für die Anwendung von XPath-Abfragen auf eine Dateninsel, die sich inline innerhalb der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seite befindet. In diesem Inline Fall [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]erbt der und somit die Daten Insel den <xref:System.Windows> -Namespace. Aus diesem Grund müssen Sie den Namespace leer festlegen, damit XPath-Abfragen nicht durch den <xref:System.Windows> Namespace qualifiziert werden, was die Abfragen falsch leiten würde.  
  
 [!code-xaml[XMLDataSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Wie in diesem Beispiel veranschaulicht, müssen Sie zur Erstellung derselben Bindungsdeklaration in Attributsyntax die Sonderzeichen ordnungsgemäß mit einem Escapezeichen versehen. Weitere Informationen hierzu finden Sie unter [XML-Zeichenentitäten und XAML](../../xaml-services/xml-character-entities-and-xaml.md).  
  
 In <xref:System.Windows.Controls.ListBox> werden die folgenden Elemente angezeigt, wenn dieses Beispiel ausgeführt wird. Das sind die *Title*-Angaben aller Elemente unter *Books*, deren *Stock-Wert* entweder *out* (vergriffen) lautet oder einen *Number*-Wert von 3 bzw. größer gleich 8 aufweist. Beachten Sie, dass keine *CD* -Elemente zurück <xref:System.Windows.Data.XmlDataProvider.XPath%2A> gegeben werden, da <xref:System.Windows.Data.XmlDataProvider> der Wert, der auf festgelegt ist, angibt, dass nur die *Bücher* Elemente verfügbar gemacht werden sollen (im Grunde ein Filter)  
  
 ![Screenshot des XPath-Beispiels mit dem Titel von vier Büchern.](./media/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries/xpath-example-listbox-details.png)  
  
 In diesem Beispiel werden die Buchtitel angezeigt, da <xref:System.Windows.Data.Binding.XPath%2A> die <xref:System.Windows.Controls.TextBlock> der Bindung in <xref:System.Windows.DataTemplate> auf "*Title*" festgelegt ist. Wenn Sie den Wert eines Attributs anzeigen möchten, z. b. die *ISBN*, legen Sie diesen <xref:System.Windows.Data.Binding.XPath%2A> Wert auf "`@ISBN`" fest.  
  
 Die **XPath**-Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden von der XmlNode.SelectNodes-Methode behandelt. Sie können die **XPath**-Abfragen ändern, um andere Ergebnisse abzurufen. Im folgenden finden Sie einige Beispiele <xref:System.Windows.Data.Binding.XPath%2A> für die Abfrage der <xref:System.Windows.Controls.ListBox> Grenze aus dem vorherigen Beispiel:  
  
- `XPath="Book[1]"` gibt das erste Buchelement ("XML in Action") zurück. Beachten Sie, dass **XPath**-Indizes auf 1 und nicht auf 0 basieren.  
  
- `XPath="Book[@*]"` gibt alle Buchelemente mit beliebigen Attributen zurück.  
  
- `XPath="Book[last()-1]"` gibt das vorletzte Buchelement („Introducing Microsoft .NET“) zurück.  
  
- `XPath="*[position()>3]"` gibt außer den ersten 3 Buchelementen alle Buchelemente zurück.  
  
 Wenn Sie eine **XPath** -Abfrage ausführen, wird eine <xref:System.Xml.XmlNode> oder eine Liste von XMLNodes zurückgegeben. <xref:System.Xml.XmlNode>ist ein Common Language Runtime (CLR)-Objekt. das bedeutet, dass Sie <xref:System.Windows.Data.Binding.Path%2A> die-Eigenschaft verwenden können, um eine Bindung an die Common Language Runtime (CLR)-Eigenschaften zu erhalten. Betrachten Sie erneut das vorherige Beispiel. Wenn der Rest des Beispiels unverändert bleibt und Sie die <xref:System.Windows.Controls.TextBlock> Bindung in Folgendes ändern, werden die Namen der zurückgegebenen XmlNodes in der <xref:System.Windows.Controls.ListBox>angezeigt. In diesem Fall lautet der Name aller zurückgegebenen Knoten *Book*.  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 In bestimmten Anwendungen ist das Einbetten von [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] als Dateninsel in die Quelle der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seite nicht geeignet, da zur Kompilierzeit der genaue Inhalt der Daten bekannt sein muss. Aus diesem Grund wird das Abrufen von Daten aus einer externen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datei ebenso unterstützt, was im folgenden Beispiel veranschaulicht wird:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Wenn sich [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] die Daten in einer Remote [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Datei befinden, definieren Sie den Zugriff auf die Daten, indem Sie [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] dem <xref:System.Windows.Data.XmlDataProvider.Source%2A> Attribut wie folgt ein entsprechendes zuweisen:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.ObjectDataProvider>
- [Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)
- [Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Übersicht über Bindungsquellen](binding-sources-overview.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
