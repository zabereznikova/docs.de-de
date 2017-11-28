---
title: 'Gewusst wie: Zugriff auf untergeordnete XML-Elemente (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d3a708b787ad38f08d4673d4003db839f6cf6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
