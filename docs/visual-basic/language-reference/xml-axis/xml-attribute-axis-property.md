---
title: "XML Attribute Axis Property (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyAttributeAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "attribute axis property [Visual Basic]"
  - "Visual Basic code, accessing XML"
  - "XML attribute axis property [Visual Basic]"
  - "XML axis [Visual Basic], attribute"
  - "XML [Visual Basic], accessing"
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML Attribute Axis Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ermöglicht den Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement>\-Objekt oder auf das erste Element in einer Aufzählung von <xref:System.Xml.Linq.XElement>\-Objekten.  
  
## Syntax  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## Teile  
 `object`  
 Erforderlich.  Ein <xref:System.Xml.Linq.XElement>\-Objekt oder eine Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten.  
  
 .@  
 Erforderlich.  Kennzeichnet den Beginn eines Achseneigenschaftattributs.  
  
 \<  
 Optional.  Kennzeichnet den Beginn des Attributnamens, wenn `attribute` kein gültiger Bezeichner in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ist.  
  
 `attribute`  
 Erforderlich.  Name des Attributs, auf das zugegriffen werden soll, in der Form \[`prefix`:\]`name`.  
  
|Bestandteil|Beschreibung|  
|-----------------|------------------|  
|`prefix`|Optional.  XML\-Namespacepräfix für das Attribut.  Muss ein globaler XML\-Namespace sein, der mit einer `Imports`\-Anweisung definiert ist.|  
|`name`|Erforderlich.  Lokaler Attributname.  Weitere Informationen finden Sie unter [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Optional.  Kennzeichnet das Ende des Attributnamens, wenn `attribute` kein gültiger Bezeichner in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ist.  
  
## Rückgabewert  
 Eine Zeichenfolge mit dem Wert von `attribute`.  Wenn der Attributname nicht vorhanden ist, wird `Nothing` zurückgegeben.  
  
## Hinweise  
 Sie können mit einer XML\-Attribut Achseneigenschaft auf den Wert eines Attributs anhand des Namens aus einem <xref:System.Xml.Linq.XElement>\-Objekt oder aus dem ersten Element in einer Sammlung von <xref:System.Xml.Linq.XElement>\-Objekten zugreifen.  Sie können den Attributwert über den Namen abrufen oder ein neues Attribut zu einem Element hinzufügen, indem Sie einen neuen Namen angeben, dem der @\-Bezeichner vorangestellt ist.  
  
 Wenn Sie auf ein XML\-Attribut mit dem @\-Bezeichner verweisen, wird der Wert des Attributs als Zeichenfolge zurückgegeben, und Sie müssen die <xref:System.Xml.Linq.XAttribute.Value%2A>\-Eigenschaft nicht explizit angeben.  
  
 Die Benennungsregeln für XML\-Attribute unterscheiden sich von den Benennungsregeln für [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Bezeichner. Um auf ein XML\-Attribut zugreifen, das einen Namen hat, der kein gültiger Visual Basic\-Bezeichner ist, schließen Sie den Namen in spitzen Klammern \(\< und \>\) ein.  
  
## XML\-Namespaces  
 Für den Namen in einem Achseneigenschaftattribut können nur XML\-Namespacepräfixe verwendet werden, die mit der `Imports`\-Anweisung global deklariert wurden.  Es können keine XML\-Namespacepräfixe verwendet werden, die lokal innerhalb von XML\-Elementliteralen deklariert wurden.  Weitere Informationen finden Sie unter [Imports Statement \(XML Namespace\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie die Werte der XML\-Attribute mit dem Namen `type` aus einer Auflistung von XML\-Elementen mit dem Namen `phone` abgerufen werden.  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## Beispiel  
 Das folgenden Beispiel zeigt, wie Attribute für ein XML\-Element erstellt werden, zum einen deklarativ als Teil des XML, zum anderen auch dynamisch, indem ein Attribut zu einer Instanz eines <xref:System.Xml.Linq.XElement>\-Objekts hinzugefügt wird.  Das `type`\-Attribut wird deklarativ erstellt, und das `owne`r\-Attribut wird dynamisch erstellt.  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## Beispiel  
 Das folgende Beispiel verwendet die Syntax mit spitzen Klammern zum Abrufen des Werts des XML\-Attributs mit dem Namen `number-type`, der in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] kein gültiger Bezeichner ist.  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: work`  
  
## Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML\-Namespacepräfix.  Anschließend wird das Namespacepräfix verwendet, um ein XML\-Literal zu erstellen und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen "`ns:name`" zuzugreifen.  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: home`  
  
## Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)