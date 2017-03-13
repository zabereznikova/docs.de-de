---
title: "&amp; Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.&"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "And (&) operator"
  - "ampersand operator (&)"
  - "& operator"
  - "concatenation operators, syntax"
  - "strings [Visual Basic], concatenating"
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &amp; Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Generiert eine Zeichenfolgenverkettung zweier Ausdrücke.  
  
## Syntax  
  
```  
  
result = expression1 & expression2  
```  
  
## Teile  
 `result`  
 Erforderlich.  Beliebige `String`\- oder `Object`\-Variable.  
  
 `expression1`  
 Erforderlich.  Ausdruck mit einem Datentyp, der zu `String` erweitert wird.  
  
 `expression2`  
 Erforderlich.  Ausdruck mit einem Datentyp, der zu `String` erweitert wird.  
  
## Hinweise  
 Wenn der `expression1`\-Datentyp oder der `expression2`\-Datentyp nicht `String` ist, jedoch zu `String` erweitert werden kann, wird er in `String` konvertiert.  Falls einer der Datentypen nicht zu `String` erweitert werden kann, generiert der Compiler einen Fehler.  
  
 Der `result`\-Datentyp ist `String`.  Wenn einer der beiden Ausdrücke oder beide [Nothing](../../../visual-basic/language-reference/nothing.md) oder den Wert <xref:System.DBNull.Value?displayProperty=fullName> ergeben, werden sie als Zeichenfolge mit dem Wert "" behandelt.  
  
> [!NOTE]
>  Der Operator `&` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  Das kaufmännische UND\-Zeichen \(&\) kann auch verwendet werden, um Variablen als Typ `Long` zu identifizieren.  Weitere Informationen finden Sie unter [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## Beispiel  
 In diesem Beispiel wird mit dem Operator `&` die Zeichenfolgenverkettung erzwungen.  Das Ergebnis ist ein Zeichenfolgenwert, der die Verkettung der beiden Zeichenfolgenoperanden darstellt.  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## Siehe auch  
 [&\= Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Concatenation Operators](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Concatenation Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)