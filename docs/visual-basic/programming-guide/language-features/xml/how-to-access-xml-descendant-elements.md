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
This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element. In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns. The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object. This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML-Nachfolger-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
