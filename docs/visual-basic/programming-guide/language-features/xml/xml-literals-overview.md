---
title: Übersicht zu XML-Literalen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1bc3bed1a7046e6f3c31828fbf17be877e66f146
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="xml-literals-overview-visual-basic"></a>Übersicht zu XML-Literalen (Visual Basic)
Ein *XML-Literal* können Sie XML direkt in Visual Basic-Code integrieren. Die XML-literal-Syntax stellt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte und ähnelt der XML 1.0-Syntax. Dies erleichtert die XML-Elementen und Dokumenten programmgesteuert erstellt werden, da der Code dieselbe Struktur auf wie die endgültigen XML hat.  
  
 Visual Basic kompiliert XML-Literale in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Stellt ein einfaches Objektmodell zum Erstellen und Bearbeiten von XML, und dieses Modell nahtlose Integration in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.  
  
 Sie können einen Visual Basic-Ausdruck in einem XML-literal einbetten. Zur Laufzeit erstellt die Anwendung eine [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt für jedes Literal, die Werte von eingebetteten Ausdrücken einbinden. Dadurch können Sie die dynamischen Inhalt in einem XML-literal angeben. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Weitere Informationen zu den Unterschieden zwischen der XML-literal-Syntax und die XML 1.0-Syntax finden Sie unter [XML-Literale und XML 1.0-Spezifikation](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Einfache Literale  
 Sie erstellen eine [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic-Code durch eingeben oder Einfügen von gültigen XML-Objekt. Gibt ein XML-Elementliteral ein <xref:System.Xml.Linq.XElement> Objekt. Weitere Informationen finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML-Literale und XML 1.0-Spezifikation](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). Das folgende Beispiel erstellt ein XML-Element, das mehrere untergeordnete Elemente verfügt.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Sie können ein XML-Dokument erstellen, indem ein XML-literal mit ab `<?xml version="1.0"?>`, wie im folgenden Beispiel gezeigt. Gibt ein XML-Dokumentliteral ein <xref:System.Xml.Linq.XDocument> Objekt. Weitere Informationen finden Sie unter [XML-Dokument-Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  Die Syntax der XML-Literale in Visual Basic ist nicht identisch mit der Syntax in der XML 1.0-Spezifikation. Weitere Informationen finden Sie unter [XML-Literale und XML 1.0-Spezifikation](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Zeilenfortsetzung  
 Ein XML-Literal kann mehrere Zeilen umfassen, ohne das Zeilenfortsetzungszeichen (die Leerzeichen-Unterstrich-EINGABETASTE-Sequenz). Dies erleichtert es, XML-Literalen in Code mit XML-Dokumenten verglichen werden soll.  
  
 Der Compiler behandelt Zeilenfortsetzungszeichen als Teil eines XML-literal. Daher sollten Sie die Leerzeichen-Unterstrich-EINGABETASTE Sequenz verwenden, nur, wenn es gehört der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt.  
  
 Allerdings ist Sie Zeilenfortsetzungszeichen erforderlich, wenn Sie einen mehrzeiligen Ausdruck in einem eingebetteten Ausdruck haben. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Einbetten von Abfragen in XML-Literalen  
 Sie können eine Abfrage in einem eingebetteten Ausdruck verwenden. Wenn Sie dies tun, werden die Elemente, die von der Abfrage zurückgegebenen XML-Elements hinzugefügt. Dadurch können Sie die dynamische Inhalte, z. B. das Ergebnis der Abfrage des Benutzers, um ein XML-literal hinzufügen.  
  
 Der folgende Code verwendet beispielsweise eine eingebettete Abfrage zum Erstellen von XML-Elementen aus den Elementen der `phoneNumbers2` array erstellt und dann diese Elemente als untergeordnete Elemente des hinzufügen `contact2`.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Der Compiler erstellt wie Objekte von XML-Literalen  
 Visual Basic-Compiler übersetzt XML-Literale in Aufrufe in die entsprechende [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Konstruktoren zum Erstellen der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt. Z. B. Visual Basic-Compiler wird im folgenden Codebeispiel wird in einen Aufruf übersetzt die <xref:System.Xml.Linq.XProcessingInstruction> Konstruktor für die XML-Version-Anweisung aufruft, um die <xref:System.Xml.Linq.XElement> Konstruktor für die `<contact>`, `<name>`, und `<phone>` Elemente und Aufrufe an die <xref:System.Xml.Linq.XAttribute> Konstruktor für die `type` Attribut. Insbesondere anhand der Attribute im folgenden Beispiel, das Visual Basic-Compiler Ruft die <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> zweimal Konstruktor. Die erste übergeben den Wert `type` für die `name` -Parameter und den Wert `home` für die `value` Parameter. Die zweite übergeben den Wert auch `type` für die `name` Parameter, aber der Wert `work` für die `value` Parameter.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md)
