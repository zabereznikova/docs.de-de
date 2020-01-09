---
title: 'Gewusst wie: Zugriff auf XML-Nachfolgerelemente'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: cc045114c67ee2917ef672e734bc852c40d408ac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347158"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)
In diesem Beispiel wird gezeigt, wie Sie mithilfe einer Nachfolger Achsen Eigenschaft auf alle XML-Elemente zugreifen können, die über einen angegebenen Namen verfügen und in einem XML-Element enthalten sind. Insbesondere wird die `Value`-Eigenschaft verwendet, um den Wert des ersten Elements in der Auflistung zu erhalten, das die `name` Nachfolger Axis-Eigenschaft zurückgibt. Die `name` Nachfolger Achsen Eigenschaft ruft alle Elemente mit dem Namen `name` ab, die im `contacts` Objekt enthalten sind. In diesem Beispiel wird auch die `phone` nachfolgende Achsen Eigenschaft verwendet, um auf alle Nachfolger `phone` zuzugreifen, die im `contacts`-Objekt enthalten sind.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML-Nachfolger-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
