---
title: "GetXmlNamespace Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.GetXmlNamespace"
  - "GetXmlNamespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetXmlNamespace operator"
  - "GetXmlNamespace keyword"
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# GetXmlNamespace Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ruft das <xref:System.Xml.Linq.XNamespace>\-Objekt ab, das dem angegebenen XML\-Namespacepräfix entspricht.  
  
## Syntax  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## Teile  
 `xmlNamespacePrefix`  
 Optional.  Die Zeichenfolge, die das XML\-Namespacepräfix identifiziert.  Falls angegeben, muss diese Zeichenfolge ein gültiger XML\-Bezeichner sein.  Weitere Informationen finden Sie unter [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  Wenn kein Präfix angegeben ist, wird der Standardnamespace zurückgegeben.  Wenn kein Standardnamespace angegeben ist, wird ein leerer Namespace zurückgegeben.  
  
## Rückgabewert  
 Das <xref:System.Xml.Linq.XNamespace>\-Objekt, das dem XML\-Namespacepräfix entspricht.  
  
## Hinweise  
 Der Operator `GetXmlNamespace` ruft das <xref:System.Xml.Linq.XNamespace>\-Objekt ab, das dem XML\-Namespacepräfix `xmlNamespacePrefix` entspricht.  
  
 XML\-Namespacepräfixe können in XML\-Literalen und XML\-Achseneigenschaften direkt verwendet werden.  Bevor es im Code verwendet werden kann, muss jedoch das Namespacepräfix mit dem Operator `GetXmlNamespace` in ein <xref:System.Xml.Linq.XNamespace>\-Objekt konvertiert werden.  Ein nicht qualifizierter Elementname kann an ein <xref:System.Xml.Linq.XNamespace>\-Objekt angehängt werden, um ein vollqualifiziertes <xref:System.Xml.Linq.XName>\-Objekt zu erhalten, das für viele [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]\-Methoden erforderlich ist.  
  
## Beispiel  
 Im folgenden Beispiel wird `ns` als ein XML\-Namespacepräfix importiert.  Anschließend wird das Namespacepräfix verwendet, um ein XML\-Literal zu erstellen und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:phone` zuzugreifen.  Anschließend wird dieser untergeordnete Knoten an die `ShowName`\-Unterroutine übergeben, die einen qualifizierten Namen erstellt, indem der Operator `GetXmlNamespace` verwendet wird.  Die `ShowName`\-Unterroutine übergibt dann den qualifizierten Namen an die <xref:System.Xml.Linq.XNode.Ancestors%2A>\-Methode, um den übergeordneten `ns:contact`\-Knoten zu erhalten.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/getxmlnamespace-operator_1.vb)]  
  
 Wenn `TestGetXmlNamespace.RunSample()` aufgerufen wird, wird ein Meldungsfeld mit dem folgenden Text angezeigt:  
  
 `Name: Patrick Hines`  
  
## Siehe auch  
 [Imports Statement \(XML Namespace\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Accessing XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)