---
title: Erweiterungsindexereigenschaft (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 25f434a5b5f8caf013ad5f778897e4e98e3d825d
ms.lasthandoff: 03/13/2017

---
# <a name="extension-indexer-property-visual-basic"></a>Erweiterungsindexereigenschaft (Visual Basic)
Bietet Zugriff auf einzelne Elemente in einer Auflistung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
object(index)  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`object`|Erforderlich. Eine abfragbare Auflistung. D. h. eine Auflistung, die implementiert <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>|  
|(|Erforderlich. Kennzeichnet den Anfang der Indexereigenschaft.|  
|`index`|Erforderlich. Ein Ganzzahlausdruck, der die nullbasierte Position eines Elements der Auflistung angibt.|  
|)|Erforderlich. Kennzeichnet das Ende der Indexereigenschaft.|  
  
## <a name="return-value"></a>Rückgabewert  
 Das Objekt aus der angegebenen Position in der Auflistung oder `Nothing` , wenn der Index außerhalb des gültigen Bereichs liegt.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die Erweiterungsindexereigenschaft Zugriff auf einzelne Elemente in einer Auflistung verwenden. Diese Indexereigenschaft wird normalerweise für die Ausgabe der XML-Achseneigenschaften verwendet. Die XML Child und untergeordnete XML-Achseneigenschaften Auflistungen von zurückgeben <xref:System.Xml.Linq.XElement>Objekte oder ein Attributwert.</xref:System.Xml.Linq.XElement>  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert Indexer-Erweiterungseigenschaften in Aufrufe an die`ElementAtOrDefault` Methode. Im Gegensatz zu einem Array-Indexer die`ElementAtOrDefault` -Methode gibt `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt. Dieses Verhalten ist nützlich, wenn Sie die Anzahl der Elemente in einer Auflistung nicht leicht ermitteln können.  
  
 Diese Indexereigenschaft ist wie eine Erweiterungseigenschaft für Auflistungen, implementieren <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Linq.IQueryable%601>: wird nur verwendet, wenn die Auflistung nicht über einen Indexer oder eine Standardeigenschaft verfügt.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>Objekte, können Sie den XML-Code `Value` Eigenschaft.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie der Erweiterungsindexer auf den zweiten untergeordneten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> Die Auflistung erfolgt über die Child Axis-Eigenschaft, die alle untergeordneten Elemente mit dem Namen abruft `phone` in den `contact` Objekt.  
  
 [!code-vb[VbXMLSamples&#24;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
