---
title: 'Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 6d41844b540631df96740ce56818c125cf85e928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648485"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)
Dieses Beispiel zeigt, wie Sie eine descendant-Achse-Eigenschaft verwenden, um Zugriff auf alle XML-Elemente, die einen angegebenen Namen aufweisen und in ein XML-Element enthalten sind. Insbesondere verwendet die `Value` Eigenschaft, um den Wert des ersten Elements in der Auflistung abrufen, die die `name` -Achseneigenschaft zurückgibt. Die `name` Nachfolgerachseneigenschaft Ruft alle Elemente, die mit dem Namen `name` enthalten sind die `contacts` Objekt. Dieses Beispiel verwendet außerdem die `phone` Nachfolgerachseneigenschaft auf allen untergeordneten Elementen mit dem Namen `phone` enthalten sind die `contacts` Objekt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [XML-Nachfolger-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
