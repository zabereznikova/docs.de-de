---
title: Erweiterungsindexereigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: a7718a4aa85a000d0c83e8c9556a448ceaf13c82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603469"
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
|`object`|Erforderlich. Eine abfragbare Sammlung. D. h. eine Auflistung mit Implementierung <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>.|  
|(|Erforderlich. Kennzeichnet den Anfang der Indexereigenschaft.|  
|`index`|Erforderlich. Ein ganzzahliger Ausdruck, der die nullbasierte Position eines Elements der Auflistung angibt.|  
|)|Erforderlich. Kennzeichnet das Ende der Indexereigenschaft.|  
  
## <a name="return-value"></a>Rückgabewert  
 Das Objekt aus der angegebenen Position in der Auflistung oder `Nothing` , wenn der Index außerhalb des gültigen Bereichs liegt.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die Erweiterungsindexereigenschaft Zugriff auf einzelne Elemente in einer Auflistung verwenden. Diese Indexereigenschaft wird in der Regel auf die Ausgabe der XML-Achseneigenschaften verwendet. Die untergeordnete XML- und die untergeordnete XML-Achseneigenschaften zurückgeben Auflistungen von <xref:System.Xml.Linq.XElement> Objekte oder ein Attributwert.  
  
 Visual Basic-Compiler konvertiert Indexer Erweiterungseigenschaften in Aufrufe an die `ElementAtOrDefault` Methode. Im Gegensatz zu einer konstantenarrayindizierung der `ElementAtOrDefault` -Methode zurückkehrt `Nothing` , wenn der Index außerhalb des gültigen Bereichs liegt. Dieses Verhalten ist nützlich, wenn Sie einfach die Anzahl der Elemente in einer Auflistung nicht bestimmen können.  
  
 Diese Indexereigenschaft ist wie eine Erweiterungseigenschaft für Auflistungen, implementieren <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>: wird verwendet, nur, wenn die Auflistung nicht über einen Indexer oder eine Standardeigenschaft verfügt.  
  
 Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XAttribute> Objekte aufweist, können Sie den XML-Code `Value` Eigenschaft. Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die Erweiterung Indexer zu verwenden, auf den zweiten untergeordneten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte. Die Auflistung erfolgt mithilfe der untergeordneten Achseneigenschaft, der alle untergeordneten Elemente mit dem Namen abgerufen `phone` in die `contact` Objekt.  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>  
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
