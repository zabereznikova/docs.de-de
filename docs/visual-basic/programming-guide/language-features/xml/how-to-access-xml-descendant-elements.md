---
title: 'Vorgehensweise: Zugriff XML-Nachfolgerelemente (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: bfbf849bd296f639f03580346e4a9c52ce000abd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832215"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Vorgehensweise: Zugriff XML-Nachfolgerelemente (Visual Basic)
Dieses Beispiel zeigt, wie Sie mit einer untergeordneten Achseneigenschaft auf alle XML-Elemente, die einen angegebenen Namen aufweisen und in ein XML-Element enthalten sind. Insbesondere verwendet die `Value` Eigenschaft, um dem Wert des ersten Elements in der Sammlung abrufen, die die `name` -Achseneigenschaft zurückgibt. Die `name` Nachfolgerachseneigenschaft Ruft alle Elemente, die mit dem Namen `name` enthalten sind die `contacts` Objekt. Dieses Beispiel verwendet auch die `phone` Nachfolgerachseneigenschaft auf alle Nachfolger namens `phone` enthalten sind die `contacts` Objekt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML-Nachfolger-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
