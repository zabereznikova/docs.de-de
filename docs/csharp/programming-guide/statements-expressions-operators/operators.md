---
title: Operatoren (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 76371985e340945793310247ec48d9b0cb747aed
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="operators-c-programming-guide"></a>Operatoren (C#-Programmierhandbuch)
In C# ist ein *Operator* ein Programmelement, das auf einen oder mehrere *Operanden* in einem Ausdruck oder einer Anweisung angewendet wird. Operatoren mit einem Operanden, z. B. der Inkrementoperator (`++`) oder `new`, werden als *unäre* Operatoren bezeichnet. Operatoren mit zwei Operanden, z. B. arithmetische Operatoren (`+`,`-`,`*`,`/`), werden als *binäre* Operatoren bezeichnet. Der bedingte Operator (`?:`) verfügt über drei Operanden. Er ist der einzige ternäre Operator in C#.  
  
 Die folgende C#-Anweisung enthält einen einzelnen unären Operator und einen einzigen Operanden. Der Inkrementoperator `++`ändert den Wert des Operanden `y`.  
  
 [!code-csharp[csProgGuideStatements#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/operators_1.cs)]  
  
 Die folgende C#-Anweisung enthält zwei binäre Operatoren mit jeweils zwei Operanden. Die Operanden des Zuweisungsoperators `=`sind die ganzzahlige Variable `y` und der Ausdruck `2 + 3` . Der Ausdruck `2 + 3` selbst besteht aus dem Additionsoperator und zwei Operanden: `2` und `3`.  
  
 [!code-csharp[csProgGuideStatements#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/operators_2.cs)]  
  
## <a name="operators-evaluation-and-operator-precedence"></a>Operatoren, Evaluierung und Operatorrangfolge  
 Ein Operand kann ein gültiger Ausdruck sein, der aus beliebig langem Code zusammengesetzt ist, und kann eine beliebige Anzahl von Unterausdrücken enthalten. In einem Ausdruck mit mehreren Operatoren wird die Reihenfolge, in der die Operatoren angewendet werden, von der *Operatorrangfolge*, der *Assoziativität*und von Klammern bestimmt.  
  
 Jeder Operator verfügt über einen definierten Vorrang. In einem Ausdruck, der mehrere Operatoren mit verschiedenen Rangfolgenebenen enthält, bestimmt die Rangfolge der Operatoren die Reihenfolge, in der die Operatoren ausgewertet werden. Beispielsweise weist die folgende Anweisung `n1`3 zu.  
  
 `n1 = 11 - 2 * 4;`  
  
 Die Multiplikation wird zuerst ausgeführt, da Multiplikation Vorrang vor Subtraktion enthält.  
  
 In der folgenden Tabelle werden die Operatoren basierend auf dem Typ der Operation, die sie ausführen, in Kategorien unterteilt. Die Kategorien sind entsprechend der Rangfolge aufgelistet.  
  
 **Primäre Operatoren**  
  
|Ausdruck|description|  
|----------------|-----------------|  
|x[.](../../../csharp/language-reference/operators/member-access-operator.md)y<br /><br /> x?.y|Memberzugriff<br /><br /> Bedingter Memberzugriff|  
|f[(x)](../../../csharp/language-reference/operators/invocation-operator.md)|Methoden- und Delegataufruf|  
|a[&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md)<br /><br /> a?[x]|Array- und Indexerzugriff<br /><br /> Bedingter Array- und Indexerzugriff|  
|x[++](../../../csharp/language-reference/operators/increment-operator.md)|Postinkrement|  
|x[--](../../../csharp/language-reference/operators/decrement-operator.md)|Postdekrement|  
|[new](../../../csharp/language-reference/keywords/new-operator.md) T(...)|Objekt- und Delegaterstellung|  
|`new` T(...){...}|Objekterstellung mit Initialisierern. Siehe [Objekt- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).|  
|`new` {...}|Anonymer Objektinitialisierer. Siehe [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).|  
|`new` T[...]|Arrayerstellung. Siehe [Arrays](../../../csharp/programming-guide/arrays/index.md).|  
|[typeof](../../../csharp/language-reference/keywords/typeof.md)(T)|Abrufen des System.Type-Objekts für T|  
|[checked](../../../csharp/language-reference/keywords/checked.md)(x)|Auswerten von Ausdrücken in geprüftem Kontext|  
|[unchecked](../../../csharp/language-reference/keywords/unchecked.md)(x)|Auswerten von Ausdrücken in nicht geprüftem Kontext|  
|[default](../../../csharp/language-reference/keywords/default.md) (T)|Abrufen des Standardwerts vom Typ T|  
|[delegate](../../../csharp/language-reference/keywords/delegate.md) {}|Anonyme Funktion (anonyme Methode)|  
  
 **Unäre Operatoren**  
  
|Ausdruck|description|  
|----------------|-----------------|  
|[+](../../../csharp/language-reference/operators/addition-operator.md)x|Identität|  
|[-](../../../csharp/language-reference/operators/subtraction-operator.md)x|Negation|  
|[\!](../../../csharp/language-reference/operators/logical-negation-operator.md)x|Logische Negation|  
|[~](../../../csharp/language-reference/operators/bitwise-complement-operator.md)x|Bitweise Negation|  
|[++](../../../csharp/language-reference/operators/increment-operator.md)x|Präinkrement|  
|[--](../../../csharp/language-reference/operators/decrement-operator.md)x|Prädekrement|  
|[(T)](../../../csharp/language-reference/operators/invocation-operator.md)x|Explizites Konvertieren von x in den Typ T|  
  
 **Multiplikative Operatoren**  
  
|Ausdruck|description|  
|----------------|-----------------|  
|[*](../../../csharp/language-reference/operators/multiplication-operator.md)|Multiplikation|  
|[/](../../../csharp/language-reference/operators/division-operator.md)|Division|  
|[%](../../../csharp/language-reference/operators/modulus-operator.md)|Rest|  
  
 **Additive Operatoren**  
  
|Ausdruck|description|  
|----------------|-----------------|  
|x [+](../../../csharp/language-reference/operators/addition-operator.md) y|Addition, Zeichenfolgenverkettung, Delegatkombination|  
|x [-](../../../csharp/language-reference/operators/subtraction-operator.md) y|Subtraktion, Delegatentfernung|  
  
 **Schiebeoperatoren**  
  
|Ausdruck|description|  
|----------------|-----------------|  
|x [<\<](../../../csharp/language-reference/operators/left-shift-operator.md) y|Linksverschiebung|  
|x [>>](../../../csharp/language-reference/operators/right-shift-operator.md) y|Rechtsverschiebung|  
  
 **Relationale Operatoren und Typoperatoren**  
  
|Ausdruck|description|  
|----------------|-----------------|  
|x [\<](../../../csharp/language-reference/operators/less-than-operator.md) y|Kleiner als|  
|x [>](../../../csharp/language-reference/operators/greater-than-operator.md) y|Größer als|  
|x [\<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) y|Kleiner oder gleich|  
|x [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) y|Größer oder gleich|  
|x [is](../../../csharp/language-reference/keywords/is.md) T|Gibt true zurück, wenn x gleich T ist, andernfalls false.|  
|x [as](../../../csharp/language-reference/keywords/as.md) T|Gibt x als T typisiert zurück, oder NULL, wenn x ungleich T ist.|  
  
 **Gleichheitsoperatoren**  
  
|Ausdruck|description|  
|----------------|-----------------|  
|x [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) y|Gleich|  
|x [!=](../../../csharp/language-reference/operators/not-equal-operator.md) y|Ungleich|  
  
 **Logische, bedingte und NULL-Operatoren**  
  
|Kategorie|Ausdruck|description|  
|--------------|----------------|-----------------|  
|Logisches AND|x [&](../../../csharp/language-reference/operators/and-operator.md) y|Ganzzahliges bitweises AND, boolesches logisches AND|  
|Logisches XOR|x [^](../../../csharp/language-reference/operators/xor-operator.md) y|Ganzzahliges bitweises XOR, boolesches logisches XOR|  
|Logisches OR|x [&#124;](../../../csharp/language-reference/operators/or-operator.md) y|Ganzzahliges bitweises OR, boolesches logisches OR|  
|Bedingtes AND|x [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y|Wertet y nur aus, wenn x den Wert true hat.|  
|Bedingtes OR|x [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) y|Wertet y nur aus, wenn x den Wert false hat.|  
|NULL-Sammeloperator|x [??](../../../csharp/language-reference/operators/null-coalescing-operator.md) y|Ergibt y, wenn x den Wert NULL hat, andernfalls x.|  
|Bedingt|x [?](../../../csharp/language-reference/operators/conditional-operator.md) y : z|Wird zu y ausgewertet, wenn x den Wert true hat, und zu z, wenn x den Wert false hat.|  
  
 **Zuweisungsoperatoren und anonyme Operatoren**  
  
|Ausdruck|description|  
|----------------|-----------------|  
|[=](../../../csharp/language-reference/operators/assignment-operator.md)|Zuweisung|  
|x op= y|Verbundzuweisung. Unterstützt diese Operatoren: [+=](../../../csharp/language-reference/operators/addition-assignment-operator.md), [-=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md), [*=](../../../csharp/language-reference/operators/multiplication-assignment-operator.md), [/=](../../../csharp/language-reference/operators/division-assignment-operator.md), [%=](../../../csharp/language-reference/operators/modulus-assignment-operator.md), [&=](../../../csharp/language-reference/operators/and-assignment-operator.md), [&#124;=](../../../csharp/language-reference/operators/or-assignment-operator.md), [!=](../../../csharp/language-reference/operators/not-equal-operator.md), [<\<=](../../../csharp/language-reference/operators/left-shift-assignment-operator.md), [>>=](../../../csharp/language-reference/operators/right-shift-assignment-operator.md).|  
|(T x) [=>](../../../csharp/language-reference/operators/lambda-operator.md) y|Anonyme Funktion (Lambda-Ausdruck)|  
  
## <a name="associativity"></a>Assoziativität  
 Wenn ein Ausdruck zwei oder mehr Operatoren mit demselben Rang enthält, wird die Auswertungsreihenfolge anhand des Assoziativitätsgesetzes festgelegt. Linksassoziative Operatoren werden von links nach rechts ausgewertet. `x * y / z` wird beispielsweise als `(x * y) / z`ausgewertet. Rechtsassoziative Operatoren werden von rechts nach links ausgewertet. Beispielsweise ist der Zuweisungsoperator rechtsassoziativ. Falls nicht, würde der folgende Code zu einem Fehler führen.  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 Ein weiteres Beispiel für einen rechtsassoziativen Operator ist der ternäre Operator ([?:](../../../csharp/language-reference/operators/conditional-operator.md)). Die meisten binäre Operatoren sind linksassoziativ.  
  
 Unabhängig davon, ob Operatoren in einem Ausdruck linksassoziativ oder rechtsassoziativ sind, werden zuerst die Operanden aller Ausdrücke von links nach rechts ausgewertet. Die folgenden Beispiele veranschaulichen die Auswertungsreihenfolge von Operatoren und Operanden.  
  
|Anweisung|Reihenfolge der Auswertung|  
|---------------|-------------------------|  
|`a = b`|a, b, =|  
|`a = b + c`|a, b, c, +, =|  
|`a = b + c * d`|a, b, c, d, *, +, =|  
|`a = b * c + d`|a, b, c, *, d, +, =|  
|`a = b - c + d`|a, b, c, -, d, +, =|  
|`a += b -= c`|a, b, c, -=, +=|  
  
## <a name="adding-parentheses"></a>Hinzufügen von Klammern  
 Sie können die Reihenfolge ändern, die von Operatorenrangfolge und Assoziativität festgelegt wird, indem Sie Klammern verwenden. Beispielsweise wird `2 + 3 * 2` gewöhnlich als 8 ausgewertet, da Multiplikationsoperatoren Vorrang gegenüber additiven Operatoren besitzen. Wenn Sie jedoch den Ausdruck als `(2 + 3) * 2`schreiben, wird die Addition vor der Multiplikation ausgewertet, und das Ergebnis ist 10. Die folgenden Beispiele veranschaulichen die Auswertungsreihenfolge der in Klammern gesetzten Ausdrücke. Wie in den vorherigen Beispielen werden die Operanden ausgewertet, bevor der Operator angewendet wird.  
  
|Anweisung|Reihenfolge der Auswertung|  
|---------------|-------------------------|  
|`a = (b + c) * d`|a, b, c, +, d, *, =|  
|`a = b - (c + d)`|a, b, c, d, +, -, =|  
|`a = (b + c) * (d - e)`|a, b, c, +, d, e, -, *, =|  
  
## <a name="operator-overloading"></a>Operatorüberladung  
 Sie können das Verhalten der Operatoren für benutzerdefinierte Klassen und Strukturen ändern. Dieser Prozess wird als *Operatorüberladung*bezeichnet. Weitere Informationen finden Sie unter [Überladbare Operatoren](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md).  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md) und [C#-Operatoren](../../../csharp/language-reference/operators/index.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Anweisungen, Ausdrücke und Operatoren](../../../csharp/programming-guide/statements-expressions-operators/index.md)
