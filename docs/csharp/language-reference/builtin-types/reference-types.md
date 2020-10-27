---
title: Integrierte Verweistypen – C#-Referenz
description: Hier erhalten Sie Informationen zu Verweistypen mit C#-Schlüsselwörtern, die Sie zu deren Deklaration verwenden können.
ms.date: 06/25/2019
f1_keywords:
- object_CSharpKeyword
- object
- delegate_CSharpKeyword
- delegate
- dynamic_CSharpKeyword
- string
- string_CSharpKeyword
helpviewer_keywords:
- object keyword [C#]
- delegate keyword [C#]
- function pointers [C#]
- dynamic [C#]
- dynamic keyword [C#]
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.openlocfilehash: c2c03f47babd9ccf87eb60d33b9d65d1a9c82e2e
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223520"
---
# <a name="built-in-reference-types-c-reference"></a>Integrierte Verweistypen (C#-Referenz)

C# enthält eine Reihe von integrierten Verweistypen. Diese enthalten Schlüsselwörter oder Operatoren, die Synonyme für einen Typ in der .NET-Bibliothek sind.

## <a name="the-object-type"></a>den Objekttyp

Der `object`-Typ ist ein Alias für <xref:System.Object?displayProperty=nameWithType> in .NET. Im vereinheitlichen Typsystem von C# erben alle Typen, vordefiniert und benutzerdefiniert sowie Verweis- und Werttypen, direkt oder indirekt von <xref:System.Object?displayProperty=nameWithType>. Sie können Werte eines beliebigen Typs Variablen des Typs `object` zuweisen. Diesem Standardwert kann mithilfe des Literals `null` eine beliebige `object`-Variable zugewiesen werden. Wenn eine Variable eines Werttyps in ein Objekt konvertiert wird, gilt es als *geschachtelt* . Wenn eine Variable des Typs `object` in ein Wertobjekt konvertiert wird, gilt es als *nicht geschachtelt* . Weitere Informationen finden Sie unter [Boxing und Unboxing](../../programming-guide/types/boxing-and-unboxing.md).

## <a name="the-string-type"></a>Der Zeichenfolgentyp

Der Typ `string` stellt eine Sequenz von Null oder mehr Unicode-Zeichen dar. `string` ist ein Alias für <xref:System.String?displayProperty=nameWithType> in .NET.

Obwohl `string` ein Verweistyp ist, werden die [Gleichheitsoperatoren`==` und `!=`](../operators/equality-operators.md#string-equality) zum Vergleichen der Werte von `string`-Objekten, nicht von Verweisen, definiert. Dadurch wird das Testen auf Zeichenfolgengleichheit intuitiver. Beispiel:

```csharp-interactive
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine(object.ReferenceEquals(a, b));
```

Dies zeigt TRUE und anschließend FALSE an, weil der Inhalt der Zeichenfolgen gleich sind. Jedoch verweisen `a` und `b` nicht auf die gleiche Zeichenfolgeninstanz.

Der [Operator „+“](../operators/addition-operator.md#string-concatenation) verkettet Zeichenfolgen:

```csharp
string a = "good " + "morning";
```

Dadurch wird ein Zeichenfolgenobjekt erstellt, das „Guten Morgen“ enthält.

Zeichenfolgen sind *unveränderlich* . Die Inhalte eines Zeichenfolgenobjekts können nicht geändert werden, nachdem ein Objekt erstellt wurde, obwohl die Syntax den Eindruck erweckt, dass es machbar wäre. Wenn Sie z. B. diesen Code schreiben, erstellt der Compiler tatsächlich ein neues Zeichenfolgenobjekt, um die neue Zeichensequenz zu speichern. Das neue Objekt wird `b` zugewiesen. Der Speicherplatz, der `b` zugeordnet wurde (sofern die Zeichenfolge „h“ enthalten war), hat dann Anspruch auf die Garbage Collection.

```csharp
string b = "h";
b += "ello";
```

Der -`[]` [Operator](../operators/member-access-operators.md#indexer-operator-) kann für schreibgeschützten Zugriff auf einzelne Zeichen einer Zeichenfolge verwendet werden: Gültige Indexwerte beginnen bei `0` und müssen kleiner als die Länge der Zeichenfolge sein:

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

Auf gleiche Weise kann der `[]`-Operator auch für das Durchlaufen jedes Zeichens in der Zeichenfolge verwendet werden:

```csharp-interactive
string str = "test";

for (int i = 0; i < str.Length; i++)
{
  Console.Write(str[i] + " ");
}
// Output: t e s t
```

Zeichenfolgenliterale sind Typ `string` und können in zwei Formaten geschrieben werden: in Anführungszeichen und mit `@`. Zeichenfolgenliterale in Anführungszeichen werden in doppelte Anführungszeichen (") eingeschlossen:

```csharp
"good morning"  // a string literal
```

Zeichenfolgenliterale können jeden Zeichenliteral enthalten. Escapesequenzen sind enthalten. Im folgenden Beispiel wird die Escapesequenz `\\` für den umgekehrten Schrägstrich, `\u0066` für den Buchstaben „f“ und `\n` für den Zeilenumbruch verwendet.

```csharp-interactive
string a = "\\\u0066\n F";
Console.WriteLine(a);
// Output:
// \f
//  F
```

> [!NOTE]
> Der Escapecode `\udddd` (wobei `dddd` eine vierstellige Zahl ist) stellt das Unicode-Zeichen U+`dddd` dar. Escapecodes aus achtstelligen Unicode werden auch erkannt: `\Udddddddd`.

[Wörtliche Zeichenfolgenliterale](../tokens/verbatim.md) beginnen mit `@` und sind ebenfalls in doppelte Anführungszeichen eingeschlossen. Beispiel:

```csharp
@"good morning"  // a string literal
```

Der Vorteil von wörtlichen Zeichenfolgen besteht darin, dass Escapesequenzen *nicht* verarbeitet werden, wodurch z. B. das Schreiben eines vollqualifizierten Windows-Dateinamens erleichtert wird:

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

Verdoppeln Sie das doppelte Anführungszeichen, um es in einer @-quoted-Zeichenfolge aufzunehmen:

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

## <a name="the-delegate-type"></a>Der Delegattyp

Die Deklaration eines Delegattyps ähnelt einer Methodensignatur. Er verfügt über einen Rückgabewert und eine beliebige Anzahl Parameter eines beliebigen Typs:

```csharp
public delegate void MessageDelegate(string message);
public delegate int AnotherDelegate(MyType m, long num);
```

In .NET stellen die Typen `System.Action` und `System.Func` generische Definitionen für zahlreiche allgemeine Delegaten bereit. Sie werden sehr wahrscheinlich keine neuen benutzerdefinierten Delegattypen definieren müssen. Stattdessen können Sie Instanziierungen der bereitgestellten generischen Typen erstellen.

Ein `delegate` ist ein Verweistyp, der verwendet werden kann, um eine benannte oder anonyme Methode zu kapseln. Delegaten entsprechen den Funktionszeigern in C++, sind jedoch typsicher und geschützt. Anwendungsmöglichkeiten von Delegaten finden Sie unter [Delegaten](../../programming-guide/delegates/index.md) und [Generische Delegaten](../../programming-guide/generics/generic-delegates.md). Delegaten bilden die Grundlage für [Ereignisse](../../programming-guide/events/index.md). Ein Delegat kann instanziiert werden, entweder durch Zuordnen mit einer benannten oder einer anonymen Methode.

Der Delegat muss mit einer Methode oder einem Lambda-Ausdruck instanziiert werden, der über einen kompatiblen Rückgabetypen und Eingabeparameter verfügt. Weitere Informationen zum Grad der Varianz, der in der Methodensignatur zulässig ist, finden Sie unter [Varianz bei Delegaten](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md). Für die Verwendung mit anonymen Methoden werden der Delegat und der Code, der mit ihm zugeordnet werden soll, zusammen deklariert.

## <a name="the-dynamic-type"></a>Der dynamische Typ

Der `dynamic`-Typ gibt an, dass durch die Verwendung der Variablen und Verweise auf die entsprechenden Member die Prüfung des Kompilierzeittyps umgangen wird. Stattdessen werden diese Vorgänge zur Laufzeit aufgelöst. Der `dynamic`-Typ vereinfacht den Zugriff auf COM-APIs, z. B. die Office Automation-APIs, auf dynamische APIs, beispielsweise IronPython-Bibliotheken und auf das HTML-Dokumentobjektmodell (Document Object Model, DOM).

Der Typ `dynamic` verhält sich in den meisten Fällen wie Typ `object`. Insbesondere können alle Ausdrücke, die nicht NULL sind, in den `dynamic`-Typ konvertiert werden. Der `dynamic`-Typ unterscheidet sich jedoch von `object` insofern, als dass Vorgänge, die Ausdrücke des Typs `dynamic` enthalten, nicht aufgelöst oder durch den Compiler typgeprüft werden. Der Compiler packt Informationen über den Vorgang. Diese Informationen werden später zur Evaluierung des Vorgangs zur Laufzeit verwendet. Als Teil dieses Prozesses werden Variablen des Typs `dynamic` in Variablen des Typs `object` kompiliert. Deshalb existiert der Typ `dynamic` nur zur Kompilierzeit und nicht zur Laufzeit.

Das folgende Beispiel vergleicht den Unterschied einer Variable des Typs `dynamic` mit einer Variable des Typs `object`. Um den Typ jeder Variable zur Kompilierzeit zu überprüfen, zeigen Sie mit dem Mauszeiger auf `dyn` oder `obj` in den `WriteLine`-Anweisungen. Kopieren Sie den folgenden Code in einen Editor, in dem IntelliSense verfügbar ist. IntelliSense zeigt **dynamic** für `dyn` und **object** für `obj`.

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

Die <xref:System.Console.WriteLine%2A>-Anweisungen zeigen die Laufzeittypen von `dyn` und `obj`. Zu diesem Zeitpunkt verfügen beide denselben Typ, Integer. Es wird die folgende Ausgabe generiert:

```console
System.Int32
System.Int32
```

Um den Unterschied zwischen `dyn` und `obj` zur Kompilierzeit anzuzeigen, fügen Sie die folgenden zwei Zeilen zwischen die Deklarationen und die `WriteLine`-Anweisungen im vorherigen Beispiel ein.

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 Es wird ein Kompilierfehler für den Versuch, einen Integer und ein Objekt im Ausdruck `obj + 3` einzufügen, ausgegeben. Es wird jedoch kein Fehler für `dyn + 3` gemeldet. Der Ausdruck, der `dyn` enthält, wird nicht zur Kompilierzeit überprüft, da der Typ von `dyn``dynamic` ist.

Das folgende Beispiel verwendet `dynamic` in einigen Deklarationen. Die `Main`-Methode unterscheidet auch die Typüberprüfung zur Kompilierzeit und die Laufzeittypüberprüfung.

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

### <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Schlüsselwörter](../keywords/index.md)
- [Ereignisse](../../programming-guide/events/index.md)
- [Verwenden von dynamischen Typen](../../programming-guide/types/using-type-dynamic.md)
- [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](../../../standard/base-types/best-practices-strings.md)
- [Grundlegende Zeichenfolgenoperationen](../../../standard/base-types/basic-string-operations.md)
- [Erstellen neuer Zeichenfolgen](../../../standard/base-types/creating-new.md)
- [Typtest- und Umwandlungsoperatoren](../operators/type-testing-and-cast.md)
- [Vorgehensweise: Sicheres Umwandeln mit Musterabgleich mit den Operatoren „as“ und „is“](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
