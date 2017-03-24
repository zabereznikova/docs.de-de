---
title: "Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 40b0e4273223093262bc54a2b13d28fc93a44c69
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)
Sie können XML-Literale kombinieren, mit eingebetteten Ausdrücken erstellen Sie ein XML-Dokument, Fragment oder Element, das zur Laufzeit erstellte Inhalte enthält. Die folgenden Beispiele veranschaulichen, wie Sie eingebettete Ausdrücke zum Auffüllen von Elementinhalt, Attribute und Elementnamen zur Laufzeit verwenden.  
  
 Die Syntax für einen eingebetteten Ausdruck lautet `<%=` `exp` `%>`, also die gleiche Syntax, [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] verwendet. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Sie können auch die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekte. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-insert-text-as-element-content"></a>Zum Einfügen von Text als Inhalt des Elements  
  
-   Das folgende Beispiel zeigt, wie Sie den Text einfügen, die in enthalten ist die `contactName` Variable zwischen den öffnenden und schließenden Name-Elementen.  
  
     [!code-vb[VbXMLSamples Nr.&39;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Zum Einfügen von Text als Attributwert  
  
-   Das folgende Beispiel zeigt, wie Sie den Text einfügen, die in enthalten ist die `phoneType` Variable als Wert für die `type` Attribut.  
  
     [!code-vb[VbXMLSamples&#40;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Zum Einfügen von Text für einen Elementnamen  
  
-   Das folgende Beispiel zeigt, wie Sie den Text einfügen, die in enthalten ist die `elementName` -Variable als den Namen eines Elements.  
  
     Elemente mit diesem Verfahren erstellen, müssen, schließen Sie sie mit der \</ > Tag.  
  
     [!code-vb[VbXMLSamples&#41;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen von XML-Literalen](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)   
 [Eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
