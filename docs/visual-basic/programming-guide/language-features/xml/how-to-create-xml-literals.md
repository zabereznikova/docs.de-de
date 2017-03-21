---
title: 'Gewusst wie: Erstellen von XML-Literalen (Visual Basic) | Microsoft-Dokumentation'
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
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 17
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
ms.openlocfilehash: 72d96f36fc17f32ac3ee3ea97175f112fcd21681
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-xml-literals-visual-basic"></a>Gewusst wie: Erstellen von XML-Literalen (Visual Basic)
Sie können ein XML-Dokument, Fragment oder das Element direkt im Code erstellen, mit einem XML-literal. In den Beispielen in diesem Thema veranschaulichen ein XML-Element zu erstellen, die drei untergeordnete Elemente verfügt, und wie Sie ein XML-Dokument zu erstellen.  
  
 Sie können auch die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekte. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>  
  
### <a name="to-create-an-xml-element"></a>Erstellen Sie ein XML-element  
  
-   Erstellen Sie XML Inline, indem die XML-Literalen Syntax verwenden, die die tatsächlichen XML-Syntax entspricht.  
  
     [!code-vb[VbXMLSamples&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     Führen Sie den Code. Die Ausgabe dieses Codes lautet:  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>Zum Erstellen eines XML-Dokuments  
  
-   Erstellen Sie die XML-Dokument Inline. Der folgende Code erstellt ein XML-Dokument mit Literalen Syntax, eine XML-Deklaration, eine verarbeitungsanweisung, einen Kommentar und ein Element, ein anderes Element enthält.  
  
     [!code-vb[VbXMLSamples&#30;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     Führen Sie den Code. Die Ausgabe dieses Codes lautet:  
  
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
