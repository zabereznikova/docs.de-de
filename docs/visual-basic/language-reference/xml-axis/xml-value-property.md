---
title: "XML Value Property (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyExtensionValue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Value property [Visual Basic]"
  - "Visual Basic code, accessing XML"
  - "XML axis [Visual Basic], Value"
  - "XML Value property [Visual Basic]"
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# XML Value Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Stellt den Zugriff auf den Wert des ersten Elements einer Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten bereit.  
  
## Syntax  
  
```  
  
object.Value  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`object`|Erforderlich.  Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten.|  
  
## Rückgabewert  
 Ein `String`, der den Wert des ersten Elements der Auflistung enthält, bzw. bei einer leeren Auflistung `Nothing`.  
  
## Hinweise  
 Mit der <xref:System.Xml.Linq.XElement.Value%2A>\-Eigenschaft erhalten Sie leicht Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten.  Diese Eigenschaft überprüft zuerst, ob die Auflistung mindestens ein Objekt enthält.  Wenn die Auflistung leer ist, gibt diese Eigenschaft `Nothing` zurück.  Andernfalls gibt diese Eigenschaft den Wert der <xref:System.Xml.Linq.XElement.Value%2A>\-Eigenschaft des ersten Elements der Auflistung zurück.  
  
> [!NOTE]
>  Wenn Sie mit dem '@'\-Bezeichner auf den Wert eines XML\-Attributs zugreifen, wird der Wert des Attributs als `String` zurückgegeben, und Sie müssen die <xref:System.Xml.Linq.XAttribute.Value%2A>\-Eigenschaft nicht explizit angeben.  
  
 Für den Zugriff auf andere Elemente in einer Auflistung können Sie die XML\-Erweiterungsindexereigenschaft verwenden.  Weitere Informationen finden Sie unter [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).  
  
## Vererbung  
 Die meisten Benutzer müssen <xref:System.Collections.Generic.IEnumerable%601> nicht implementieren und können diesen Abschnitt daher ignorieren.  
  
 Die <xref:System.Xml.Linq.XElement.Value%2A>\-Eigenschaft ist eine Erweiterungseigenschaft für Typen, die `IEnumerable(Of XElement)` implementieren.  Die Bindung dieser Erweiterungseigenschaft entspricht der Bindung von Erweiterungsmethoden: Wenn ein Typ eine der Schnittstellen implementiert und eine Eigenschaft namens "Value" definiert, hat diese Eigenschaft Vorrang vor der Erweiterungseigenschaft.  Anders ausgedrückt kann diese <xref:System.Xml.Linq.XElement.Value%2A>\-Eigenschaft durch die Definition einer neuen Eigenschaft in einer Klasse, die `IEnumerable(Of XElement)` implementiert, überschrieben werden.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mit der <xref:System.Xml.Linq.XElement.Value%2A>\-Eigenschaft auf den ersten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten zugegriffen werden kann.  In diesem Beispiel wird mithilfe der untergeordneten Achseneigenschaft die Auflistung aller untergeordneten Knoten mit dem Namen `phone` abgerufen, die sich im `contact`\-Objekt befinden.  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone number: 206-555-0144`  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der Wert eines XML\-Attributs aus einer Auflistung von <xref:System.Xml.Linq.XAttribute>\-Objekten abgerufen wird.  In diesem Beispiel wird mithilfe der Attributachseneigenschaft der Wert des `type`\-Attributs für alle `phone`\-Elemente angezeigt.  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `home`  
  
 `work`  
  
## Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Collections.Generic.IEnumerable%601>   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)   
 [XML Child Axis Property](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)   
 [XML Attribute Axis Property](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)