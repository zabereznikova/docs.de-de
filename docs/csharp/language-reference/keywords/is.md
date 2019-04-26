---
title: is – C#-Referenz
ms.custom: seodec18
ms.date: 04/09/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 9fb57caeafde9db5759300d938a85f4abf4d05f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672458"
---
# <a name="is-c-reference"></a>is (C#-Referenz)

Überprüft, ob ein Objekt mit einem angegebenen Typ kompatibel ist, oder gleicht ab C# 7.0 einen Ausdruck mit einem Muster ab.

## <a name="testing-for-type-compatibility"></a>Prüfen auf Typkompatibilität

Das `is`-Schlüsselwort wertet die Typkompatibilität zur Laufzeit aus. Es bestimmt, ob eine Instanz eines Objekts oder das Ergebnis eines Ausdrucks in einen angegebenen Typen konvertiert werden kann. Es besitzt die Syntax

```csharp
   expr is type
```

in der *expr* ein Ausdruck ist, der die Instanz eines Typs auswertet und *type* der Name des Typs, in den das Ergebnis von *expr* konvertiert werden soll. Die Anweisung `is` ist `true`, wenn *expr* nicht NULL ist, und das Objekt, das beim Auswerten des Ausdrucks entsteht, kann in *Typ* konvertiert werden; andernfalls gibt es `false` zurück.

Der folgende Code bestimmt beispielsweise, ob `obj` in eine Instanz des Typs `Person` umgewandelt werden kann:

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

Die Anweisung `is` ist TRUE, wenn:

- *expr* eine Instanz des gleichen Typs wie *Typ* ist.

- *expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird. Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.

- *expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird. Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert. Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.

- *expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.

Im folgenden Beispiel wird veranschaulicht, wie der Ausdruck `is` für jede dieser Konvertierungen `true` ergibt.

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

Das Schlüsselwort `is` generiert eine Kompilierzeitwarnung, wenn der Ausdruck immer entweder `true` oder `false` ist. Es berücksichtigt nur Verweis-, Boxing- und Unboxing-Konvertierungen; es berücksichtigt keine benutzerdefinierten Konvertierungen oder Konvertierungen, die von den [impliziten](implicit.md) und [expliziten](explicit.md) Operatoren eines Typs definiert wurden. Das folgende Beispiel generiert Warnungen, weil das Ergebnis der Konvertierung zur Kompilierzeit bekannt ist. Der Ausdruck `is` für Konvertierungen von `int` in `long` und `double` gibt FALSE zurück, da diese Konvertierungen vom [impliziten](implicit.md) Operator verarbeitet werden.

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

`expr` kann weder eine anonyme Methode noch ein Lambdaausdruck sein. Es kann ein anderer Ausdruck sein, der einen Wert zurückgibt. Im folgenden Beispiel wird `is` verwendet, um den Rückgabewert eines Methodenaufrufs auszuwerten.   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

Ab C# 7.0 können Sie den Musterabgleich mit dem [Typmuster](#type) verwenden, um präziseren Code zu schreiben, der die Anweisung `is` verwendet.

## <a name="pattern-matching-with-is"></a>Musterabgleich mit `is`

Ab C# 7.0 unterstützen die Anweisungen `is` und [switch](../../../csharp/language-reference/keywords/switch.md) den Musterabgleich. Das Schlüsselwort `is` unterstützt folgende Muster:

- Das [Typmuster](#type), das prüft, ob ein Ausdruck in einen bestimmten Typ konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typs um.

- Das [Konstantenmuster](#constant), das prüft, ob ein Ausdruck einen angegebenen konstanten Wert ergibt.

- Das [Variablenmuster](#var), eine Übereinstimmung, die immer erfolgreich ausführt wird und den Wert eines Ausdrucks an eine neue lokale Variable bindet. 

### <a name="a-nametype-type-pattern"></a><a name="type" />Typmuster

Wenn Sie das Typmuster verwenden, um einen Musterabgleich durchzuführen, prüft `is`, ob ein Ausdruck in einen angegebenen Typen konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typ um. Dies ist eine einfach Erweiterung der `is`-Anweisung, die eine präzise Auswertung und Konvertierung des Typs ermöglicht. Die allgemeine Form des Typmusters `is` ist:

```csharp
   expr is type varname 
```

Hier ist *expr* ein Ausdruck, der eine Instanz eines beliebigen Typen ergibt, *Typ* ist der Name des Typen, in den das Ergebnis von *expr* konvertiert werden soll, und *varname* ist das Objekt, in das das Ergebnis von *expr* konvertiert wird, wenn der `is`-Test `true` ist. 

Der Ausdruck `is` ist `true`, wenn *expr* nicht `null` ist und eine der folgenden Aussagen zutrifft:

- *expr* ist eine Instanz des gleichen Typs wie *Typ*.

- *expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird. Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.

- *expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird. Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert. Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.

- *expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.

Beginnend mit C# 7.1 kann *expr* einen Kompilierzeittyp haben, der durch einen generischen Typparameter und seine Einschränkungen definiert ist. 

Wenn *expr* `true` ist, und `is` mit der `if`-Anweisung verwendet wird, wird *varname* zugewiesen und ist nur lokal innerhalb der Anweisung `if` gültig.

Im folgenden Beispiel wird das `is`-Typmuster verwendet, um die Implementierung der Methode <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> des Typs bereitzustellen.

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden. Die Verwendung des Typenmusterabgleichs erzeugt einen kompakteren, lesbaren Code, da nicht mehr geprüft werden muss, ob das Ergebnis einer Umwandlung `null` ist.  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

Das Typmuster `is` erstellt zusätzlich kompakteren Code, wenn der Typ eines Werttyps bestimmt wird. Im folgenden Beispiel wird das Typmuster `is` verwendet, um zu bestimmen, ob ein Objekt eine Instanz von `Person` oder `Dog` ist, bevor der Wert einer passenden Eigenschaft angezeigt wird. 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

Der gleichwertige Code erfordert ohne einen Musterabgleich eine gesonderte Zuweisung, die eine explizite Umwandlung beinhaltet.

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><a name="constant" /> Konstantenmuster

Beim Durchführen eines Musterabgleichs mit einem Konstantenmuster prüft `is`, ob ein Ausdruck einer angegebenen Konstanten entspricht. In C# 6 und früheren Versionen wird das Konstantenmuster von der Anweisung [switch](switch.md) unterstützt. Ab C# 7.0 wird es ebenfalls von der Anweisung `is` unterstützt. Die Syntax lautet:

```csharp
   expr is constant
```

Hier ist *expr* der auszuwertende Ausdruck, und *constant* ist der Wert, auf den geprüft werden soll. *constant* kann einer der folgenden konstanten Ausdrücke sein: 

- Ein Literalwert.

- Der Name einer deklarierten `const`-Variable.

- Eine Enumerationskonstante.

Der konstante Ausdruck wird wie folgt ausgewertet:

- Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.

- Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.  

Im folgenden Beispiel werden Typ- und Konstantenmuster miteinander vereint, um zu prüfen, ob ein Objekt eine `Dice`-Instanz ist; ist dem so, wird geprüft, ob der Wert eines Würfelvorgangs 6 ist.

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

Die Überprüfung auf `null` kann mithilfe des Konstantenmusters erfolgen. Das Schlüsselwort `null` wird von der `is`-Anweisung unterstützt. Die Syntax lautet:

```csharp 
   expr is null
```

Das folgende Beispiel zeigt einen Vergleich von `null`-Überprüfungen:

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <a name="var" />Variablenmuster</a>

Das `var`-Muster ist ein Catch-All-Muster für jeden Typ bzw. jeden Wert. Der Wert von *expr* wird immer einer lokalen Variablen zugewiesen, deren Typ dem Kompilierzeittyp von *expr* entspricht. Das Ergebnis des `is`-Ausdrucks lautet immer `true`. Die Syntax lautet:

```csharp 
   expr is var varname
```

In folgendem Beispiel wird das Variablenmuster verwendet, um einen Ausdruck einer Variablen mit dem Namen `obj` zuzuweisen. Dann zeigt es den Wert und den Typ von `obj` an.

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)
- [typeof](../../../csharp/language-reference/keywords/typeof.md)
- [as](../../../csharp/language-reference/keywords/as.md)
- [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)
