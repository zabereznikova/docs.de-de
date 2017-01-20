---
title: "Extension Indexer Property (Visual Basic) | Microsoft Docs"
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
  - "vb.XmlPropertyExtensionIndexer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, accessing XML"
  - "XML extension indexer [Visual Basic]"
  - "extension indexer [Visual Basic]"
  - "XML [Visual Basic], accessing"
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Extension Indexer Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Bietet Zugriff auf einzelne Elemente in einer Auflistung.  
  
## Syntax  
  
```  
  
object(index)  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`object`|Erforderlich.  Eine abfragbare Auflistung.  Dabei handelt es sich um eine Auflistung, die <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601> implementiert.|  
|\(|Erforderlich.  Kennzeichnet den Anfang der Indexereigenschaft.|  
|`index`|Erforderlich.  Ein ganzzahliger Ausdruck, der die nullbasierte Position eines Elements der Auflistung angibt.|  
|\)|Erforderlich.  Kennzeichnet das Ende der Indexereigenschaft.|  
  
## Rückgabewert  
 Das Objekt an der angegebenen Position in der Auflistung oder `Nothing`, wenn der Index außerhalb des Bereichs liegt.  
  
## Hinweise  
 Mit der Erweiterungsindexereigenschaft können Sie auf einzelne Elemente in einer Auflistung zugreifen.  Diese Indexereigenschaft wird in der Regel für Ausgaben von XML\-Achseneigenschaften verwendet.  Die Achseneigenschaften des untergeordneten und des nachfolgenden XML\-Elements geben Auflistungen von <xref:System.Xml.Linq.XElement>\-Objekten oder einen Attributwert zurück.  
  
 Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler konvertiert Indexer\-Erweiterungseigenschaften in Aufrufe der `ElementAtOrDefault`\-Methode. Im Gegensatz zu einem Array\-Indexer gibt die `ElementAtOrDefault`\-Methode `Nothing` zurück, wenn der Index außerhalb des zulässigen Bereichs ist.  Dieses Verhalten ist nützlich, wenn Sie die Anzahl von Elementen in einer Auflistung nicht leicht ermitteln können.  
  
 Diese Indexereigenschaft ist vergleichbar mit der Erweiterungseigenschaft für Auflistungen, die <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601> implementieren: Sie wird nur verwendet, wenn die Auflistung nicht über einen Indexer oder eine Standardeigenschaft verfügt.  
  
 Um auf den Wert des ersten Elements einer Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten oder <xref:System.Xml.Linq.XAttribute>\-Objekten zuzugreifen, können Sie die `Value`\-Eigenschaft von XML verwenden.  Weitere Informationen finden Sie unter [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der Erweiterungsindexer für den Zugriff auf den zweiten untergeordneten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten verwendet werden kann.  Der Zugriff auf die Auflistung erfolgt mithilfe der untergeordneten Achseneigenschaft, die alle untergeordneten Elemente mit dem Namen `phone` im `contact`\-Objekt abruft.  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Second phone number: 425-555-0145`  
  
## Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)