---
title: 'Nullable-Verweistypen: C#-Referenz'
description: Informationen zu Nullable-Verweistypen in C# und deren Verwendung
ms.date: 04/06/2020
ms.openlocfilehash: 274a613a8381a2b7718c9025f51aadb2eb32af36
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471862"
---
# <a name="nullable-reference-types-c-reference"></a>Nullable-Verweistypen (C#-Referenz)

> [!NOTE]
> Dieser Artikel behandelt Nullable-Verweistypen. Sie können auch [Nullable-Werttypen](nullable-value-types.md) deklarieren.

Nullable-Verweistypen sind ab C# 8.0 verfügbar, sofern der Code für *NULL-kompatiblen Kontext* aktiviert wurde. Nullable-Verweistypen, Warnungen bei statischer Analyse des NULL-Status und der [NULL-tolerante Operator](../operators/null-forgiving.md) sind optionale Sprachfeatures. Alle sind standardmäßig deaktiviert. Ein *NULL-kompatibler Kontext* wird auf Projektebene mithilfe von Buildeinstellungen oder im Code mithilfe von Pragmas festgelegt.

 In einem NULL-kompatiblen Kontext gilt Folgendes:

- Eine Variable mit dem Verweistyp `T` muss ohne NULL-Werte initialisiert werden, und ihr darf kein Wert zugewiesen werden, der `null` sein kann.
- Eine Variable mit dem Verweistyp `T?` kann mit `null` initialisiert oder `null` zugewiesen werden, muss jedoch vor der Dereferenzierung auf `null` geprüft werden.
- Eine `m`-Variable vom Typ `T?` wird als ungleich NULL betrachtet, wenn Sie den NULL-toleranten Operator wie in `m!` anwenden.

Die Unterschiede zwischen dem Non-Nullable-Verweistyp `T` und dem Nullable-Verweistyp `T?` werden so erzwungen, wie der Compiler die vorhergehenden Regeln interpretiert. Eine Variable vom Typ `T` und eine Variable vom Typ `T?` werden durch denselben .NET-Typ dargestellt. Im folgenden Beispiel werden eine Non-Nullable-Zeichenfolge und eine Nullable-Zeichenfolge deklariert. Anschließend wird der NULL-tolerante Operator verwendet, um einer Non-Nullable-Zeichenfolge einen Wert zuzuweisen:

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetCoreSyntax":::

Die Variablen `notNull` und `nullable` werden beide durch den <xref:System.String>-Typ dargestellt. Da Non-Nullable- und Nullable-Typen als derselbe Typ gespeichert werden, gibt es mehrere Speicherorte, an denen Nullable-Verweistypen nicht verwendet werden dürfen. Ein Nullable-Verweistyp kann generell nicht als Basisklasse oder implementierte Schnittstelle verwendet werden. Ein Nullable-Verweistyp kann nicht in Ausdrücken für Objekterstellung oder Typtests verwendet werden. Ein Nullable-Verweistyp kann nicht der Typ eines Memberzugriffsausdrucks sein. In den folgenden Beispielen werden diese Konstrukte veranschaulicht:

```csharp
public MyClass : System.Object? // not allowed
{
}

var nullEmpty = System.String?.Empty; // Not allowed
var maybeObject = new object?(); // Not allowed
try
{
    if (thing is string? nullableString) // not allowed
        Console.WriteLine(nullableString);
} catch (Exception? e) // Not Allowed
{
    Console.WriteLine("error");
}
```

## <a name="nullable-references-and-static-analysis"></a>Nullable-Verweise und statische Analyse

Die Beispiele im vorherigen Abschnitt veranschaulichen den Charakter von Nullable-Verweistypen. Nullable-Verweistypen sind keine neuen Klassentypen, sondern eher Annotationen zu vorhandenen Verweistypen. Der Compiler verwendet diese Annotationen, um potenzielle NULL-Verweisfehler in Ihrem Code zu finden. Für Non-Nullable-Verweistypen und Nullable-Verweistypen werden keine unterschiedlichen Runtimes verwendet. Der Compiler fügt keine Runtime hinzu, die auf Non-Nullable-Verweistypen prüft. Die Vorteile liegen in der Analyse zur Kompilierzeit. Der Compiler generiert Warnungen, die Ihnen helfen, potenzielle NULL-Fehler in Ihrem Code zu finden und zu beheben. Sie deklarieren Ihre Absicht, und der Compiler warnt Sie, wenn Ihr Code gegen diese Absicht verstößt.

In NULL-kompatiblem Kontext führt der Compiler eine statische Analyse für Variablen für Nullable- und Non-Nullable-Verweistypen durch. Der Compiler erfasst den NULL-Status jeder Verweisvariablen entweder als *not null* (nicht NULL) oder als *maybe null* (vielleicht NULL). Der Standardstatus eines Non-Nullable-Verweises ist *not null* (nicht NULL). Der Standardstatus eines Nullable-Verweises ist *maybe null* (vielleicht NULL).

Non-Nullable-Verweistypen können immer sicher dereferenziert werden, da ihr NULL-Status *not null* (nicht NULL) ist. Der Compiler erzwingt diese Regel, indem Warnungen ausgegeben werden, wenn ein Non-Nullable-Verweistyp nicht in einen Wert ungleich NULL initialisiert wird. Lokale Variablen müssen dort zugewiesen werden, wo sie auch deklariert werden. Jeder Konstruktor muss jedes Feld im Textkörper, in einem aufgerufenen Konstruktor oder mithilfe eines Feldinitialisierers zuweisen. Der Compiler gibt Warnungen aus, wenn ein Non-Nullable-Verweis einem Verweis zugeordnet wird, dessen Status *maybe null* (vielleicht NULL) ist. Da ein Non-Nullable-Verweis jedoch den Status *not null* (nicht NULL) hat, werden keine Warnungen ausgegeben, wenn diese Variablen dereferenziert werden.

Nullable-Verweistypen können initialisiert oder `null` zugewiesen werden. Daher muss bei der statischen Analyse bestätigt werden, dass eine Variable *not null* (nicht NULL) ist, bevor sie dereferenziert wird. Wenn feststeht wird, dass ein Nullable-Verweis *maybe null* (vielleicht NULL) ist, kann dieser keiner Non-Nullable-Verweisvariable zugewiesen werden. In der folgenden Klasse werden Beispiele für diese Warnungen veranschaulicht:

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetClassWithNullable":::

Im folgenden Codeausschnitt sehen Sie, an welcher Stelle der Compiler bei Verwendung dieser Klasse Warnungen ausgibt:

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetLocalWarnings":::

In den vorangehenden Beispielen wird die statische Analyse des Compilers veranschaulicht, mit der der NULL-Status von Verweisvariablen bestimmt wird. Der Compiler wendet Sprachregeln auf NULL-Prüfungen und -Zuweisungen an, um die Analyse mit Informationen zu versorgen.  Der Compiler kann keine Annahmen zur Semantik von Methoden oder Eigenschaften treffen. Wenn Sie Methoden aufzurufen, die NULL-Prüfungen durchführen, kann der Compiler nicht wissen, welche Methoden den NULL-Status einer Variablen beeinflussen. Es gibt einige Attribute, die Sie Ihren APIs hinzufügen können, um den Compiler über die Semantik von Argumenten und Rückgabewerten in Kenntnis zu setzen. Diese Attribute wurden auf viele gängige APIs in den .NET Core-Bibliotheken angewendet. Beispielsweise wurde <xref:System.String.IsNullOrEmpty%2A> aktualisiert, und der Compiler interpretiert diese Methode ordnungsgemäß als NULL-Prüfung. Weitere Informationen zu den Attributen, die für die statische Analyse des NULL-Status gelten, finden Sie im Artikel zu [Nullable-Attributen](../attributes/nullable-analysis.md).

## <a name="setting-the-nullable-context"></a>Festlegen des NULL-kompatiblen Kontexts

Es gibt zwei Möglichkeiten, den NULL-kompatiblen Kontext festzulegen. Auf Projektebene können Sie die Projekteinstellung `<Nullable>enable</Nullable>` hinzufügen. In einer einzelnen C#-Quelldatei können Sie das `#nullable enable`-Pragma hinzufügen, um den NULL-kompatiblen Kontext zu aktivieren. Weitere Informationen finden Sie im Artikel zum [Festlegen einer NULL-kompatiblen Strategie](../../nullable-migration-strategies.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Vorschlägen für die [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Nullwerte zulassende Verweistypen](~/_csharplang/proposals/csharp-8.0/nullable-reference-types.md)
- [Entwurf der Spezifikation für Nullable-Verweistypen](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Auf NULL festlegbare Werttypen](nullable-value-types.md)
