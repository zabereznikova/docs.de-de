---
title: 'Vorgehensweise: Zugreifen auf untergeordnete XML-Elemente'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 994249801eecc2984947efac9712df0047f076a4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392817"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Gewusst wie: Zugriff auf untergeordnete XML-Elemente (Visual Basic)
Dieses Beispiel zeigt, wie Sie mithilfe einer untergeordneten Achsen Eigenschaft auf alle untergeordneten XML-Elemente zugreifen können, die einen angegebenen Namen in einem XML-Element aufweisen. Insbesondere wird die-Eigenschaft verwendet <xref:System.Xml.Linq.XElement.Value%2A> , um den Wert des ersten Elements in der Auflistung zu erhalten, das von der Eigenschaft der untergeordneten `name` Achse zurückgegeben wird. Die untergeordnete `name` Achsen Eigenschaft ruft alle untergeordneten `phone` Elemente mit dem Namen im- `contact` Objekt ab. In diesem Beispiel wird auch die Eigenschaft untergeordnete `phone` Achse verwendet, um auf alle untergeordneten Elemente mit dem Namen zuzugreifen `phone` , die im-Objekt enthalten sind `contact`  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [XML Child Axis Property](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [XML-Value-Eigenschaft](../../../language-reference/xml-axis/xml-value-property.md)
- [Zugreifen auf XML in Visual Basic](accessing-xml.md)
- [XML](index.md)
