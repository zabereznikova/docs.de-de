---
title: 'Gewusst wie: Zugriff auf XML-Nachfolgerelemente'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 63a094c3c2b20736f0ef6589c76d53b7cc96b29a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332312"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)
In diesem Beispiel wird gezeigt, wie Sie mithilfe einer Nachfolger Achsen Eigenschaft auf alle XML-Elemente zugreifen können, die über einen angegebenen Namen verfügen und in einem XML-Element enthalten sind. Insbesondere wird die `Value`-Eigenschaft verwendet, um den Wert des ersten Elements in der Auflistung zu erhalten, das die `name` Nachfolger Axis-Eigenschaft zurückgibt. Die `name` Nachfolger Achsen Eigenschaft ruft alle Elemente mit dem Namen `name` ab, die im `contacts` Objekt enthalten sind. In diesem Beispiel wird auch die `phone` nachfolgende Achsen Eigenschaft verwendet, um auf alle Nachfolger `phone` zuzugreifen, die im `contacts`-Objekt enthalten sind.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML-Nachfolger-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
