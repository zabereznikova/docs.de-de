---
title: Eingebettete Ausdrücke in XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 4c96665994a7e56bc70f72b66d5922f5a6472a13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961225"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Eingebettete Ausdrücke in XML (Visual Basic)
Eingebettete Ausdrücke ermöglichen Ihnen die Erstellung von XML-Literale, die Ausdrücke enthalten, die zur Laufzeit ausgewertet werden. Die Syntax für einen eingebetteten Ausdruck ist `<%=` `expression` `%>`, das ist identisch mit der Syntax in verwendet [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
 Beispielsweise können Sie ein XML-Element Zeichenliteral erstellen eingebettete Ausdrücke mit Inhalt für Literaltext kombinieren.  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 Wenn `isbnNumber` enthält die ganze Zahl 12345 und `modifiedDate` enthält das Datum, 3/5/2006, wenn dieser Code ausgeführt wird, den Wert der `book` ist:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Speicherort des eingebetteten Ausdrucks und Überprüfung  
 Eingebettete Ausdrücke können nur an bestimmten Speicherorten innerhalb der XML-Literale Ausdrücke verwendet werden. Position des Ausdrucks legt die Typen der Ausdruck zurückgeben können und wie `Nothing` erfolgt. Die folgende Tabelle beschreibt die zulässigen Standorte und die Typen von eingebetteten Ausdrücken.  
  
|Position im literal|Der Typ des Ausdrucks|Behandlung von `Nothing`|  
|---|---|---|  
|XML-Elementname|<xref:System.Xml.Linq.XName>|Fehler|  
|XML-Elementinhalt.|`Object` oder ein Array von `Object`|Ignoriert|  
|XML-Elementname-Attribut|<xref:System.Xml.Linq.XName>|Fehler, es sei denn, der den Wert des Attributs auch ist `Nothing`|  
|XML-Element-Attributwert|`Object`|Attributdeklaration ignoriert|  
|XML-Element-Attribut|<xref:System.Xml.Linq.XAttribute> oder eine Auflistung von <xref:System.Xml.Linq.XAttribute>|Ignoriert|  
|Stammelement des XML-Dokuments|<xref:System.Xml.Linq.XElement> oder eine Auflistung von einem <xref:System.Xml.Linq.XElement> -Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> und <xref:System.Xml.Linq.XComment> Objekte|Ignoriert|  
  
- Beispiel für einen eingebetteten Ausdruck in ein XML-Elementname:  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- Beispiel für einen eingebetteten Ausdruck in den Inhalt eines XML-Elements:  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- Beispiel für einen eingebetteten Ausdruck in eine XML-Elementname-Attribut:  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attributwert:  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- Beispiel für einen eingebetteten Ausdruck in ein XML-Element-Attribut:  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- Beispiel für einen eingebetteten Ausdruck in das Stammelement eines XML-Dokuments:  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 Wenn Sie aktivieren `Option Strict`, überprüft der Compiler, dass der Typ jedes eingebetteten Ausdrucks in den erforderlichen Typ erweitert wird. Die einzige Ausnahme ist für das Stammelement eines XML-Dokuments, das überprüft wird, wenn der Code ausgeführt wird. Wenn Sie ohne Kompilieren `Option Strict`, können Sie Ausdrücke vom Typ einbetten `Object` und deren Typ wird zur Laufzeit überprüft.  
  
 An Standorten, in dem der Inhalt optional ist, eingebettete Ausdrücke, die enthalten `Nothing` werden ignoriert. Dies bedeutet, Sie haben keinen Elementinhalt, Attributwerte zu überprüfen und die Elemente des Arrays sind nicht `Nothing` vor der Verwendung eines XML-Literals. Erforderlich, nicht möglich, Werte, z. B. Element- und Attributnamen, `Nothing`.  
  
 Weitere Informationen zur Verwendung von eines eingebetteten Ausdrucks in einen bestimmten Typ eines Literals finden Sie unter [XML-Dokument-Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Bereichsregeln  
 Der Compiler konvertiert jedes XML-literal in einen Konstruktoraufruf für den entsprechenden literal. Die literalen Inhalt und eingebettete Ausdrücke in einem XML-Literal werden als Argumente an den Konstruktor übergeben. Dies bedeutet, dass alle Programmierelemente Visual Basic zur Verfügung, um ein XML-literal auch für die eingebettete Ausdrücke verfügbar sind.  
  
 Sie können in einem XML-literal, den XML-Namespace-Präfixe, die mit deklariert zugreifen der `Imports` Anweisung. Sie können ein neues XML-Namespacepräfix deklariert oder Shadowing für eine vorhandene XML-Namespacepräfix, in einem Element mit dem `xmlns` Attribut. Der neue Namespace ist verfügbar, die untergeordneten Knoten dieses Elements, aber nicht auf XML-Literalen in eingebettete Ausdrücke.  
  
> [!NOTE]
>  Wenn Sie ein XML-Namespacepräfix deklarieren, indem die `xmlns` Namespace-Attribut den Wert des Attributs muss eine Konstante Zeichenfolge sein. In dieser Hinsicht mithilfe der `xmlns` Attribut ist, wie die Verwendung der `Imports` Anweisung, um ein XML-Namespace zu deklarieren. Sie können keinen eingebetteten Ausdruck verwenden, um die XML-Namespacewert anzugeben.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Übersicht über XML-Literale](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
