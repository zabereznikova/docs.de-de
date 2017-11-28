---
title: "Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bef4662d69ca7ceddeb2641cbe265d93712c5d16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)
Sie können XML-Literale kombinieren, mit eingebetteten Ausdrücken erstellen Sie eine XML-Dokument, Fragment oder Element, das zur Laufzeit erstellte Inhalte enthält. In den folgenden Beispielen wird gezeigt, wie eingebettete Ausdrücke, die zum Auffüllen von Elementinhalt, Attribute und Elementnamen zur Laufzeit verwendet wird.  
  
 Die Syntax für einen eingebetteten Ausdruck `<%=` `exp` `%>`, die die gleiche Syntax ist, [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] verwendet. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Sie können auch die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-insert-text-as-element-content"></a>Zum Einfügen von Text als Elementinhalt  
  
-   Im folgende Beispiel wird gezeigt, wie den Text einfügen, die in enthalten ist das `contactName` Variable zwischen den öffnenden und schließenden Name-Elementen.  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Zum Einfügen von Text als Attributwert  
  
-   Im folgende Beispiel wird gezeigt, wie den Text einfügen, die in enthalten ist das `phoneType` Variable als Wert für die `type` Attribut.  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Zum Einfügen von Text für den Namen eines Elements  
  
-   Im folgende Beispiel wird gezeigt, wie den Text einfügen, die in enthalten ist die `elementName` -Variable als den Namen eines Elements.  
  
     Wenn Elemente mit diesem Verfahren erstellen, müssen Sie schließen, sie mit der \</ >-Tag.  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen von XML-Literalen](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [Eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
