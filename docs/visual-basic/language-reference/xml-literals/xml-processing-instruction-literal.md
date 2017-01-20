---
title: "XML Processing Instruction Literal (Visual Basic) | Microsoft Docs"
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
  - "vb.XmlLiteralProcessingInstruction"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML literals [Visual Basic], processing instruction"
  - "XML processing instruction literal [Visual Basic]"
  - "processing instruction literal [Visual Basic]"
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML Processing Instruction Literal (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein Literal, das ein <xref:System.Xml.Linq.XProcessingInstruction>\-Objekt darstellt.  
  
## Syntax  
  
```  
<?piName [ = piData ] ?>  
```  
  
## Teile  
 `<?`  
 Erforderlich.  Kennzeichnet den Anfang des XML\-Verarbeitungsanweisungsliterals.  
  
 `piName`  
 Erforderlich.  Name, der angibt, auf welche Anwendung die Verarbeitungsanweisung abzielt.  Darf nicht mit "xml" oder "XML" beginnen.  
  
 `piData`  
 Optional.  Zeichenfolge zum Angeben, wie die Anwendung, auf die `piName` abzielt, das XML\-Dokument verarbeiten soll.  
  
 `?>`  
 Erforderlich.  Kennzeichnet das Ende der Verarbeitungsanweisung.  
  
## Rückgabewert  
 Ein <xref:System.Xml.Linq.XProcessingInstruction>\-Objekt.  
  
## Hinweise  
 XML\-Verarbeitungsanweisungsliterale geben an, wie Anwendungen ein XML\-Dokument verarbeiten sollen.  Wenn eine Anwendung ein XML\-Dokument lädt, kann die Anwendung die XML\-Verarbeitungsanweisungen überprüfen, um zu bestimmen, wie das Dokument verarbeitet wird.  Die Anwendung interpretiert die Bedeutung von `piName` und `piData`.  
  
 Das XML\-Dokumentliteral verwendet eine ähnliche Syntax wie die XML\-Verarbeitungsanweisung.  Weitere Informationen finden Sie unter [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  Das `piName`\-Element darf nicht mit den Zeichenfolgen "xml" oder "XML" beginnen, weil diese Bezeichner für XML 1.0\-Spezifikationen reserviert sind.  
  
 Ein XML\-Verarbeitungsanweisungsliteral kann einer Variablen zugewiesen oder in einem XML\-Dokumentliteral eingeschlossen werden.  
  
> [!NOTE]
>  Ein XML\-Literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen zu benötigen.  So kann Inhalt aus einem XML\-Dokument kopiert und direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programm eingefügt werden.  
  
 Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler konvertiert das XML\-Verarbeitungsanweisungsliteral in einen Aufruf des <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>\-Konstruktors.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Verarbeitungsanweisung erstellt, die ein Stylesheet für ein XML\-Dokument identifiziert.  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-_1.vb)]  
  
## Siehe auch  
 <xref:System.Xml.Linq.XProcessingInstruction>   
 [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)