---
title: 'Gewusst wie: Erstellen von XML-Literalen (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce1bf763529b436158c2d74811c4938182166f92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Gewusst wie: Erstellen von XML-Literalen (Visual Basic)
Sie können eine XML-Dokument, Fragment oder Element direkt im Code erstellen, mit einem XML-literal. In den Beispielen in diesem Thema wird veranschaulicht, wie ein XML-Element zu erstellen, die über drei untergeordnete Elemente verfügt, wie ein XML-Dokument erstellt.  
  
 Sie können auch die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.  
  
### <a name="to-create-an-xml-element"></a>So erstellen ein XML-element  
  
-   Erstellen Sie die XML-Inline mit der XML-literal Syntax, die die tatsächlichen XML-Syntax entspricht.  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     Führen Sie den Code ein. Die Ausgabe dieses Codes lautet:  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>Beim Erstellen des XML-Dokuments  
  
-   Erstellen der XML-Dokument zu ermöglichen. Der folgende Code erstellt ein XML-Dokument, dessen literal Syntax, eine XML-Deklaration, eine verarbeitungsanweisung, einen Kommentar und ein Element, das ein anderes Element enthält.  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     Führen Sie den Code ein. Die Ausgabe dieses Codes lautet:  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>Siehe auch  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
