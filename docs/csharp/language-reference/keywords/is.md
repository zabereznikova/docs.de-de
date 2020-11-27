---
description: is – C#-Referenz
title: is – C#-Referenz
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: d30ebfa2dc47265185a96514efbddc3e4937438c
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982393"
---
# <a name="is-c-reference"></a>is (C#-Referenz)

Der `is`-Operator überprüft, ob das Ergebnis eines Ausdrucks mit einem angegebenen Typ kompatibel ist, oder (ab C# 7.0) testet einen Ausdruck anhand eines Musters. Informationen zu Typtests des `is`-Operators finden Sie im Abschnitt [is-Operator](../operators/type-testing-and-cast.md#is-operator) des Artikels [Typtestoperatoren und Cast-Ausdrücke](../operators/type-testing-and-cast.md).

## <a name="pattern-matching-with-is"></a>Musterabgleich mit `is`

Ab C# 7.0 unterstützen die Anweisungen `is` und [switch](switch.md) den Musterabgleich. Das Schlüsselwort `is` unterstützt folgende Muster:

- Das [Typmuster](#type-pattern), das prüft, ob ein Ausdruck in einen angegebenen Typ konvertiert werden kann, und die Variable, sofern die Konvertierung möglich ist, in eine Variable dieses Typs umwandelt.
- Das [Konstantenmuster](#constant-pattern), das prüft, ob ein Ausdruck einen angegebenen konstanten Wert ergibt.
- Das [Variablenmuster](#var-pattern), eine Übereinstimmung, die immer erfolgreich ausführt wird und den Wert eines Ausdrucks an eine neue lokale Variable bindet.

### <a name="type-pattern"></a>Typmuster

Wenn Sie das Typmuster verwenden, um einen Musterabgleich durchzuführen, prüft `is`, ob ein Ausdruck in einen angegebenen Typen konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typ um. Dies ist eine einfach Erweiterung der `is`-Anweisung, die eine präzise Auswertung und Konvertierung des Typs ermöglicht. Die allgemeine Form des Typmusters `is` ist:

```csharp
   expr is type varname
```

Hier ist *expr* ein Ausdruck, der eine Instanz eines beliebigen Typen ergibt, *Typ* ist der Name des Typen, in den das Ergebnis von *expr* konvertiert werden soll, und *varname* ist das Objekt, in das das Ergebnis von *expr* konvertiert wird, wenn der `is`-Test `true` ist.

Der Ausdruck `is` ist `true`, wenn *expr* nicht `null` ist und eine der folgenden Bedingungen vorliegt:

- *expr* ist eine Instanz des gleichen Typs wie *Typ*.
- *expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird. Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.
- *expr* hat einen Kompilierzeittyp, der eine Basisklasse von *type* ist, und *expr* hat einen Laufzeittyp,der *type* ist oder von *type* abgeleitet wurde. Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert. Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variable zugewiesen wird.
- *expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.

Beginnend mit C# 7.1 kann *expr* einen Kompilierzeittyp haben, der durch einen generischen Typparameter und seine Einschränkungen definiert ist.

Wenn *expr*`true` ist und `is` mit der `if`-Anweisung verwendet wird, wird *varname* nur innerhalb der `if`-Anweisung zugewiesen. Der Bereich von *varname* stammt aus dem `is`-Ausdruck am Ende des Block, der die `if`-Anweisung umschließt. Bei Verwendung von *varname* an einer anderen Stelle wird ein Kompilierzeitfehler für die Verwendung einer nicht zugewiesenen Variablen erzeugt.

Im folgenden Beispiel wird das `is`-Typmuster verwendet, um die Implementierung der Methode <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> des Typs bereitzustellen.

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden. Die Verwendung des Typenmusterabgleichs erzeugt einen kompakteren, lesbaren Code, da nicht mehr geprüft werden muss, ob das Ergebnis einer Umwandlung `null` ist.  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

Das Typmuster `is` erstellt zusätzlich kompakteren Code, wenn der Typ eines Werttyps bestimmt wird. Im folgenden Beispiel wird das Typmuster `is` verwendet, um zu bestimmen, ob ein Objekt eine Instanz von `Person` oder `Dog` ist, bevor der Wert einer passenden Eigenschaft angezeigt wird.

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

Der gleichwertige Code erfordert ohne einen Musterabgleich eine gesonderte Zuweisung, die eine explizite Umwandlung beinhaltet.

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a>Konstantenmuster

Beim Durchführen eines Musterabgleichs mit einem Konstantenmuster prüft `is`, ob ein Ausdruck einer angegebenen Konstanten entspricht. In C# 6 und früheren Versionen wird das Konstantenmuster von der Anweisung [switch](switch.md) unterstützt. Ab C# 7.0 wird es ebenfalls von der Anweisung `is` unterstützt. Die Syntax sieht wie folgt aus:

```csharp
   expr is constant
```

Hier ist *expr* der auszuwertende Ausdruck, und *constant* ist der Wert, auf den geprüft werden soll. *constant* kann eine der folgenden konstanten Ausdrücke sein:

- Ein Literalwert

- Der Name einer deklarierten `const`-Variablen

- Eine Enumerationskonstante.

Der Konstantenausdruck wird wie folgt ausgewertet:

- Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.

- Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.  

Im folgenden Beispiel werden Typ- und Konstantenmuster miteinander vereint, um zu prüfen, ob ein Objekt eine `Dice`-Instanz ist; ist dem so, wird geprüft, ob der Wert eines Würfelvorgangs 6 ist.

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

Die Überprüfung auf `null` kann mithilfe des Konstantenmusters erfolgen. Das Schlüsselwort `null` wird von der `is`-Anweisung unterstützt. Die Syntax sieht wie folgt aus:

```csharp
   expr is null
```

Das folgende Beispiel zeigt einen Vergleich von `null`-Überprüfungen:

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

Der Ausdruck `x is null` wird für Referenztypen und Nullwerte zulassende Werttypen unterschiedlich berechnet. Für Nullwerte zulassende Werttypen wird <xref:System.Nullable%601.HasValue?displayProperty=nameWithType> verwendet. Für Referenztypen wird `(object)x == null` verwendet.

### <a name="var-pattern"></a>var-Muster

Eine Musterübereinstimmung mit einem `var`-Muster wird immer erfolgreich ausgeführt. Die Syntax sieht wie folgt aus:

```csharp
   expr is var varname
```

Hier wird der Wert von *expr* immer einer lokalen Variablen mit dem Namen *varname* zugewiesen. *varname* ist eine Variable desselben Typs wie der Kompilierzeittyp *expr*.

Wenn *expr* zu `null` ausgewertet wird, ergibt der `is`-Ausdruck `true` und weist `null` zu *varname* zu. Das var-Muster ist eine der wenigen Verwendungen von `is`, die `true` für einen `null`-Wert erzeugt.

Sie können das `var`-Muster verwenden, um eine temporäre Variable innerhalb eines booleschen Ausdrucks zu erstellen, wie das folgende Beispiel zeigt:

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

Im vorhergehenden Beispiel wird die temporäre Variable verwendet, um das Ergebnis einer aufwendigen Operation zu speichern. Die Variable kann dann mehrfach verwendet werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation
  
Weitere Informationen finden Sie im Abschnitt [is-Operator](~/_csharplang/spec/expressions.md#the-is-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) sowie in den folgenden Vorschlägen für C#:

- [Mustervergleich](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [Musterabgleich mit Generics](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Schlüsselwörter](index.md)
- [Typtest- und Umwandlungsoperatoren](../operators/type-testing-and-cast.md)
