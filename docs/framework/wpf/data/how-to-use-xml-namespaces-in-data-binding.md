---
title: "Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung | Microsoft Docs"
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
  - "Datenbindung, XML-Namespaces"
  - "Namespaces, XML"
  - "XML, Namespaces"
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung
## Beispiel  
 Dieses Beispiel zeigt, wie in der [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)][Bindungsquelle](GTMT) angegebene Namespaces behandelt werden.  
  
 Wenn die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten die folgende [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Namespacedefinition aufweisen:  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 Mit dem <xref:System.Windows.Data.XmlNamespaceMapping>\-Element können Sie den Namespace einem <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> zuordnen, wie im folgenden Beispiel.  Sie können dann mit dem <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> auf den [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Namespace verweisen.  Das <xref:System.Windows.Controls.ListBox> in diesem Beispiel zeigt *Titel* und *dc:date* jedes *Elements* an.  
  
 <!-- TODO: review snippet reference [!code-xml[XmlnsBind#XmlNamespaceMapping](../../../../samples/snippets/xaml/VS_Snippets_Wpf/XmlnsBind/XAML/Window1.xaml#xmlnamespacemapping)]  -->
 <!-- TODO: review snippet reference [!code-xml[XmlnsBind#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBind/CS/Window1.xaml#xmlnamespacemapping)]  -->  
  
 Beachten Sie, dass das angegebene <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> nicht mit dem in der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Quelle verwendeten Präfix übereinstimmen muss. Wenn das Präfix in der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Quelle geändert wird, funktioniert die Zuordnung weiterhin.  
  
 In diesem speziellen Beispiel stammen die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten aus einem Webdienst, das <xref:System.Windows.Data.XmlNamespaceMapping>\-Element funktioniert jedoch auch mit Inline\-[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] oder [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten in einer eingebetteten Datei.  
  
## Siehe auch  
 [Binden an XML\-Daten mithilfe von XMLDataProvider und XPath\-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)