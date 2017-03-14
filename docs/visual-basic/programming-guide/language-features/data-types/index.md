---
title: "Datentypen in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Datentypen [Visual Basic], Deklarieren"
  - "Typisierung"
  - "Datentypen [Visual Basic]"
  - "Visual Basic-Code, Datentypen"
  - "Datentypen [Visual Basic], Verbessern der Geschwindigkeit mit"
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Datentypen in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Der *Datentyp* von Programmierelementen gibt an, welche Art von Daten das jeweilige Programmierelement enthalten kann und wie diese Daten gespeichert werden.  Datentypen gelten für alle Werte, die im Computerspeicher gespeichert werden können oder an der Auswertung eines Ausdrucks beteiligt sind.  Der Rückgabewert jeder Variablen, jedes Literals, jeder Konstanten, jeder Enumeration, jeder Eigenschaft, jedes Prozedurparameters und jedes Prozedurrückgabewerts verfügt über einen Datentyp.  
  
## Deklarierte Datentypen  
 Programmierelemente werden mit einer Deklarationsanweisung definiert, und der zugehörige Datentyp wird mit der `As`\-Klausel angegeben.  Die folgende Tabelle enthält die Anweisungen, mit denen Sie verschiedene Elemente deklarieren.  
  
|Programmierelement|Datentypdeklaration|  
|------------------------|-------------------------|  
|Variable|In einer [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Literal|Mit einem Literalzeichen; siehe "Literalzeichen" in [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|Konstante|In einer [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|Enumeration|In einer [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)<br /><br /> `Public`   `Enum`   `colors`|  
|Eigenschaft|In einer [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)<br /><br /> `Property`   `region() As String`|  
|Prozedurparameter|In einer [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) oder einer [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|Prozedurargument|Im aufrufenden Code. Jedes Argument ist ein Programmierelement, das bereits deklariert wurde, oder ein Ausdruck, der deklarierte Elemente enthält.<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|Rückgabewert der Prozedur|In einer [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) oder einer [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 Eine Liste von Visual Basic\-Datentypen, finden Sie unter [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## Siehe auch  
 [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)