---
title: 'Vorgehensweise: Erstellen von XML-Literalen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 836ec4390e7675effe57c75c79768272d66925a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836862"
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Vorgehensweise: Erstellen von XML-Literalen (Visual Basic)
Sie können eine XML-Dokument, Fragment oder Element direkt im Code erstellen, mit einem XML-literal. In die Beispielen in diesem Thema wird veranschaulicht, wie ein XML-Element zu erstellen, die über drei untergeordnete Elemente verfügt wie ein XML-Dokument erstellt.  
  
 Sie können auch die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.  
  
### <a name="to-create-an-xml-element"></a>Erstellen Sie ein XML-element  
  
-   Erstellen Sie die XML-Inline, indem Sie mit der XML-Literalen Syntax, die die tatsächlichen XML-Syntax identisch ist.  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     Führen Sie den Code aus. Die Ausgabe dieses Codes lautet:  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>Zum Erstellen eines XML-Dokuments  
  
-   Die XML-Dokument Inline zu erstellen. Der folgende Code erstellt eine XML-Dokument mit Literalen Syntax, eine XML-Deklaration, eine verarbeitungsanweisung, einen Kommentar und ein Element, ein anderes Element enthält.  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     Führen Sie den Code aus. Die Ausgabe dieses Codes lautet:  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>Siehe auch

- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
