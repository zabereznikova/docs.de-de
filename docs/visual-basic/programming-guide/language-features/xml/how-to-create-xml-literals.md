---
title: 'Gewusst wie: Erstellen von XML-Literalen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e5f8429b3ff02678bf8bf3e9e32bef6eb1a56831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652869"
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
