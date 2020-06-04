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
ms.openlocfilehash: c91061d49e22e648b7bf75a812071b352793abcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401341"
---
# <a name="extension-indexer-property-visual-basic"></a>Erweiterungsindexereigenschaft (Visual Basic)
Bietet Zugriff auf einzelne Elemente in einer Auflistung.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`object`|Erforderlich. Eine abfragbare Auflistung. Das heißt, eine Auflistung, die <xref:System.Collections.Generic.IEnumerable%601> oder implementiert <xref:System.Linq.IQueryable%601> .|  
|(|Erforderlich. Gibt den Anfang der Indexer-Eigenschaft an.|  
|`index`|Erforderlich. Ein ganzzahliger Ausdruck, der die null basierte Position eines Elements der Auflistung angibt.|  
|)|Erforderlich. Bezeichnet das Ende der Indexer-Eigenschaft.|  
  
## <a name="return-value"></a>Rückgabewert  
 Das Objekt aus der angegebenen Position in der Auflistung oder, `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt.  
  
## <a name="remarks"></a>Bemerkungen  
 Mit der Eigenschaft Erweiterungsindexer können Sie auf einzelne Elemente in einer Auflistung zugreifen. Diese Indexer-Eigenschaft wird in der Regel in der Ausgabe von XML-Achsen Eigenschaften verwendet. Die Eigenschaften der untergeordneten XML-und XML-Nachfolger Achse geben Auflistungen von <xref:System.Xml.Linq.XElement> Objekten oder einen Attribut Wert zurück.  
  
 Der Visual Basic-Compiler konvertiert Erweiterungs Indexer-Eigenschaften in Aufrufe der- `ElementAtOrDefault` Methode. Anders als bei einem Arrayindexer `ElementAtOrDefault` gibt die Methode zurück, `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt. Dieses Verhalten ist nützlich, wenn Sie die Anzahl der Elemente in einer Auflistung nicht einfach ermitteln können.  
  
 Diese Indexer-Eigenschaft ist wie eine Erweiterungs Eigenschaft für Auflistungen, die <xref:System.Collections.Generic.IEnumerable%601> oder implementieren <xref:System.Linq.IQueryable%601> : Sie wird nur verwendet, wenn die Auflistung keinen Indexer oder keine Standard Eigenschaft aufweist.  
  
 Um auf den Wert des ersten Elements in einer Auflistung von- <xref:System.Xml.Linq.XElement> Objekten oder- <xref:System.Xml.Linq.XAttribute> Objekten zuzugreifen, können Sie die XML- `Value` Eigenschaft verwenden. Weitere Informationen finden Sie unter [XML-Wert Eigenschaft](xml-value-property.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der Erweiterungsindexer zum Zugreifen auf den zweiten untergeordneten Knoten in einer Auflistung von-Objekten verwendet wird <xref:System.Xml.Linq.XElement> . Der Zugriff auf die Auflistung erfolgt mithilfe der untergeordneten Achsen Eigenschaft, die alle untergeordneten Elemente mit dem Namen im-Objekt abruft `phone` `contact` .  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.Linq.XElement>
- [XML-Achseneigenschaften](index.md)
- [XML-Literale](../xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [XML-Value-Eigenschaft](xml-value-property.md)
