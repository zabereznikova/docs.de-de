---
title: "XML Document Literal (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralDocument"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML document literal [Visual Basic]"
  - "XML literals [Visual Basic], document"
  - "XML documents [Visual Basic], creating"
  - "document literal [Visual Basic]"
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# XML Document Literal (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ein Literal, das ein <xref:System.Xml.Linq.XDocument>\-Objekt darstellt.  
  
## Syntax  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`encoding`|Optional.  Literaltext, der deklariert, welche Codierung das Dokument verwendet.|  
|`standalone`|Optional.  Literaltext.  Muss "ja" oder "nein" sein.|  
|`piCommentList`|Optional.  Liste von XML\-Verarbeitungsanweisungen und XML\-Kommentaren.  Die Anweisungen sind im folgenden Format:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Für jeden `piComment` `` gibt es folgende Möglichkeiten:<br /><br /> -   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Erforderlich.  Stammelement des Dokuments.  Das Format ist eins der folgenden:<br /><br /> <ul><li>[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Eingebetteter Ausdruck der Form `<%=` `elementExp` `%>`.  `elementExp` gibt Folgendes zurück:<br /><br /> <ul><li>Ein <xref:System.Xml.Linq.XElement>\-Objekt.</li><li>Eine Auflistung, die ein <xref:System.Xml.Linq.XElement>\-Objekt und eine Anzahl von <xref:System.Xml.Linq.XProcessingInstruction>\-Objekten und <xref:System.Xml.Linq.XComment>\-Objekten enthält.</li></ul></li></ul><br /> Weitere Informationen finden Sie unter [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## Rückgabewert  
 Ein <xref:System.Xml.Linq.XDocument>\-Objekt.  
  
## Hinweise  
 Ein XML\-Dokumentliteral wird von der XML\-Deklaration am Anfang des Literals identifiziert.  Auch wenn jedes XML\-Dokumentliteral genau ein XML\-Stammelement haben muss, kann es über beliebig viele XML\-Verarbeitungsanweisungen und XML\-Kommentare verfügen.  
  
 Ein XML\-Dokumentliteral kann nicht in einem XML\-Element enthalten sein.  
  
> [!NOTE]
>  Ein XML\-Literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen zu verwenden.  So kann Inhalt aus einem XML\-Dokument kopiert und direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programm eingefügt werden.  
  
 Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler konvertiert das XML\-Dokumentliteral in Aufrufe an den <xref:System.Xml.Linq.XDocument.%23ctor%2A>\-Konstruktor und den <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>\-Konstruktor.  
  
## Beispiel  
 Mit dem folgenden Beispiel wird ein XML\-Dokument mit einer XML\-Deklaration, einer Verarbeitungsanweisung, einem Kommentar und einem Element, das ein anderes Element enthält, erstellt.  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-document-literal_1.vb)]  
  
## Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Xml.Linq.XProcessingInstruction>   
 <xref:System.Xml.Linq.XComment>   
 <xref:System.Xml.Linq.XDocument>   
 [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)   
 [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)