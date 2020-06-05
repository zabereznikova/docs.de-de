---
title: 'Vorgehensweise: Erstellen von XML-Literalen'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 61b138c0851c747ed30eedc10cb882cc3b03c4d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392609"
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Gewusst wie: Erstellen von XML-Literalen (Visual Basic)
Sie können ein XML-Dokument,-Fragment oder-Element direkt im Code mithilfe eines XML-Literals erstellen. In den Beispielen in diesem Thema wird gezeigt, wie ein XML-Element erstellt wird, das über drei untergeordnete Elemente verfügt, und wie ein XML-Dokument erstellt wird.  
  
 Sie können auch die- [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs verwenden, um-Objekte zu erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] . Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.  
  
### <a name="to-create-an-xml-element"></a>So erstellen Sie ein XML-Element  
  
- Erstellen Sie die XML-Datei Inline mithilfe der XML-Literalsyntax, die der eigentlichen XML-Syntax entspricht.  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     Führen Sie den Code aus. Die Ausgabe dieses Codes lautet wie folgt:  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>So erstellen Sie ein XML-Dokument  
  
- Erstellen Sie das XML-Dokument Inline. Der folgende Code erstellt ein XML-Dokument, das eine Literalsyntax, eine XML-Deklaration, eine Verarbeitungsanweisung, einen Kommentar und ein Element mit einem anderen Element enthält.  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     Führen Sie den Code aus. Die Ausgabe dieses Codes lautet wie folgt:  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>Weitere Informationen

- [XML](index.md)
- [Erstellen von XML in Visual Basic](creating-xml.md)
- [XML-Elementliteral](../../../language-reference/xml-literals/xml-element-literal.md)
- [XML-Dokumentliteral](../../../language-reference/xml-literals/xml-document-literal.md)
