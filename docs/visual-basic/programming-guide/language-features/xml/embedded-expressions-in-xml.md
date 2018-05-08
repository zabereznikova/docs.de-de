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
ms.openlocfilehash: f99735df2512fd4b1477bab9126e18f5afbbfa8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Eingebettete Ausdrücke in XML (Visual Basic)
Mit eingebetteten können Ausdrücken Sie XML-Literale erstellen, die Ausdrücke enthalten, die zur Laufzeit ausgewertet werden. Die Syntax für einen eingebetteten Ausdruck `<%=` `expression` `%>`, denen ist identisch, verwendet die Syntax in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
 Beispielsweise können Sie ein XML-Element literal erstellen eingebettete Ausdrücke mit Literaltext kombinieren.  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 Wenn `isbnNumber` enthält die ganze Zahl 12345 und `modifiedDate` enthält das Datum, 3/5/2006, wenn dieser Code ausgeführt wird, den Wert des `book` ist:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Speicherort der eingebetteten Ausdruck und Überprüfung  
 Eingebettete Ausdrücke können nur an bestimmten Positionen im XML-Literale Ausdrücke angezeigt werden. Der Ausdruck Speicherort-steuert, welche die Typen der Ausdruck zurückgeben können und wie `Nothing` behandelt wird. Die folgende Tabelle beschreibt die zulässigen Positionen und Typen von eingebetteten Ausdrücken.  
  
|Position im literal|Der Typ des Ausdrucks|Behandlung von `Nothing`|  
|---|---|---|  
|XML-Elementnamen|<xref:System.Xml.Linq.XName>|Fehler|  
|XML-Elementinhalt.|`Object` oder ein Array von `Object`|Ignoriert|  
|XML-Element-Attributnamen|<xref:System.Xml.Linq.XName>|Fehler, es sei denn, Sie auch den Wert des Attributs ist `Nothing`|  
|XML-Element-Attributwert|`Object`|Attributdeklaration ignoriert|  
|XML-Element-Attribut|<xref:System.Xml.Linq.XAttribute> oder eine Auflistung von <xref:System.Xml.Linq.XAttribute>|Ignoriert|  
|Stammelement des XML-Dokuments|<xref:System.Xml.Linq.XElement> oder eine Auflistung von einem <xref:System.Xml.Linq.XElement> -Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> und <xref:System.Xml.Linq.XComment> Objekte|Ignoriert|  
  
-   Beispiel für einen eingebetteten Ausdruck in den Namen eines XML-Elements:  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck im Inhalt eines XML-Elements:  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attribut-Namen:  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attributwert:  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attribut:  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in ein XML-Dokument-Stammelement:  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 Wenn Sie aktivieren `Option Strict`, überprüft der Compiler, dass der Typ jedes eingebetteten Ausdrucks in den erforderlichen Typ erweitert wird. Die einzige Ausnahme ist für das Stammelement eines XML-Dokuments, das überprüft wird, wenn der Code ausgeführt wird. Wenn Sie bei der Kompilierung ohne `Option Strict`, können Sie Ausdrücke vom Typ einbetten `Object` und deren Typ wird zur Laufzeit überprüft.  
  
 An Standorten, in dem der Inhalt optional ist, eingebettete Ausdrücke, die enthalten `Nothing` werden ignoriert. Dies bedeutet, dass Sie keine Elementinhalt, Attributwerte, überprüfen und Elemente des Arrays sind nicht `Nothing` vor der Verwendung eines XML-Literals. Erforderlich, nicht mit Werten, z. B. Element- und Attributnamen verwendet, `Nothing`.  
  
 Weitere Informationen zur Verwendung von eines eingebetteten Ausdrucks in einen bestimmten Typ eines Literals finden Sie unter [XML-Dokument-Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Bereichsregeln  
 Der Compiler konvertiert jedes XML-literal in einen Konstruktoraufruf für den jeweiligen literal. Die literalen Inhalt und eingebettete Ausdrücke in einem XML-Literal werden als Argumente an den Konstruktor übergeben. Dies bedeutet, dass alle Programmierelemente Visual Basic ein XML-literal kann auch für deren eingebettete Ausdrücke verfügbar sind.  
  
 In einem XML-literal, erreichen Sie den deklarierten XML-Namespacepräfixe mit der `Imports` Anweisung. Sie können ein neue XML-Namespacepräfix deklariert oder Shadowing für eine vorhandene XML-Namespacepräfix in einem Element mit dem `xmlns` Attribut. Der neue Namespace ist verfügbar, um die untergeordneten Knoten des jeweiligen Elements, jedoch nicht in XML-Literale in eingebettete Ausdrücke.  
  
> [!NOTE]
>  Wenn Sie ein XML-Namespacepräfix deklarieren, indem die `xmlns` Namespace-Attribut den Wert des Attributs muss eine Konstante Zeichenfolge sein. In dieser Hinsicht mithilfe der `xmlns` Attribut ist, wie die Verwendung der `Imports` -Anweisung zum Deklarieren eines XML-Namespace. Einen eingebetteten Ausdruck können Sie die XML-Namespacewert anzugeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Übersicht über XML-Literale](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
