---
title: 'Vorgehensweise: Zugriff auf XML-untergeordnete Elemente (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 874c7490e451d64bf50e25934ea43a9b928ddab9
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980554"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Vorgehensweise: Zugriff auf XML-untergeordnete Elemente (Visual Basic)
In diesem Beispiel zeigt, wie eines untergeordneten Achseneigenschaft auf alle untergeordneten XML-Elemente, die einen angegebenen Namen in ein XML-Element aufweisen. Insbesondere verwendet die <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft, um dem Wert des ersten Elements in der Sammlung abrufen, die die `name` untergeordnete Achse-Eigenschaft gibt. Die `name` Child Axis-Eigenschaft ruft alle untergeordneten Elemente, die mit dem Namen `phone` in die `contact` Objekt. Dieses Beispiel verwendet auch die `phone` Child Axis-Eigenschaft auf alle untergeordneten Elemente, die mit dem Namen `phone` enthalten sind die `contact` Objekt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [Untergeordnete XML-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
