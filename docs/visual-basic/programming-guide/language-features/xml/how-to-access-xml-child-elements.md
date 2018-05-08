---
title: 'Gewusst wie: Zugriff auf untergeordnete XML-Elemente (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 4ec7743a30b8101d813ac414a8f5164aeb6c593d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Gewusst wie: Zugriff auf untergeordnete XML-Elemente (Visual Basic)
Dieses Beispiel zeigt, wie eines untergeordneten Achseneigenschaft auf alle untergeordnete XML-Elemente, die den angegebenen Namen in ein XML-Element aufweisen. Insbesondere verwendet die <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft rufen Sie den Wert des ersten Elements in der Auflistung, die die `name` untergeordnete Achse Eigenschaft gibt. Die `name` Child Axis-Eigenschaft ruft alle untergeordneten Elemente mit dem Namen `phone` in die `contact` Objekt. Dieses Beispiel verwendet außerdem die `phone` Child Axis-Eigenschaft auf alle untergeordneten Elemente mit dem Namen `phone` enthalten sind die `contact` Objekt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 [Untergeordnete XML-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
