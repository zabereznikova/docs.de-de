---
description: switch (C#-Referenz)
title: switch-Anweisung in C#
ms.date: 04/09/2019
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
ms.openlocfilehash: 20c1d9786eaa184088500cf1b37d33afc421b5e7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142023"
---
# <a name="switch-c-reference"></a>switch (C#-Referenz)

In diesem Artikel wird die `switch`-Anweisung vorgestellt. Informationen zum `switch`-Ausdruck (eingeführt in C# 8.0) finden Sie im Artikel zu [`switch`-Ausdrücken](../operators/switch-expression.md) im Abschnitt [Ausdrücke und Operatoren](../operators/index.md).

`switch` ist eine Auswahlanweisung, die einen einzelnen *switch-Abschnitt* zum Ausführen aus einer Liste von Kandidaten auswählt, die auf einem Mustertreffer mit dem *Vergleichsausdruck* basiert.

[!code-csharp[switch#1](~/samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]

Die Anweisung `switch` wird häufig als Alternative zu einem [if-else](if-else.md)-Konstrukt verwendet, wenn ein einzelner Ausdruck mit drei oder mehr Bedingungen getestet wird. Die folgende Anweisung `switch` bestimmt z.B., ob eine Variable des Typs `Color` einen von drei Werten hat:

[!code-csharp[switch#3](~/samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]

Dies entspricht dem folgenden Beispiel, das ein `if`-`else`-Konstrukt verwendet.

[!code-csharp[switch#3a](~/samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]

## <a name="the-match-expression"></a>Der Vergleichsausdruck

Der Vergleichsausdruck stellt den Wert bereit, mit dem die Muster in den Bezeichnungen `case` verglichen werden. Die Syntax lautet:

```csharp
   switch (expr)
```

In C# 6 und früher muss der Vergleichsausdruck ein Ausdruck sein, der einen Wert der folgenden Typen zurückgibt:

- Ein [char](../builtin-types/char.md)
- Eine [Zeichenfolge](../builtin-types/reference-types.md)
- Ein [bool](../builtin-types/bool.md)
- Ein [ganzzahliger](../builtin-types/integral-numeric-types.md) Wert wie `int` oder `long`.
- Ein [Enumerations](../builtin-types/enum.md)wert

Ab C# 7.0 kann der Vergleichsausdruck jeder Ausdruck sein, der nicht NULL ist.

## <a name="the-switch-section"></a>Der switch-Abschnitt

Eine `switch`-Anweisung enthält eine oder mehrere switch-Abschnitte. Jeder switch-Abschnitt enthält mindestens eine *case-Bezeichnung* (eine case- oder Standardbezeichnung) gefolgt von mindestens einer Anweisung. Die `switch`-Anweisung kann höchstens eine Standardbezeichnung in einem beliebigen switch-Abschnitt enthalten. Das folgende Beispiel zeigt eine einfache `switch`-Anweisung, die über drei switch-Abschnitte mit je zwei Anweisungen verfügt. Der zweite switch-Abschnitt enthält die Bezeichnungen `case 2:` und `case 3:`.

Eine `switch`-Anweisung kann eine beliebige Anzahl von switch-Abschnitten enthalten, und jeder Abschnitt kann eine oder mehrere case-Bezeichnungen haben, wie im folgend Beispiel gezeigt wird. Allerdings können zwei case-Bezeichnungen nicht denselben Ausdruck enthalten.

[!code-csharp[switch#2](~/samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]

Nur ein switch-Abschnitt einer switch-Anweisung wir ausgeführt. C# lässt nicht zu, dass die Ausführung von einem switch-Abschnitt zum nächsten fortgesetzt wird. Deshalb verursacht der folgende Code den Compilerfehler CS0163: „Das Steuerelement kann nicht von einer case-Bezeichnung (\<case label>) zur nächsten fortfahren.“

```csharp
switch (caseSwitch)
{
    // The following switch section causes an error.
    case 1:
        Console.WriteLine("Case 1...");
        // Add a break or other jump statement here.
    case 2:
        Console.WriteLine("... and/or Case 2");
        break;
}
```

Diese Anforderung wird normalerweise erfüllt, indem der switch-Abschnitt ausdrücklich durch Verwenden einer Anweisung [break](break.md), [goto](goto.md) oder [return](return.md) beendet wird. Der folgende Code ist jedoch auch gültig, da er sicherstellt, dass die Programmsteuerung nicht im switch-Abschnitt `default` fortfährt.

[!code-csharp[switch#4](~/samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]

Die Ausführung der Anweisungsliste im switch-Abschnitt mit einer case-Bezeichnung, die den Vergleichsausdruck vergleicht, beginnt mit der ersten Anweisung und durchläuft in der Regel die Anweisungsliste, bis eine jump-Anweisung erreicht wird, z.B. `break`, `goto case`, `goto label`, `return` oder `throw`. An diesem Punkt wird die Steuerung der `switch`-Anweisung entzogen oder an eine andere case-Bezeichnung übertragen. Wenn eine `goto`-Anweisung verwendet wird, muss sie die Steuerung an eine konstante Bezeichnung übergeben. Diese Einschränkung ist notwendig, da der Versuch, die Steuerung an eine nicht konstante Bezeichnung zu übergeben, unerwünschte Nebeneffekte haben kann, z.B. kann die Steuerung an eine nicht beabsichtigte Position im Code übergeben werden, oder es kann eine Endlosschleife entstehen.

## <a name="case-labels"></a>case-Bezeichnungen

Jede case-Bezeichnung gibt ein Muster an, mit dem der Vergleichsausdruck verglichen werden soll (die Variable `caseSwitch` in den vorherigen Beispielen). Wenn sie übereinstimmen, wird das Steuerelement an den switch-Abschnitt übertragen, der die **erste** übereinstimmende case-Bezeichnung enthält. Wenn keine case-Bezeichnung mit dem Vergleichsausdruck übereinstimmt, wird das Steuerelement an den Abschnitt mit der `default`-case-Bezeichnung übertragen, sofern vorhanden. Wenn kein `default`-case vorhanden ist, werden keine Anweisungen in jeglichen switch-Abschnitten ausgeführt, und ein Steuerelement wird außerhalb der `switch`-Anweisung übertragen.

Informationen zur `switch`-Anweisung und zum Musterabgleich finden Sie im Abschnitt [Musterabgleich mit der `switch`-Anweisung](#pattern-matching with-the-switch-statement).

Da C# 6 nur das Konstantenmuster unterstützt und die Wiederholung von Konstantenwerten nicht erlaubt, definieren case-Bezeichnungen exklusive Werte, und nur ein Muster kann mit dem Vergleichsausdruck übereinstimmen. Daher ist die Reihenfolge, in der die `case`-Anweisungen auftauchen, unwichtig.

Da in C# 7.0 jedoch andere Muster unterstützt werden, müssen case-Bezeichnungen keine gegenseitig ausschließenden Werte definieren, und mehrere Muster können mit dem Vergleichsausdruck übereinstimmen. Da nur die Anweisungen im ersten switch-Abschnitt ausgeführt werden, die das übereinstimmende Muster enthalten, ist die Reihenfolge, in der `case`-Anweisungen erscheinen, nun wichtig. Wenn C# einen switch-Abschnitt erkennt, dessen case-Anweisung oder Anweisungen eine Teilmenge der vorherigen Anweisungen ist oder einer entsprechen, erzeugt der Abschnitt den Compilerfehler CS8120: „Der Parameter wurde bereits von einem vorherigen Parameter verarbeitet.“

Das folgende Beispiel veranschaulicht eine `switch`-Anweisung, die eine Reihe von sich nicht gegenseitig ausschließenden Mustern verwendet. Wenn Sie den switch-Abschnitt `case 0:` verschieben, sodass er nicht länger der erste Abschnitt in der `switch`-Anweisung ist, erzeugt C# einen Compilerfehler, da eine Ganzzahl, deren Wert 0 ist, eine Teilmenge aller Ganzzahlen ist, die dem von der `case int val`-Anweisung definierten Muster entspricht.

[!code-csharp[switch#5](~/samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]

Sie können dieses Problem beheben und die Compilerwarnung auf eine von zwei Arten entfernen:

- Durch das Ändern der Reihenfolge der switch-Abschnitte

- Durch Verwenden einer [when-Klausel](#the-case-statement-and-the-when-clause) in der `case`-Bezeichnung

## <a name="the-default-case"></a>Der `default`-Case

Der `default`-Case gibt den auszuführenden switch-Abschnitt an, wenn der Vergleichsausdruck nicht mit einer anderen `case`-Bezeichnung übereinstimmt. Wenn ein `default`-Case nicht vorhanden ist, und der Vergleichsausdruck nicht einer anderen `case`-Bezeichnung entspricht, fährt der Programmablauf mit der `switch`-Anweisung fort.

Der `default`-Case kann in beliebiger Reihenfolge in der `switch`-Anweisung auftauchen. Unabhängig von der Reihenfolge im Quellcode wird er immer zuletzt ausgewertet, nachdem alle `case`-Bezeichnungen ausgewertet wurden.

## <a name="pattern-matching-with-the-switch-statement"></a>Musterabgleich mit der `switch`-Anweisung

Jede `case`-Anweisung definiert ein Muster, das, wenn es mit dem Vergleichsausdruck übereinstimmt, dafür sorgt, dass seine enthaltenden switch-Abschnitte ausgeführt werden. Alle Versionen von C# unterstützen Konstantenmuster. Die übrigen Muster werden ab C# 7.0 unterstützt.

### <a name="constant-pattern"></a>Konstantenmuster

Das Konstantenmuster testet, ob der Vergleichsausdruck einer festgelegten Konstanten entspricht. Die Syntax lautet:

```csharp
   case constant:
```

wobei *constant* der zu testende Wert ist. *constant* kann eine der folgenden konstanten Ausdrücke sein:

- Ein [bool](../builtin-types/bool.md)-Literal: entweder `true` oder `false`
- Eine [ganzzahlige](../builtin-types/integral-numeric-types.md) Konstante wie `int`, `long` oder `byte`.
- Der Name einer deklarierten `const`-Variablen
- Eine Enumerationskonstante.
- Ein [char](../builtin-types/char.md)-Literal
- Ein [Zeichenfolgenliteral](../builtin-types/reference-types.md).

Der Konstantenausdruck wird wie folgt ausgewertet:

- Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.

- Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.

Das folgende Beispiel verwendet das Konstantenmuster, um zu bestimmen, ob ein bestimmtes Datum ein Wochenende, der erste Tag der Arbeitswoche, der letzte Tag der Arbeitswoche oder die Mitte der Arbeitswoche ist. Es bewertet die Eigenschaft <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> des heutigen Tags mit den Membern der <xref:System.DayOfWeek>-Enumeration.

[!code-csharp[switch#7](~/samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]

Im folgenden Beispiel wird das Konstantenmuster verwendet, um Benutzereingaben in einer Konsolenanwendung zu steuern, die eine automatische Kaffeemaschine simuliert.

[!code-csharp[switch#6](~/samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]

### <a name="type-pattern"></a>Typmuster

Das Typmuster ermöglicht die präzise Auswertung und Konvertierung des Typs. Wenn es mit der `switch`-Anweisung verwendet wird, um einen Musterabgleich auszuführen, wird getestet, ob eine Anweisung in einen bestimmten Typ konvertiert werden kann, und sofern dies möglich ist, wird es in eine Variable des Typs umgewandelt. Die Syntax lautet:

```csharp
   case type varname
```

bei der *Typ* der Name des Typs ist, in den das Ergebnis von *expr* konvertiert wird, und *varname* das Objekt ist, in das das Ergebnis von *expr* konvertiert wird, wenn der Abgleich erfolgreich ist Der Kompilierzeittyp von *expr* kann ab C# 7.1 ein generischen Parameter sein.

Der `case`-Ausdruck ist `true`, wenn eine der folgenden Aussagen zutrifft:

- *expr* ist eine Instanz des gleichen Typs wie *Typ*.

- *expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird. Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.

- *expr* hat einen Kompilierzeittyp, der eine Basisklasse von *type* ist, und *expr* hat einen Laufzeittyp,der *type* ist oder von *type* abgeleitet wurde. Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie es in der Deklaration des Typs definiert wurde. Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variable zugewiesen wird.

- *expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.

Wenn der case-Ausdruck TRUE ist, ist *varname* definitiv zugewiesen und hat nur innerhalb des switch-Abschnitts einen lokalen Geltungsbereich.

Beachten Sie, dass `null` nicht mit einem Typ übereinstimmt. Verwenden Sie folgende `case`-Bezeichnung, um `null` abzugleichen:

```csharp
case null:
```

Im folgenden Beispiel wird mithilfe des Typmusters Informationen über die verschiedenen Arten von Auflistungstypen bereitgestellt.

[!code-csharp[type-pattern#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]

Anstelle von `object` könnten Sie eine generische Methode erstellen, indem Sie den Typ der Sammlung als Typparameter verwenden, wie im folgenden Code gezeigt:

[!code-csharp[type-pattern#3](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern3.cs#1)]

Die generische Version unterscheidet sich auf zwei Arten vom ersten Beispiel. Zunächst können Sie den `null`-Case verwenden. Sie können keinen konstanten Case verwenden, da der Compiler nicht jeden beliebigen Typ `T` in einen anderen Typ als `object` konvertieren kann. Was ein `default`-Case war, ist jetzt ein `object` ungleich NULL. Das bedeutet, dass der `default`-Case nur `null` ergibt.

Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden. Die Verwendung des Typmusterabgleichs erzeugt einen kompakteren, lesbaren Code, indem nicht mehr getestet werden muss, ob das Ergebnis einer Umwandlung `null` ist, oder um wiederholte Umwandlungen auszuführen.

[!code-csharp[type-pattern2#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]

## <a name="the-case-statement-and-the-when-clause"></a>Die `case`-Anweisung und die `when`-Klausel

Da sich case-Anweisungen ab C# 7.0 nicht gegenseitig ausschließen müssen, können Sie eine `when`-Klausel hinzufügen, um eine zusätzliche Bedingung anzugeben, die erfüllt werden muss, damit die case-Anweisung als TRUE ausgewertet wird. Die `when`-Klausel kann ein beliebiger Ausdruck sein, der einen booleschen Wert zurückgibt.

Im folgenden Beispiel wird eine `Shape`-Basisklasse, eine `Rectangle`-Klasse, die von `Shape` abgeleitet wird, und eine `Square`-Klasse, die von `Rectangle` abgeleitet wird, definiert. Die `when`-Klausel wird verwendet, um sicherzustellen, dass `ShowShapeInfo` ein `Rectangle`-Objekt, dem eine gleiche Länge und Breite zugewiesen wurde, wie ein `Square` behandelt, selbst wenn es nicht als ein `Square`-Objekt instanziiert wurde. Diese Methode versucht weder Informationen über ein Objekt anzuzeigen, das `null` ist, noch über eine Form, deren Bereich NULL ist.

[!code-csharp[when-clause#1](~/samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]

Beachten Sie, dass in diesem Beispiel die `when`-Klausel, die zu prüfen versucht, ob ein `Shape`-Objekt `null` ist, nicht ausgeführt wird. Das richtige Typmuster, um auf `null` zu testen, ist `case null:`.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [Die switch-Anweisung](~/_csharplang/spec/statements.md#the-switch-statement) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [if-else](if-else.md)
- [Mustervergleich](../../pattern-matching.md)
