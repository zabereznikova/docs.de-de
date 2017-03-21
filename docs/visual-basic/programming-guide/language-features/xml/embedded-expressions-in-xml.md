---
title: "Eingebettete Ausdrücke in XML (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlEmbeddedExpression
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
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
ms.openlocfilehash: e5cd40e55ec23de3ad1bb2f5f065762c893d9cb3
ms.lasthandoff: 03/13/2017

---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Eingebettete Ausdrücke in XML (Visual Basic)
Mit eingebetteten können Ausdrücken Sie XML-Literale zu erstellen, die Ausdrücke enthalten, die zur Laufzeit ausgewertet werden. Die Syntax für einen eingebetteten Ausdruck lautet `<%=` `expression` `%>`, das ist identisch mit der Syntax in verwendet [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].  
  
 Beispielsweise können Sie ein XML-Element literal erstellen eingebettete Ausdrücke mit Literaltext kombinieren.  
  
 [!code-vb[VbXMLSamples&#27;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 Wenn `isbnNumber` die ganze Zahl 12345 und `modifiedDate` enthält das Datum, 3/5/2006, wenn dieser Code ausgeführt wird, den Wert des `book` ist:  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Eingebettete Ausdrücke Positionierung und Validierung  
 Eingebettete Ausdrücke können nur an bestimmten Positionen in XML-Literale Ausdrücke angezeigt werden. Position des Ausdrucks legt die Typen der Ausdruck zurückgeben können und wie `Nothing` behandelt wird. Die folgende Tabelle beschreibt die zulässigen Positionen und Typen von eingebetteten Ausdrücken.  
  
|Position im literal|Der Typ des Ausdrucks|Behandlung von`Nothing`|  
|---|---|---|  
|XML-Elementnamen|<xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName>|Fehler|  
|XML-Elementinhalt.|`Object`oder ein Array von`Object`|Ignoriert|  
|XML-Elementname-Attribut|<xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName>|Fehler, es sei denn, Sie auch den Wert des Attributs ist`Nothing`|  
|XML-Element-Attributwert|`Object`|Attributdeklaration wird ignoriert|  
|XML-Element-Attribut|<xref:System.Xml.Linq.XAttribute>oder eine Auflistung von<xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute>|Ignoriert|  
|Stammelement des XML-Dokuments|<xref:System.Xml.Linq.XElement>oder eine Auflistung von einem <xref:System.Xml.Linq.XElement>Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment>Objekten</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XElement>|Ignoriert|  
  
-   Beispiel für einen eingebetteten Ausdruck in ein XML-Elementname:  
  
     [!code-vb[VbXMLSamples&#32;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck im Inhalt eines XML-Elements:  
  
     [!code-vb[VbXMLSamples&33;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in ein XML-Elementname-Attribut:  
  
     [!code-vb[VbXMLSamples&#34;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attributwert:  
  
     [!code-vb[VbXMLSamples&#35;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attribut:  
  
     [!code-vb[VbXMLSamples Nr.&36;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML-Dokument-Stammelement:  
  
     [!code-vb[VbXMLSamples&#37;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 Wenn Sie aktivieren `Option Strict`, überprüft der Compiler, dass der Typ jedes eingebetteten Ausdrucks auf den erforderlichen Typ erweitert wird. Die einzige Ausnahme gilt für das Stammelement eines XML-Dokuments, die überprüft wird, wenn der Code ausgeführt wird. Wenn Sie ohne Kompilieren `Option Strict`, können Sie Ausdrücke vom Typ einbetten `Object` und deren Typ wird zur Laufzeit überprüft.  
  
 An Standorten, in dem Inhalte optional und ist, eingebetteten Ausdrücken, die enthalten `Nothing` werden ignoriert. Dies bedeutet, dass Sie keinen Elementinhalt, Attributwerte zu überprüfen und Arrayelemente sind nicht `Nothing` vor der Verwendung von XML-Literal. Erforderliche Werte, z. B. Element- und Attributnamen, nicht `Nothing`.  
  
 Weitere Informationen zur Verwendung von eingebetteten Ausdrücken in Literalen eines bestimmten Typs finden Sie unter [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Bereichsregeln  
 Der Compiler konvertiert jedes XML-literal in einen Konstruktoraufruf für den entsprechenden literal. Die literalen Inhalt und eingebettete Ausdrücke in einem XML-Literal werden als Argumente an den Konstruktor übergeben. Dies bedeutet, dass alle [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] XML-Literale verfügbaren Programmierelemente sind auch für deren eingebettete Ausdrücke verfügbar.  
  
 Sie können in einem XML-literal der deklarierten XML-Namespacepräfixe mit zugreifen der `Imports` Anweisung. Sie können ein neue XML-Namespacepräfix deklariert oder Shadowing ein vorhandenen XML-Namespacepräfix, in einem Element mit dem `xmlns` Attribut. Der neue Namespace ist auch die untergeordneten Knoten des Elements, jedoch nicht für XML-Literale in eingebetteten Ausdrücken verfügbar.  
  
> [!NOTE]
>  Wenn Sie ein XML-Namespacepräfix deklarieren, indem die `xmlns` Namespace-Attribut den Wert des Attributs muss eine Konstante Zeichenfolge sein. In dieser Hinsicht mithilfe der `xmlns` -Attribut ist vergleichbar mit der `Imports` -Anweisung zum Deklarieren eines XML-Namespace. Einen eingebetteten Ausdruck können Sie den Wert des XML-Namespace angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Übersicht über XML-Literale](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
