---
title: "Gewusst wie: Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen | Microsoft Docs"
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
  - "Bindung, An XML-Daten mithilfe von XMLDataProvider-Abfragen"
  - "Datenbindung, Bindung an XML-Daten mithilfe von XMLDataProvider-Abfragen"
  - "XmlDataProvider, Binden an XML-Daten"
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Gewusst wie: Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen
Dieses Beispiel zeigt, wie Daten mit einem <xref:System.Windows.Data.XmlDataProvider> an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] gebunden werden.  
  
 Mit einem <xref:System.Windows.Data.XmlDataProvider> können Sie mithilfe der Datenbindung auf die Ihrer Anwendung zugrunde liegenden [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Knotenstrukturen zugreifen.  Mit anderen Worten: Ein <xref:System.Windows.Data.XmlDataProvider> bietet eine komfortable Möglichkeit, jede beliebige Struktur von [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]\-Knoten als [Bindungsquelle](GTMT) zu verwenden.  
  
## Beispiel  
 Im folgenden Beispiel werden die Daten direkt als [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-*Dateninsel* im Abschnitt <xref:System.Windows.FrameworkElement.Resources%2A> eingebettet.  Eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Dateninsel muss mit `<x:XData>`\-Tags umschlossen sein und immer über einen einzelnen Stammknoten, in diesem Beispiel *Inventory*, verfügen.  
  
> [!NOTE]
>  Der Stammknoten der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten verfügt über ein **xmlns**\-Attribut, das den [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Namespace auf eine leere Zeichenfolge festlegt.  Dies ist eine Anforderung für die Anwendung von XPath\-Abfragen auf eine Dateninsel, die sich inline innerhalb der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite befindet.  In diesem Inlinefall erbt [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], und damit die Dateninsel, den <xref:System.Windows>\-Namespace.  Aus diesem Grund müssen Sie den Namespace auf eine leere Zeichenfolge festlegen und verhindern so, dass XPath\-Abfragen vom <xref:System.Windows>\-Namespace bestimmt werden, was zu fehlgeleiteten Abfragen führen würde.  
  
 [!code-xml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Wie in diesem Beispiel veranschaulicht, müssen Sie zur Erstellung derselben Bindungsdeklaration in Attributsyntax die Sonderzeichen ordnungsgemäß mit einem Escapezeichen versehen.  Weitere Informationen hierzu finden Sie unter [XML\-Zeichenentitäten und XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 Wenn dieses Beispiel ausgeführt wird, zeigt das <xref:System.Windows.Controls.ListBox> die folgenden Elemente an.  Das sind die *Title*\-Angaben aller Elemente unter *Books*, deren *Stock*\-Wert entweder "*out*" \(vergriffen\) lautet oder einen *Number*\-Wert von 3 bzw. größer\/gleich 8 aufweist.  Beachten Sie, dass keine *CD*\-Elemente zurückgegeben werden, da der im <xref:System.Windows.Data.XmlDataProvider>\-Element festgelegte <xref:System.Windows.Data.XmlDataProvider.XPath%2A>\-Wert angibt, dass nur die *Books*\-Elemente zur Verfügung gestellt werden sollen \(durch die Einrichtung eines Filters\).  
  
 ![XPath&#45;Beispiel](../../../../docs/framework/wpf/data/media/xpathexample.png "XPathExample")  
  
 In diesem Beispiel werden die Buchtitel angezeigt, weil der <xref:System.Windows.Data.Binding.XPath%2A> der <xref:System.Windows.Controls.TextBlock>\-Bindung in der <xref:System.Windows.DataTemplate> auf "*Title*" festgelegt ist.  Um den Wert eines Attributs anzuzeigen, z. B. *ISBN*, legen Sie den <xref:System.Windows.Data.Binding.XPath%2A>\-Wert auf "`@ISBN`" fest.  
  
 Die **XPath**\-Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden von der XmlNode.SelectNodes\-Methode behandelt.  Sie können die **XPath**\-Abfragen ändern, um andere Ergebnisse abzurufen.  Es folgen einige Beispiele der <xref:System.Windows.Data.Binding.XPath%2A>\-Abfrage für das gebundene <xref:System.Windows.Controls.ListBox> des vorherigen Beispiels:  
  
-   `XPath="Book[1]"` gibt das erste Buchelement \("XML in Action"\) zurück.  Beachten Sie, dass **XPath**\-Indizes auf 1, nicht auf 0, basieren.  
  
-   `XPath="Book[@*]"` gibt alle Buchelemente mit beliebigen Attributen zurück.  
  
-   `XPath="Book[last()-1]"` gibt das vorletzte Buchelement \("Introducing Microsoft .NET"\) zurück.  
  
-   `XPath="*[position()>3]"` gibt außer den ersten 3 Buchelementen alle Buchelemente zurück.  
  
 Wenn Sie eine **XPath**\-Abfrage ausführen, gibt sie ein <xref:System.Xml.XmlNode>\-Element oder eine Liste von XmlNodes zurück.  Ein <xref:System.Xml.XmlNode>\-Element ist ein [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Objekt. Das bedeutet, dass Sie die <xref:System.Windows.Data.Binding.Path%2A>\-Eigenschaft zur Bindung an die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Eigenschaften verwenden können.  Betrachten Sie erneut das vorherige Beispiel.  Wenn Sie den Rest des Beispiels unverändert lassen und nur die <xref:System.Windows.Controls.TextBlock>\-Bindung wie folgt ändern, werden im <xref:System.Windows.Controls.ListBox> die Namen der zurückgegebenen XmlNodes angezeigt.  In diesem Fall lautet der Name aller zurückgegebenen Knoten "*Book*".  
  
 [!code-xml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 In bestimmten Anwendungen ist das Einbetten von [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] als Dateninsel in die Quelle der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite nicht geeignet, da zur Kompilierzeit der genaue Inhalt der Daten bekannt sein muss.  Aus diesem Grund wird das Abrufen von Daten aus einer externen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Datei ebenso unterstützt. Das folgende Beispiel veranschaulicht dies.  
  
 [!code-xml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Wenn die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten in einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Remotedatei gespeichert sind, definieren Sie den Zugriff auf die Daten durch das Zuweisen einer geeigneten [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] zum <xref:System.Windows.Data.XmlDataProvider.Source%2A>\-Attribut. Das folgende Beispiel veranschaulicht dies:  
  
```  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## Siehe auch  
 <xref:System.Windows.Data.ObjectDataProvider>   
 [Binden an XDocument, XElement oder LINQ für XML\-Abfrageergebnisse](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)   
 [Verwenden des Master\-\/Detailmusters mit hierarchischen XML\-Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)   
 [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)