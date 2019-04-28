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
ms.openlocfilehash: a02c482db81d9d76752cfe66a292dc57c48b2acb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698901"
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
|`object`|Erforderlich. Eine abfragbare Auflistung. D. h. einer Auflistung mit Implementierung <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>.|  
|(|Erforderlich. Kennzeichnet den Anfang der Indexereigenschaft.|  
|`index`|Erforderlich. Ein ganzzahliger Ausdruck, der die nullbasierte Position eines Elements der Auflistung angibt.|  
|)|Erforderlich. Kennzeichnet das Ende der Indexereigenschaft.|  
  
## <a name="return-value"></a>Rückgabewert  
 Das Objekt aus der angegebenen Position in der Auflistung oder `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die Erweiterungseigenschaft für Indexer verwenden, Zugriff auf einzelne Elemente in einer Auflistung. Diese Indexereigenschaft wird in der Regel für die Ausgabe der XML-Achseneigenschaften verwendet. Die XML-untergeordneten und untergeordnete XML-Achseneigenschaften Auflistungen von zurückgeben <xref:System.Xml.Linq.XElement> Objekte oder einen Attributwert.  
  
 Visual Basic-Compiler konvertiert die Erweiterungseigenschaften für Indexer in Aufrufe an die `ElementAtOrDefault` Methode. Im Gegensatz zu einem Arrayindexer der `ElementAtOrDefault` Methodenrückgabe `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt. Dies ist hilfreich, wenn Sie einfach die Anzahl der Elemente in einer Auflistung nicht bestimmen können.  
  
 Diese Indexereigenschaft wird wie eine Erweiterungseigenschaft für Auflistungen, implementieren <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>: Es wird nur verwendet, wenn die Auflistung nicht über einen Indexer oder eine Default-Eigenschaft verfügt.  
  
 Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XAttribute> Objekte aufweist, können Sie den XML-Code `Value` Eigenschaft. Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der Erweiterungsindexer auf den zweiten untergeordneten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte. Die Auflistung erfolgt mithilfe einer untergeordneten Achseneigenschaft, in dem alle untergeordneten Elemente, die mit dem Namen abgerufen werden, `phone` in die `contact` Objekt.  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
