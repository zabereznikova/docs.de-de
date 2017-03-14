---
title: "XML Descendant Axis Property (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyDescendantsAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, accessing XML"
  - "XML descendant axis property [Visual Basic]"
  - "descendant axis property [Visual Baisc]"
  - "XML axis [Visual Basic], descendant"
  - "XML [Visual Basic], accessing"
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# XML Descendant Axis Property (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Ermöglicht Zugriff auf folgende Nachfolgerelemente: ein <xref:System.Xml.Linq.XElement>\-Objekt, ein <xref:System.Xml.Linq.XDocument>\-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument>\-Objekten.  
  
## Syntax  
  
```  
  
object...<descendant>  
```  
  
## Teile  
 `object`  
 Erforderlich.  Ein <xref:System.Xml.Linq.XElement>\-Objekt, ein <xref:System.Xml.Linq.XDocument>\-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument> \-Objekten.  
  
 ...\<  
 Erforderlich.  Gibt den Start einer untergeordneten Achseneigenschaft an.  
  
 `descendant`  
 Erforderlich.  Name der Nachfolgerknoten, um zuzugreifen, vom Formular \[`prefix``:`\]`name`.  
  
|Bestandteil|Beschreibung|  
|-----------------|------------------|  
|`prefix`|Optional.  XML\-Namespacepräfix für den untergeordneten Knoten.  Muss ein globaler XML\-Namespace sein, der durch eine `Imports`\-Anweisung definiert wird.|  
|`name`|Erforderlich.  Der lokale Name der untergeordneten Knoten.  Weitere Informationen finden Sie unter [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Erforderlich.  Gibt das Ende einer untergeordneten Achseneigenschaft an.  
  
## Rückgabewert  
 Eine Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten.  
  
## Hinweise  
 Sie können eine untergeordnete XML\-Achseneigenschaft verwenden, um nach Name auf untergeordnete Knoten von einem <xref:System.Xml.Linq.XElement>\-Objekt oder einem <xref:System.Xml.Linq.XDocument>\-Objekt bzw. von einer Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten oder <xref:System.Xml.Linq.XDocument>\-Objekten zuzugreifen.  Verwenden Sie die XML\-`Value`\-Eigenschaft, um auf den Wert des ersten untergeordneten Knoten in der zurückgegebenen Auflistung zuzugreifen.  Weitere Informationen finden Sie unter [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Compiler konvertiert die untergeordneten Achseneigenschaften in Aufrufe an die <xref:System.Xml.Linq.XContainer.Descendants%2A>\-Methode.  
  
## XML\-Namespaces  
 Für den Namen in einer untergeordneten Achseneigenschaft können nur XML\-Namespaces verwendet werden, die mit der `Imports`\-Anweisung global deklariert wurden.  Es können keine XML\-Namespaces verwendet werden, die lokal innerhalb von XML\-Elementliteralen deklariert wurden.  Weitere Informationen finden Sie unter [Imports Statement \(XML Namespace\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie auf den Wert des ersten untergeordneten Knotens mit dem Namen `name` und die Werte aller untergeordneten Knoten mit dem Namen `phone` aus dem `contacts`\-Objekt zugegriffen wird.  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML\-Namespacepräfix.  Anschließend wird das Namespacepräfix verwendet, um ein XML\-Literal zu erstellen und auf den ersten Wert des untergeordneten Knotens mit dem qualifizierten Namen `ns:name` zuzugreifen.  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Name: Patrick Hines`  
  
## Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)