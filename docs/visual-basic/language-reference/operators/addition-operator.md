---
title: "+ Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.+"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arithmetic operators, addition"
  - "+ operator"
  - "concatenation operators, syntax"
  - "strings [Visual Basic], concatenating"
  - "sum operator"
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# + Operator (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Addiert zwei Zahlen oder gibt den positiven Wert eines numerischen Ausdrucks zurück.  Kann auch zum Verketten zweier Zeichenfolgenausdrücke verwendet werden.  
  
## Syntax  
  
```  
  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`expression1`|Erforderlich.  Beliebiger numerischer Ausdruck oder Zeichenfolgenausdruck.|  
|`expression2`|Erforderlich, außer wenn der Operator `+` einen negativen Wert berechnet.  Beliebiger numerischer Ausdruck oder Zeichenfolgenausdruck.|  
  
## Ergebnis  
 Wenn sowohl `expression1` als auch `expression2` numerisch sind, ist das Ergebnis ihre arithmetische Summe.  
  
 Wenn `expression2` nicht vorhanden ist, ist der Operator `+` der *unäre* Identitätsoperator für den unveränderten Wert eines Ausdrucks.  Unter diesen Bedingungen besteht die Operation darin, das Vorzeichen von `expression1` beizubehalten, sodass das Ergebnis negativ ist, wenn `expression1` negativ ist.  
  
 Wenn sowohl `expression1` als auch `expression2` Zeichenfolgen sind, ist das Ergebnis die Verkettung ihrer Werte.  
  
 Wenn `expression1` und `expression2` unterschiedliche Typen sind, richtet sich die ausgeführte Aktion nach ihren Typen, ihren Inhalten und der Einstellung der [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).  Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
## Unterstützte Typen  
 Alle numerischen Typen, einschließlich Typen ohne Vorzeichen, Gleitkommatypen sowie `Decimal` und `String`.  
  
## Hinweise  
 Im Allgemeinen führt `+` wann immer möglich arithmetische Additionen aus und führt nur dann eine Verkettung aus, wenn beide Ausdrücke Zeichenfolgen sind.  
  
 Wenn kein Ausdruck ein `Object` ist, führt Visual Basic die folgenden Aktionen aus.  
  
|||  
|-|-|  
|Datentypen der Ausdrücke|Aktion des Compilers|  
|Beide Ausdrücke sind numerische Datentypen \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` oder `Double`\)|Addition  Der Ergebnisdatentyp ist ein numerischer Typ, der sich für die Datentypen von `expression1` und `expression2` eignet.  Siehe die "Ganzzahlarithmetik"\-Tabellen in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Beide Ausdrücke weisen den Typ `String` auf|Verkettung|  
|Ein Ausdruck ist ein numerischer Datentyp und der andere eine Zeichenfolge.|Wenn `Option Strict` auf `On` festgelegt ist, wird ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` auf `Off` festgelegt ist, wird `String` implizit in `Double` konvertiert und addiert.<br /><br /> Wenn `String` nicht in `Double` konvertiert werden kann, wird eine <xref:System.InvalidCastException>\-Ausnahme ausgelöst.|  
|Ein Ausdruck ein numerischer Datentyp und der andere [Nothing](../../../visual-basic/language-reference/nothing.md) ist|Addition, wobei der Wert von `Nothing` 0 ist.|  
|Ein Ausdruck ist eine Zeichenfolge und der andere `Nothing`|Verkettung mit `Nothing`, wobei Nothing als "" angenommen wird.|  
  
 Wenn ein Ausdruck ein `Object` ist, führt Visual Basic die folgenden Aktionen aus.  
  
|||  
|-|-|  
|Datentypen der Ausdrücke|Aktion des Compilers|  
|`Object`\-Ausdruck enthält einen numerischen Wert, und der andere Ausdruck ist ein numerischer Datentyp|Wenn `Option Strict` auf `On` festgelegt ist, wird ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` auf `Off` festgelegt ist, wird eine Addition ausgeführt.|  
|`Object`\-Ausdruck enthält einen numerischen Wert, und der andere Ausdruck ist vom Typ `String`|Wenn `Option Strict` auf `On` festgelegt ist, wird ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` auf `Off` festgelegt ist, wird `String` implizit in `Double` konvertiert und addiert.<br /><br /> Wenn `String` nicht in `Double` konvertiert werden kann, wird eine <xref:System.InvalidCastException>\-Ausnahme ausgelöst.|  
|`Object`\-Ausdruck enthält eine Zeichenfolge, und der andere Ausdruck ist ein numerischer Datentyp|Wenn `Option Strict` auf `On` festgelegt ist, wird ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` auf `Off` festgelegt ist, wird `Object` implizit in `Double` konvertiert und addiert.<br /><br /> Wenn `Object` nicht in `Double` konvertiert werden kann, wird eine <xref:System.InvalidCastException>\-Ausnahme ausgelöst.|  
|`Object`\-Ausdruck enthält eine Zeichenfolge, und der andere Ausdruck ist vom Typ `String`|Wenn `Option Strict` auf `On` festgelegt ist, wird ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` auf `Off` festgelegt ist, wird `Object` implizit in `String` konvertiert und verkettet.|  
  
 Wenn beide Ausdrücke `Object`\-Ausdrücke sind, führt Visual Basic die folgenden Aktionen \(nur `Option Strict Off`\) aus.  
  
|||  
|-|-|  
|Datentypen der Ausdrücke|Aktion des Compilers|  
|Beide `Object`\-Ausdrücke enthalten numerische Werte|Addition|  
|Beide `Object`\-Ausdrücke weisen den Typ `String` auf|Verkettung|  
|Ein `Object`\-Ausdruck enthält einen numerischen Wert, und der andere enthält eine Zeichenfolge|Die `Object`\-Zeichenfolge wird implizit in `Double` konvertiert und addiert.<br /><br /> Wenn `Object` nicht in einen numerischen Wert konvertiert werden kann, wird eine <xref:System.InvalidCastException>\-Ausnahme ausgelöst.|  
  
 Wenn einer der `Object`\-Ausdrücke [Nothing](../../../visual-basic/language-reference/nothing.md) oder <xref:System.DBNull> ergibt, behandelt der Operator `+` den Ausdruck als `String` mit dem Wert "".  
  
> [!NOTE]
>  Wenn Sie den Operator `+` verwenden, können Sie nicht immer bestimmen, ob eine Addition oder eine Zeichenverkettung erfolgt.  Verwenden Sie für die Verkettung den Operator `&`, um Mehrdeutigkeiten zu vermeiden und sich selbst dokumentierenden Code zu erhalten.  
  
## Überladen  
 Der Operator `+` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator `+` verwendet, um Zahlen zu addieren.  Wenn beide Operanden numerisch sind, berechnet Visual Basic das arithmetische Ergebnis.  Das arithmetische Ergebnis stellt die Summe der beiden Operanden dar.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 Sie können mit dem Operator `+` auch Zeichenfolgen verketten.  Wenn beide Operanden Zeichenfolgen sind, verkettet Visual Basic die Operanden.  Das Verkettungsergebnis ist eine einzige Zeichenfolge, bei der der Inhalt der beiden Operanden hintereinander angeordnet ist.  
  
 Wenn die Operanden unterschiedliche Typen sind, hängt das Ergebnis von der Einstellung der [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) ab.  Im folgenden Beispiel wird das Ergebnis veranschaulicht, wenn `Option Strict` auf `On` festgelegt ist.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 Im folgenden Beispiel wird das Ergebnis veranschaulicht, wenn `Option Strict` auf `Off` festgelegt ist.  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 Um Mehrdeutigkeiten zu vermeiden, sollten Sie für Verkettungen den Operator `&` anstelle von `+` verwenden.  
  
## Siehe auch  
 [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)   
 [Concatenation Operators](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)