---
title: "How to: Embed Expressions in XML Literals (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "embedded expressions [Visual Basic]"
  - "XML literals [Visual Basic], embedded expressions"
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Embed Expressions in XML Literals (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können XML\-Literale mit eingebetteten Ausdrücken kombinieren, um ein XML\-Dokument, \-Fragment oder \-Element zu erstellen, das zur Laufzeit erstellten Inhalt enthält.  In den folgenden Beispielen wird gezeigt, wie eingebettete Ausdrücke verwendet werden, um den Elementinhalt, Attribute und Elementnamen zur Laufzeit zu füllen.  
  
 Die Syntax für einen eingebetteten Ausdruck lautet `<%=` `exp` `%>`. Sie stimmt mit der in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] verwendeten Syntax überein. Weitere Informationen finden Sie unter [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Sie können auch die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]\-APIs verwenden, um [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]\-Objekte zu erstellen.  Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.  
  
## Arbeitsschritte  
  
#### So fügen Sie Text als Elementinhalt ein  
  
-   Im folgenden Beispiel wird gezeigt, wie der in der `contactName`\-Variable enthaltene Text zwischen dem ersten und dem letzten Nameelement eingefügt wird.  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     Dieses Beispiel erzeugt folgende Ausgabe:  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### So fügen Sie Text als Attributwert ein  
  
-   Im folgenden Beispiel wird gezeigt, wie der in der `phoneType`\-Variable enthaltene Text als Wert des `type`\-Attributs eingefügt wird.  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     Dieses Beispiel erzeugt folgende Ausgabe:  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### So fügen Sie Text für einen Elementnamen ein  
  
-   Im folgenden Beispiel wird gezeigt, wie der in der `elementName`\-Variable enthaltene Text als Name eines Elements eingefügt wird.  
  
     Wenn Sie Elemente auf diese Weise erstellen, müssen Sie sie mit dem \<\/\>\-Tag schließen.  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     Dieses Beispiel erzeugt folgende Ausgabe:  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## Siehe auch  
 [How to: Create XML Literals](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)   
 [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)