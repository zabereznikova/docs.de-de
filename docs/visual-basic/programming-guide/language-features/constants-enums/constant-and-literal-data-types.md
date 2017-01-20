---
title: "Constant and Literal Data Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaring constants, literal data types"
  - "data types [Visual Basic], declaring"
  - "constants, declaring"
  - "explicit declarations"
  - "literals, coercing data type"
  - "declarations, data types"
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Constant and Literal Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein Literal ist ein Wert, der sich selbst ausdrückt und nicht als Wert einer Variablen oder als Ergebnis eines Ausdrucks ausgedrückt wird, beispielsweise die Zahl 3 oder die Zeichenfolge "Hallo".  Eine Konstante ist ein aussagekräftiger Name, der anstelle eines Literals verwendet wird. Im Unterschied zu einer Variablen, deren Wert sich ändern kann, ist der Wert einer Konstante während der Ausführung des Programms unveränderlich.  
  
 Wenn die [Option "Infer"](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` und die [Option "Strict"](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On` ist, müssen alle Konstanten explizit mit einem Datentyp deklariert werden.  Im folgenden Beispiel wird der Datentyp von `MyByte` explizit als Datentyp `Byte` deklariert:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-t_1.vb)]  
  
 Wenn `Option Infer` `On` oder `Option Strict` is `Off` ist, können Sie eine Konstante ohne Angabe eines Datentyps mit einer `As`\-Klausel deklarieren.  Der Compiler bestimmt den Typ der Konstante anhand des Ausdruckstyps.  Ein numerisches Ganzzahlliteral wird standardmäßig in den Datentyp `Integer` umgewandelt.  Der Standarddatentyp für Gleitkommazahlen lautet `Double`, und die Schlüsselwörter `True` sowie `False` geben eine `Boolean`\-Konstante an.  
  
## Literale und Typkonvertierung  
 In bestimmten Fällen kann es erforderlich sein, einen bestimmten Datentyp für ein Literal zu erzwingen. Dies ist beispielsweise der Fall, wenn Sie einem besonders großen Ganzzahlliteralwert eine Variable vom Typ `Decimal` zuweisen möchten.  Das folgende Beispiel führt zu einem Fehler:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Der Fehler resultiert aus der Literaldarstellung.  Der `Decimal`\-Datentyp kann einen Wert dieser Größe enthalten. Das Literal wird jedoch implizit als `Long` dargestellt. Dabei handelt es sich um einen Datentyp, der einen solchen Wert nicht enthalten kann.  
  
 Sie haben zwei Möglichkeiten zum Konvertieren eines Literals in einen bestimmten Datentyp: indem Sie ein Typzeichen anhängen oder das Literal in Zeichen einschließen.  Ein Typzeichen oder umschließende Zeichen müssen dem Literal unmittelbar vorangehen und\/oder folgen. Leerzeichen oder andere Zeichen dürfen also nicht dazwischen stehen.  
  
 Zur Korrektur des vorherigen Beispiels hängen Sie das Typzeichen `D` an das Literal an. Dadurch wird das Literal als `Decimal` dargestellt:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-t_2.vb)]  
  
 Das folgende Beispiel demonstriert die richtige Verwendung von Typzeichen und umschließenden Zeichen:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-t_3.vb)]  
  
 In der folgenden Tabelle finden Sie die in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] zur Verfügung stehenden umschließenden Zeichen und Typzeichen.  
  
||||  
|-|-|-|  
|Datentyp|Umschließendes Zeichen|Angehängtes Typzeichen|  
|`Boolean`|\(kein\)|\(kein\)|  
|`Byte`|\(kein\)|\(kein\)|  
|`Char`|"|C|  
|`Date`|\#|\(kein\)|  
|`Decimal`|\(kein\)|D oder @|  
|`Double`|\(kein\)|R oder \#|  
|`Integer`|\(kein\)|I oder %|  
|`Long`|\(kein\)|L oder &|  
|`Short`|\(kein\)|S|  
|`Single`|\(kein\)|F oder \!|  
|`String`|"|\(kein\)|  
  
## Siehe auch  
 [User\-Defined Constants](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)   
 [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)   
 [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Option Explicit Statement](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)