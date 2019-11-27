---
title: Erweiterungsindexereigenschaft
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 5f91dc8a6b1a0d82daa4891cf826c16e2716839f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352702"
---
# <a name="extension-indexer-property-visual-basic"></a>Erweiterungsindexereigenschaft (Visual Basic)
Bietet Zugriff auf einzelne Elemente in einer Auflistung.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`object`|Erforderlich Eine abfragbare Auflistung. Das heißt, eine Auflistung, die <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>implementiert.|  
|(|Erforderlich Gibt den Anfang der Indexer-Eigenschaft an.|  
|`index`|Erforderlich Ein ganzzahliger Ausdruck, der die null basierte Position eines Elements der Auflistung angibt.|  
|)|Erforderlich Bezeichnet das Ende der Indexer-Eigenschaft.|  
  
## <a name="return-value"></a>Rückgabewert  
 Das-Objekt aus der angegebenen Position in der Auflistung oder `Nothing`, wenn der Index außerhalb des gültigen Bereichs liegt.  
  
## <a name="remarks"></a>Hinweise  
 Mit der Eigenschaft Erweiterungsindexer können Sie auf einzelne Elemente in einer Auflistung zugreifen. Diese Indexer-Eigenschaft wird in der Regel in der Ausgabe von XML-Achsen Eigenschaften verwendet. Die Eigenschaften der untergeordneten XML-und XML-Nachfolger Achse geben Auflistungen von <xref:System.Xml.Linq.XElement> Objekten oder einem Attribut Wert zurück.  
  
 Der Visual Basic-Compiler konvertiert Erweiterungs Indexer-Eigenschaften in Aufrufe der `ElementAtOrDefault`-Methode. Anders als bei einem Arrayindexer gibt die `ElementAtOrDefault`-Methode `Nothing` zurück, wenn der Index außerhalb des gültigen Bereichs liegt. Dieses Verhalten ist nützlich, wenn Sie die Anzahl der Elemente in einer Auflistung nicht einfach ermitteln können.  
  
 Diese Indexer-Eigenschaft entspricht einer Erweiterungs Eigenschaft für Auflistungen, die <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>implementieren: Sie wird nur verwendet, wenn die Auflistung keinen Indexer oder keine Standard Eigenschaft aufweist.  
  
 Um auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement>-oder <xref:System.Xml.Linq.XAttribute> Objekten zuzugreifen, können Sie die XML-`Value`-Eigenschaft verwenden. Weitere Informationen finden Sie unter [XML-Wert Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der Erweiterungsindexer zum Zugreifen auf den zweiten untergeordneten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten verwendet wird. Der Zugriff auf die Auflistung erfolgt mithilfe der untergeordneten Achsen Eigenschaft, die alle untergeordneten Elemente mit dem Namen `phone` im `contact`-Objekt abruft.  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
