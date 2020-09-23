---
title: 'Vorgehensweise: Zugreifen auf XML-Nachfolgerelemente'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: dcbaf1f9022d86f40a90ef6a1e0033f627caeef2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058208"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)

In diesem Beispiel wird gezeigt, wie Sie mithilfe einer Nachfolger Achsen Eigenschaft auf alle XML-Elemente zugreifen können, die über einen angegebenen Namen verfügen und in einem XML-Element enthalten sind. Insbesondere wird die-Eigenschaft verwendet `Value` , um den Wert des ersten Elements in der Auflistung zu erhalten, das von der Eigenschaft der nachfolgenden `name` Achse zurückgegeben wird. Die Eigenschaft der nachfolgenden `name` Achse ruft alle Elemente mit dem Namen ab `name` , die im-Objekt enthalten sind `contacts` . In diesem Beispiel wird auch die Eigenschaft für die nachfolgende `phone` Achse verwendet, um auf alle im-Objekt enthaltenen Nachfolger Elemente mit dem Namen zuzugreifen `phone` `contacts` .  
  
## <a name="example"></a>Beispiel  

 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  

 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML Descendant Axis Property](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [XML-Value-Eigenschaft](../../../language-reference/xml-axis/xml-value-property.md)
- [Zugreifen auf XML in Visual Basic](accessing-xml.md)
- [XML](index.md)
