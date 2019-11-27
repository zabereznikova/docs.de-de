---
title: Eingebettete Ausdrücke in XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 0cdb960160457108ddf18c554dae5f5993269833
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332351"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Eingebettete Ausdrücke in XML (Visual Basic)
Mit eingebetteten Ausdrücken können Sie XML-Literale erstellen, die Ausdrücke enthalten, die zur Laufzeit ausgewertet werden. Die Syntax für einen eingebetteten Ausdruck ist `<%=` `expression` `%>`. Dies entspricht der Syntax, die in ASP.NET verwendet wird.  
  
 Sie können z. b. ein XML-Elementliteral erstellen, indem Sie eingebettete Ausdrücke mit literalem Text Inhalt kombinieren.  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 Wenn `isbnNumber` die ganze Zahl 12345 enthält und `modifiedDate` das Datum 3/5/2006 enthält, ist der Wert von `book`, wenn dieser Code ausgeführt wird:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Speicherort und Validierung des eingebetteten Ausdrucks  
 Eingebettete Ausdrücke können nur an bestimmten Positionen innerhalb von XML-Literalausdrücken vorkommen. Der Ausdrucks Speicherort steuert, welche Typen der Ausdruck zurückgeben kann und wie `Nothing` behandelt werden. In der folgenden Tabelle werden die zulässigen Speicherorte und Typen von eingebetteten Ausdrücken beschrieben.  
  
|Speicherort in Literalen|Typ des Ausdrucks|Behandlung von `Nothing`|  
|---|---|---|  
|XML-Elementname|<xref:System.Xml.Linq.XName>|Error|  
|Inhalt des XML-Elements|`Object` oder Array von `Object`|Ignoriert|  
|Name des XML-Element Attributs|<xref:System.Xml.Linq.XName>|Fehler, es sei denn, der Attribut Wert ist ebenfalls `Nothing`|  
|XML-Element Attribut Wert|`Object`|Attribut Deklaration wird ignoriert|  
|XML-Element Attribut|<xref:System.Xml.Linq.XAttribute> oder eine Auflistung von <xref:System.Xml.Linq.XAttribute>|Ignoriert|  
|Stamm Element des XML-Dokuments|<xref:System.Xml.Linq.XElement> oder eine Auflistung von einem <xref:System.Xml.Linq.XElement> Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> und <xref:System.Xml.Linq.XComment> Objekten|Ignoriert|  
  
- Beispiel für einen eingebetteten Ausdruck in einem XML-Elementnamen:  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- Beispiel eines eingebetteten Ausdrucks im Inhalt eines XML-Elements:  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- Beispiel für einen eingebetteten Ausdruck in einem XML-Element Attributnamen:  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- Beispiel für einen eingebetteten Ausdruck in einem Attribut Wert des XML-Elements:  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- Beispiel für einen eingebetteten Ausdruck in einem XML-Element Attribut:  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- Beispiel eines eingebetteten Ausdrucks in einem XML-Dokument Stamm Element:  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 Wenn Sie `Option Strict`aktivieren, überprüft der Compiler, ob der Typ jedes eingebetteten Ausdrucks auf den erforderlichen Typ erweitert wird. Die einzige Ausnahme gilt für das Stamm Element eines XML-Dokuments, das überprüft wird, wenn der Code ausgeführt wird. Wenn Sie ohne `Option Strict`kompilieren, können Sie Ausdrücke vom Typ `Object` einbetten, und der Typ wird zur Laufzeit überprüft.  
  
 An Standorten, an denen Inhalt optional ist, werden eingebettete Ausdrücke, die `Nothing` enthalten, ignoriert. Dies bedeutet, dass Sie nicht überprüfen müssen, ob Element Inhalt, Attributwerte und Array Elemente vor der Verwendung eines XML-Literals nicht `Nothing` werden. Erforderliche Werte, z. b. Element-und Attributnamen, können nicht `Nothing`werden.  
  
 Weitere Informationen zum Verwenden eines eingebetteten Ausdrucks in einem bestimmten Literaltyp finden Sie unter [XML-dokumentliterale](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML-Elementliterale](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Bereichsregeln  
 Der Compiler konvertiert alle XML-Literale in einen konstruktorrückruf für den entsprechenden Literaltyp. Der Literale Inhalt und eingebettete Ausdrücke in einem XML-Literalformat werden als Argumente an den Konstruktor übergeben. Dies bedeutet, dass alle Visual Basic Programmier Elemente, die für ein XML-wahrsten verfügbar sind, auch für eingebettete Ausdrücke verfügbar sind.  
  
 Innerhalb eines XML-Literals können Sie auf die XML-Namespace Präfixe zugreifen, die mit der `Imports`-Anweisung deklariert werden. Sie können ein neues XML-Namespace Präfix oder ein neues XML-Namespace Präfix mithilfe des `xmlns`-Attributs in einem-Element deklarieren. Der neue Namespace ist für die untergeordneten Knoten dieses Elements verfügbar, jedoch nicht für XML-Literale in eingebetteten Ausdrücken.  
  
> [!NOTE]
> Wenn Sie ein XML-Namespace Präfix mit dem `xmlns` Namespace-Attribut deklarieren, muss der Attribut Wert eine Konstante Zeichenfolge sein. In dieser Hinsicht entspricht die Verwendung des `xmlns` Attributs der Verwendung der `Imports`-Anweisung zum Deklarieren eines XML-Namespace. Sie können keinen eingebetteten Ausdruck verwenden, um den XML-Namespace Wert anzugeben.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Übersicht über XML-Literale](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
