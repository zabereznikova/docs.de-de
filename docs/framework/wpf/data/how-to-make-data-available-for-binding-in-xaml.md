---
title: "Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden | Microsoft Docs"
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
  - "Binden von Daten, Bereitstellen von Daten für"
  - "Datenbindung, Bereitstellen von Daten für die Bindung"
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden
In diesem Thema werden die unterschiedlichen Möglichkeiten zur Bereitstellung von Daten erläutert, um diese je nach den Anforderungen Ihrer Anwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zu binden.  
  
## Beispiel  
 Wenn Sie über ein [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Objekt verfügen, zu dem Sie eine Bindung aus [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellen möchten, besteht eine Möglichkeit zur Bereitstellung des Objekts darin, es als Ressource zu definieren und mit einem `x:Key` zu versehen.  Im folgenden Beispiel wird ein `Person`\-Objekt mit einer Zeichenfolgeneigenschaft mit dem Namen `PersonName` verwendet.  Das `Person`\-Objekt wird im Namespace mit dem Namen `SDKSample` definiert.  
  
 [!code-xml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 Wie im folgenden Beispiel gezeigt, können Sie daraufhin in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] eine Bindung zum Objekt erstellen.  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Alternativ dazu können Sie, wie im folgenden Beispiel dargestellt, die <xref:System.Windows.Data.ObjectDataProvider>\-Klasse verwenden.  
  
 [!code-xml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 Die Bindung wird auf dieselbe Weise definiert:  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 In diesem speziellen Beispiel wird dasselbe Ergebnis erzielt: Ein <xref:System.Windows.Controls.TextBlock> mit dem Textinhalt `Joe`.  Die <xref:System.Windows.Data.ObjectDataProvider>\-Klasse verfügt jedoch über Funktionen wie die Fähigkeit, eine Bindung zum Ergebnis einer Methode zu erstellen.  Wenn Sie die entsprechenden Funktionalitäten benötigen, verwenden Sie die <xref:System.Windows.Data.ObjectDataProvider>\-Klasse.  
  
 Wenn Sie jedoch eine Bindung zu einem Objekt erstellen möchten, das bereits erstellt wurde, müssen Sie die `DataContext`\-Eigenschaft, wie im folgenden Beispiel dargestellt, im Code festlegen.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Informationen darüber, wie Sie mit der <xref:System.Windows.Data.XmlDataProvider>\-Klasse auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten für die Bindung zugreifen, finden Sie unter [Binden an XML\-Daten mithilfe von XMLDataProvider und XPath\-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  Informationen darüber, wie Sie mit der <xref:System.Windows.Data.ObjectDataProvider>\-Klasse auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten für die Bindung zugreifen, finden Sie unter [Binden an XDocument, XElement oder LINQ für XML\-Abfrageergebnisse](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Informationen über die verschiedenen Methoden zur Angabe der Daten, die Sie binden möchten, finden Sie unter [Angeben der Bindungsquelle](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).  Wenn Sie erfahren möchten, zu welchen Datentypen Bindungen erstellt werden können oder wie Sie für die Bindung eigene [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Objekte implementieren können, finden Sie die entsprechenden Informationen unter [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)