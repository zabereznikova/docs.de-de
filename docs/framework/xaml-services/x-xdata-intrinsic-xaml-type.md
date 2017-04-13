---
title: "x:XData Intrinsic XAML Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:XData"
  - "XData"
  - "xXData"
helpviewer_keywords: 
  - "XAML [XAML Services], x:XData directive element"
  - "XData in XAML [XAML Services]"
  - "x:XData XAML directive element [XAML Services]"
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: 17
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 17
---
# x:XData Intrinsic XAML Type
Aktiviert die Platzierung von XML\-Dateninseln innerhalb einer XAML\-Produktion.  XML\-Elemente `x:XData` sollten nicht von XAML\-Prozessoren so behandelt werden, als ob sie Teil des agierenden XAML\-Standardnamespace oder eines anderen XAML\-Namespace wären.  `x:XData` kann beliebige wohlgeformte XML enthalten.  
  
## Verwendung von XAML\-Objektelementen  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`elementDataRoot`|Das einzelne Stammelement der eingeschlossenen Dateninsel.  Für die meisten tatsächlichen Consumer wird XML, das keinen einzelnen Stamm hat, als ungültig angesehen.  Insbesondere ist ein einzelner Stamm erforderlich, wenn `x:XData` als XML\-Datenquelle für WPF und viele anderen Technologien vorgesehen ist, die XML\-Quellen für die Datenbindung verwenden.|  
|`[elementData]`|Optional.  XML, das die XML\-Daten darstellt.  Entsprechend den allgemeinen XML\-Regeln kann eine beliebige Anzahl von Elementen als Elementdaten und verschachtelten Elemente in anderen Elementen enthalten sein.|  
  
## Hinweise  
 Die XML\-Elemente in einem `x:XData`\-Objekt können alle möglichen Namespaces und Präfixe der enthaltenen XMLDOM in den Daten deklarieren.  
  
 Programmgesteuerter Zugriff auf XML\-Daten und der `x:XData` systeminterne XAML\-Typ ist in .NET Framework\-XAML\-Diensten durch die <xref:System.Windows.Markup.XData>\-Klasse möglich.  
  
## Hinweise zur WPF\-Verwendung  
 Das `x:XData`\-Objekt wird vorrangig als untergeordnetes Objekt von <xref:System.Windows.Data.XmlDataProvider> oder alternativ dazu als untergeordnetes Objekt der <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=fullName>\-Eigenschaft verwendet \(in XAML wird sie in der Regel mithilfe der Eigenschaftenelementsyntax ausgedrückt\).  
  
 Normalerweise sollten die Daten den XML\-Basis\-Namespace innerhalb der Dateninsel als neuen XML\-Namespace \(auf eine leere Zeichenfolge gesetzt\) definieren.  Dies ist für simple Dateninseln am einfachsten, da die <xref:System.Windows.Data.Binding.XPath%2A>\-Ausdrücke, die zum Verweisen auf und Binden an die Daten verwendet werden, keine Einbeziehung von Präfixen erfordern.  Komplexere Dateninseln können für die Daten mehrere Präfixe definieren und auf Stammebene für den XML\-Namespace ein spezielles Präfix verwenden.  In diesem Fall müssen alle Verweise auf <xref:System.Windows.Data.Binding.XPath%2A>\-Ausdrücke das entsprechende Präfix mit Namespacezuordnung enthalten.  Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Technisch können Sie `x:XData` als Inhalt einer beliebigen Eigenschaft vom Typ <xref:System.Xml.Serialization.IXmlSerializable> verwenden.  Die einzige deutlich erkennbare Implementierung ist jedoch <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=fullName>..  
  
## Siehe auch  
 <xref:System.Windows.Data.XmlDataProvider>   
 [Übersicht über Datenbindung](../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Bindung als Markuperweiterung](../../../docs/framework/wpf/advanced/binding-markup-extension.md)