---
title: "Embedded Expressions in XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlEmbeddedExpression"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "embedded expressions [Visual Basic]"
  - "LINQ to XML [Visual Basic], embedded expressions"
  - "XML literals [Visual Basic], embedded expressions"
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Embedded Expressions in XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit eingebetteten Ausdrücken können XML\-Literale erstellt werden, die Ausdrücke enthalten, welche zur Laufzeit ausgewertet werden.  Die Syntax für einen eingebetteten Ausdruck ist `<%=` `expression` `%>`. Sie stimmt mit der in [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)] verwendeten Syntax überein.  
  
 Beispielsweise können XML\-Elementliterale erstellt und so eingebettete Ausdrücke mit Literaltextinhalt kombiniert werden.  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 Wenn `isbnNumber` die ganze Zahl 12345 und `modifiedDate` das Datum 3\/5\/2006 enthält, hat `book` nach der Ausführung des Codes den folgenden Wert:  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## Position und Validierung eingebetteter Ausdrücke  
 Eingebettete Ausdrücke können nur an bestimmten Positionen in XML\-Literalausdrücken stehen.  Die Position des Ausdrucks legt fest, welche Typen der Ausdruck zurückgeben kann und wie `Nothing` behandelt wird.  In der folgenden Tabelle werden die zulässigen Positionen und Typen eingebetteter Ausdrücke beschrieben.  
  
||||  
|-|-|-|  
|Position im Literal|Ausdruckstyp|Behandlung von `Nothing`|  
|XML\-Elementname|<xref:System.Xml.Linq.XName>|Fehler|  
|XML\-Elementinhalt|`Object` oder Array von `Object`|Ignoriert|  
|XML\-Element\-Attributname|<xref:System.Xml.Linq.XName>|Fehler, außer wenn der Attributwert auch `Nothing` ist|  
|XML\-Element\-Attributwert|`Object`|Attributdeklaration wird ignoriert|  
|XML\-Elementattribut|<xref:System.Xml.Linq.XAttribute> oder eine Auflistung von <xref:System.Xml.Linq.XAttribute>|Ignoriert|  
|XML\-Dokument\-Stammelement|<xref:System.Xml.Linq.XElement> oder eine Auflistung eines <xref:System.Xml.Linq.XElement>\-Objekts und einer beliebigen Anzahl von <xref:System.Xml.Linq.XProcessingInstruction>\-Objekten und <xref:System.Xml.Linq.XComment>\-Objekten|Ignoriert|  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML\-Elementnamen:  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck im Inhalt eines XML\-Elements:  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML\-Element\-Attributnamen:  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML\-Element\-Attributwert:  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML\-Elementattribut:  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   Beispiel für einen eingebetteten Ausdruck in einem XML\-Dokument\-Stammelement:  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 Wenn `Option Strict` aktiviert ist, überprüft der Compiler, ob der Typ jedes eingebetteten Ausdrucks auf den erforderlichen Typ erweitert wird.  Die einzige Ausnahme davon ist das Stammelement eines XML\-Dokuments, das während der Ausführung des Codes überprüft wird.  Wenn ohne `Option Strict` kompiliert wird, können Ausdrücke vom Typ `Object` eingebettet werden, und deren Typ wird während der Laufzeit überprüft.  
  
 An Positionen, an denen Inhalt optional ist, werden eingebettete Ausdrücke, die `Nothing` enthalten, ignoriert.  Das bedeutet, dass vor der Verwendung eines XML\-Literals nicht überprüft werden muss, ob Elementinhalt, Attributwerte und Arrayelemente `Nothing` sind.  Erforderliche Werte, z. B. Element\- und Attributnamen, können nicht `Nothing` sein.  
  
 Weitere Informationen über die Verwendung von eingebetteten Ausdrücken in Literalen eines bestimmten Typs finden Sie unter [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## Bereichsregeln  
 Der Compiler konvertiert jedes XML\-Literal in einen Konstruktoraufruf des entsprechenden Literaltyps.  Der Literalinhalt und eingebettete Ausdrücke in einem XML\-Literal werden dem Konstruktor als Argumente übergeben.  Das bedeutet, dass sämtliche für XML\-Literale verfügbare [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programmierelemente auch für deren eingebettete Ausdrücke verfügbar sind.  
  
 Innerhalb eines XML\-Literals kann auf die mit der `Imports`\-Anweisung deklarierten XML\-Namespacepräfixe zugegriffen werden.  Mit dem `xmlns`\-Attribut kann in einem Element ein neues XML\-Namespacepräfix deklariert oder Shadowing für ein existierendes XML\-Namespacepräfix durchgeführt werden.  Der neue Namespace ist für untergeordnete Knoten, nicht jedoch für XML\-Literale in eingebetteten Ausdrücken verfügbar.  
  
> [!NOTE]
>  Wenn ein XML\-Namespacepräfix mit dem `xmlns`\-Namespace\-Attribut deklariert wird, muss der Attributwert eine konstante Zeichenfolge sein.  Unter diesem Gesichtspunkt gleicht die Verwendung des `xmlns`\-Attributs der Verwendung der `Imports`\-Anweisung zum Deklarieren eines XML\-Namespace.  Sie können keinen eingebetteten Ausdruck verwenden, um den XML\-Namespacewert anzugeben.  
  
## Siehe auch  
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)