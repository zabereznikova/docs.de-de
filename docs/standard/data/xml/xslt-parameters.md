---
title: "XSLT-Parameter | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: fe60aaa0-ae43-4b1c-9be1-426af66ba757
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# XSLT-Parameter
XSLT\-Parameter werden der <xref:System.Xml.Xsl.XsltArgumentList> mithilfe der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>\-Methode hinzugefügt.  Dabei werden ein qualifizierter Name und ein Namespace\-URI \(Uniform Resource Identifier\) mit dem Parameterobjekt verknüpft.  
  
### So verwenden Sie einen XSLT\-Parameter  
  
1.  Erstellen Sie ein <xref:System.Xml.Xsl.XsltArgumentList>\-Objekt, und fügen Sie den Parameter mit der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>\-Methode hinzu.  
  
2.  Rufen Sie den Parameter aus dem Stylesheet auf.  
  
3.  Übergeben Sie das <xref:System.Xml.Xsl.XsltArgumentList>\-Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>\-Methode.  
  
## Parametertypen  
 Das Parameterobjekt sollte einem W3C\-Typ entsprechen.  In der folgenden Tabelle sind die jeweiligen W3C\-Typen mit den entsprechenden Microsoft .NET\-Klassen \(Typen\) aufgelistet. Weiterhin wird angegeben, ob es sich bei dem W3C\-Typ um einen XPath\-Typ oder einen XSLT\-Typ handelt.  
  
|W3C\-Typ|Entsprechende .NET\-Klasse \(Typ\)|XPath\-Typ oder XSLT\-Typ|  
|--------------|----------------------------------------|-------------------------------|  
|`String`|<xref:System.String?displayProperty=fullName>|XPath|  
|`Boolean`|<xref:System.Boolean?displayProperty=fullName>|XPath|  
|`Number`|<xref:System.Double?displayProperty=fullName>|XPath|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=fullName>|XSLT|  
|`Node*`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=fullName>|XPath|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator><br /><br /> **XPathNavigator\[\]**|XPath|  
  
 \*Dies entspricht einer Knotengruppe, die einen Knoten enthält.  
  
 Wenn das Parameterobjekt keiner der oben genannten Klassen entspricht, wird es entsprechend der folgenden Regeln konvertiert.  Numerische CLR\-Typen \(Common Language Runtime\) werden in <xref:System.Double> konvertiert.  Der <xref:System.DateTime>\-Typ wird in <xref:System.String> konvertiert.  <xref:System.Xml.XPath.IXPathNavigable>\-Typen werden in <xref:System.Xml.XPath.XPathNavigator> konvertiert.  **XPathNavigator\[\]** wird konvertiert in <xref:System.Xml.XPath.XPathNodeIterator>.  
  
 Alle anderen Typen lösen einen Fehler aus.  
  
## Beispiel  
 Im folgenden Beispiel wird mit der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>\-Methode ein Parameter erstellt, der ein berechnetes Skontodatum enthält.  Das Skontodatum ist 20 Tage nach dem Auftragsdatum.  
  
 [!code-csharp[XSLT_Param#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Param/CS/xsltparam.cs#1)]
 [!code-vb[XSLT_Param#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Param/VB/xsltparam.vb#1)]  
  
### Eingabe  
  
##### order.xml  
 [!code-xml[XSLT_Param#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/order.xml#2)]  
  
##### discount.xsl  
 [!code-xml[XSLT_Param#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/discount.xsl#3)]  
  
### Ausgabe  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<order>  
  <total>36.9</total>  
     15% discount if paid by: 2/4/2004 12:00:00 AM  
</order>  
```  
  
## Siehe auch  
 [XSLT\-Transformationen](../../../../docs/standard/data/xml/xslt-transformations.md)