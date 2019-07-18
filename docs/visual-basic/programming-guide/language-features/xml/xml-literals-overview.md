---
title: Übersicht zu XML-Literalen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: a7b70669131ae35135088418e4b33b3ae289d322
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761753"
---
# <a name="xml-literals-overview-visual-basic"></a>Übersicht zu XML-Literalen (Visual Basic)
Ein *XML-Literal* können Sie XML direkt in Visual Basic-Code integriert. Stellt die XML-Literalsyntax [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte, und es ähnelt der XML 1.0-Syntax. Dies erleichtert die XML-Elementen und Dokumenten programmgesteuert erstellt werden, da der Code die gleiche Struktur wie der endgültige XML-Code aufweist.  
  
 Visual Basic kompiliert XML-Literale in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet ein einfaches Objektmodell zum Erstellen und Bearbeiten von XML, und dieses Modell integriert auch [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.  
  
 Sie können einen Visual Basic-Ausdruck in einem XML-literal einbetten. Zur Laufzeit erstellt die Anwendung eine [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] -Objekt für jedes Literal, integrieren die Werte von eingebetteten Ausdrücken. Dadurch können Sie die dynamischen Inhalt in einem XML-literal angeben. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Weitere Informationen zu den Unterschieden zwischen der XML-Literalen Syntax und die XML 1.0-Syntax finden Sie unter [XML-Literale und der XML 1.0-Spezifikation](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Einfache Literale  
 Sie erstellen eine [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekts in Visual Basic-Code durch eingeben oder Einfügen von gültigen XML. Gibt ein XML-Elementliteral ein <xref:System.Xml.Linq.XElement> Objekt. Weitere Informationen finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML-Literale und der XML 1.0-Spezifikation](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). Das folgende Beispiel erstellt ein XML‑Element, das mehrere untergeordnete Elemente verfügt.  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Sie können ein XML-Dokument erstellen, indem ein XML-literal mit ab `<?xml version="1.0"?>`, wie im folgenden Beispiel gezeigt. Gibt ein XML-Dokumentliteral ein <xref:System.Xml.Linq.XDocument> Objekt. Weitere Informationen finden Sie unter [XML-Dokument-Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
>  Die XML-Literale-Syntax in Visual Basic ist nicht identisch mit der Syntax in der XML 1.0-Spezifikation. Weitere Informationen finden Sie unter [XML-Literale und der XML 1.0-Spezifikation](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Zeilenfortsetzung  
 Ein XML-Literal kann mehrere Zeilen umfassen, ohne das Zeilenfortsetzungszeichen (die Leerzeichen-Unterstrich-EINGABETASTE Sequenz). Dies erleichtert es, XML-Literalen in Code mit XML-Dokumente verglichen werden soll.  
  
 Der Compiler behandelt Zeilenfortsetzungszeichen als Teil eines XML-Literals. Aus diesem Grund sollten Sie die Leerzeichen-Unterstrich-EINGABETASTE Sequenz verwenden, nur, wenn sie Teil der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt.  
  
 Allerdings benötigen Sie Zeilenfortsetzungszeichen, wenn Sie einen mehrzeiligen Ausdruck in einem eingebetteten Ausdruck haben. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Einbetten von Abfragen in der XML-Literale  
 Sie können eine Abfrage in einem eingebetteten Ausdruck verwenden. Wenn Sie dies tun, werden die Elemente, die von der Abfrage zurückgegebenen XML-Elements hinzugefügt. Dadurch können Sie die dynamische Inhalte, z. B. das Ergebnis der Abfrage eines Benutzers, ein XML-literal hinzufügen.  
  
 Der folgende Code verwendet beispielsweise eine eingebettete Abfrage zum Erstellen von XML-Elementen aus den Elementen der `phoneNumbers2` Arrays, und klicken Sie dann die Elemente als untergeordnete Elemente des hinzufügen `contact2`.  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Wie der Compiler erstellt Objekte aus XML-Literale  
 Visual Basic-Compiler übersetzt XML-Literale in Aufrufe an die entsprechende [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] von Konstruktoren zum Erstellen der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt. Z. B. Visual Basic-Compiler wird im folgenden Codebeispiel wird in einen Aufruf übersetzt die <xref:System.Xml.Linq.XProcessingInstruction> Konstruktor für die XML-Version-Anweisung, Aufrufe von der <xref:System.Xml.Linq.XElement> Konstruktor für die `<contact>`, `<name>`, und `<phone>` Elemente und Aufrufe an die <xref:System.Xml.Linq.XAttribute> Konstruktor für die `type` Attribut. Genauer gesagt, die Attribute im folgenden Beispiel, Visual Basic-Compiler wird auf die <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> zweimal Konstruktor. Der erste Aufruf übergibt den Wert `type` für die `name` -Parameter und den Wert `home` für die `value` Parameter. Die zweite übergibt den Wert auch `type` für die `name` -Parameter, aber der Wert `work` für die `value` Parameter.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md)
