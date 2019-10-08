---
title: 'Vorgehensweise: Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen'
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: d92b01c453a9e07a5d4a6d1900d54e8c86210041
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005682"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Vorgehensweise: Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen
In diesem Beispiel wird gezeigt, wie mit einem <xref:System.Windows.Data.XmlDataProvider> an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Daten gebunden wird.  
  
 Bei einem <xref:System.Windows.Data.XmlDataProvider> können die zugrunde liegenden Daten, auf die über die Datenbindung in Ihrer Anwendung zugegriffen werden kann, jede Struktur von [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Knoten sein. Mit anderen Worten: ein <xref:System.Windows.Data.XmlDataProvider> stellt eine bequeme Möglichkeit dar, jede Struktur von [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Knoten als Bindungs Quelle zu verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Daten direkt als [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]- *Daten Insel* innerhalb des <xref:System.Windows.FrameworkElement.Resources%2A>-Abschnitts eingebettet. Eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Dateninsel muss mit `<x:XData>`-Tags umschlossen sein und immer über einen einzelnen Stammknoten, in diesem Beispiel *Inventory*, verfügen.  
  
> [!NOTE]
> Der Stammknoten der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten verfügt über ein **xmlns**-Attribut, das den [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace auf eine leere Zeichenfolge festlegt. Dies ist eine Anforderung für die Anwendung von XPath-Abfragen auf eine Dateninsel, die sich inline innerhalb der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seite befindet. In diesem Inline Fall erbt der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und somit die Daten Insel den <xref:System.Windows>-Namespace. Aus diesem Grund müssen Sie den Namespace leer festlegen, um zu verhindern, dass XPath-Abfragen vom <xref:System.Windows>-Namespace qualifiziert werden, was die Abfragen falsch leiten würde.  
  
 [!code-xaml[XMLDataSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Wie in diesem Beispiel veranschaulicht, müssen Sie zur Erstellung derselben Bindungsdeklaration in Attributsyntax die Sonderzeichen ordnungsgemäß mit einem Escapezeichen versehen. Weitere Informationen hierzu finden Sie unter [XML-Zeichenentitäten und XAML](../../xaml-services/xml-character-entities-and-xaml.md).  
  
 Der <xref:System.Windows.Controls.ListBox> zeigt die folgenden Elemente an, wenn dieses Beispiel ausgeführt wird. Das sind die *Title*-Angaben aller Elemente unter *Books*, deren *Stock-Wert* entweder *out* (vergriffen) lautet oder einen *Number*-Wert von 3 bzw. größer gleich 8 aufweist. Beachten Sie, dass keine *CD* -Elemente zurückgegeben werden, da der <xref:System.Windows.Data.XmlDataProvider.XPath%2A>-Wert, der für die <xref:System.Windows.Data.XmlDataProvider> festgelegt ist, angibt, dass nur die *Bücher* Elemente verfügbar gemacht werden sollen (im Grunde ein Filter  
  
 ![Screenshot des XPath-Beispiels mit dem Titel von vier Büchern.](./media/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries/xpath-example-listbox-details.png)  
  
 In diesem Beispiel werden die Buchtitel angezeigt, da der <xref:System.Windows.Data.Binding.XPath%2A> der <xref:System.Windows.Controls.TextBlock>-Bindung in der <xref:System.Windows.DataTemplate> auf "*Title*" festgelegt ist. Wenn Sie den Wert eines Attributs anzeigen möchten, z. b. den *ISBN*, legen Sie den Wert <xref:System.Windows.Data.Binding.XPath%2A> auf "`@ISBN`" fest.  
  
 Die **XPath**-Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden von der XmlNode.SelectNodes-Methode behandelt. Sie können die **XPath**-Abfragen ändern, um andere Ergebnisse abzurufen. Im folgenden finden Sie einige Beispiele für die <xref:System.Windows.Data.Binding.XPath%2A>-Abfrage für das gebundene <xref:System.Windows.Controls.ListBox> aus dem vorherigen Beispiel:  
  
- `XPath="Book[1]"` gibt das erste Buchelement ("XML in Action") zurück. Beachten Sie, dass **XPath**-Indizes auf 1 und nicht auf 0 basieren.  
  
- `XPath="Book[@*]"` gibt alle Buchelemente mit beliebigen Attributen zurück.  
  
- `XPath="Book[last()-1]"` gibt das vorletzte Buchelement („Introducing Microsoft .NET“) zurück.  
  
- `XPath="*[position()>3]"` gibt außer den ersten 3 Buchelementen alle Buchelemente zurück.  
  
 Wenn Sie eine **XPath** -Abfrage ausführen, wird eine <xref:System.Xml.XmlNode> oder eine Liste von XMLNodes zurückgegeben. <xref:System.Xml.XmlNode> ist ein Common Language Runtime (CLR)-Objekt. das bedeutet, dass Sie die <xref:System.Windows.Data.Binding.Path%2A>-Eigenschaft verwenden können, um eine Bindung an die Common Language Runtime Eigenschaften (CLR) herzustellen. Betrachten Sie erneut das vorherige Beispiel. Wenn der Rest des Beispiels unverändert bleibt und Sie die <xref:System.Windows.Controls.TextBlock>-Bindung in Folgendes ändern, sehen Sie die Namen der zurückgegebenen XmlNodes in der <xref:System.Windows.Controls.ListBox>. In diesem Fall lautet der Name aller zurückgegebenen Knoten *Book*.  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 In bestimmten Anwendungen ist das Einbetten von [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] als Dateninsel in die Quelle der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seite nicht geeignet, da zur Kompilierzeit der genaue Inhalt der Daten bekannt sein muss. Aus diesem Grund wird das Abrufen von Daten aus einer externen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datei ebenso unterstützt, was im folgenden Beispiel veranschaulicht wird:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Wenn sich die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten in einer Remote [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datei befinden, definieren Sie den Zugriff auf die Daten, indem Sie dem <xref:System.Windows.Data.XmlDataProvider.Source%2A>-Attribut wie folgt eine entsprechende URL zuweisen:  
  
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
