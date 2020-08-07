---
title: Zeigertypen – C#-Programmierhandbuch
description: Erfahren Sie mehr über Zeigertypen. Hier finden Sie Beispiele für verschiedene Zeiger, Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 9c62a31f9a4a090fe56fb10ac45fe2f93f1b036e
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382034"
---
# <a name="pointer-types-c-programming-guide"></a>Zeigertypen (C#-Programmierhandbuch)

In einem unsicheren Kontext kann ein Typ sowohl ein Zeigertyp als auch ein Werttyp oder Verweistyp sein. Eine Zeigertypdeklaration erfolgt in einer der folgenden Formen:

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

Der Typ, der vor `*` in einem Zeigertyp angegeben wird, wird als **Verweistyp** bezeichnet. Nur ein [nicht verwalteter Typ](../../language-reference/builtin-types/unmanaged-types.md) kann ein Verweistyp sein.

Zeigertypen erben nicht von [object`object`, und es ist keine Konvertierung zwischen Zeigertypen und ](../../language-reference/builtin-types/reference-types.md) möglich. Weiterhin unterstützen Boxing und Unboxing keine Zeiger. Es ist jedoch möglich, Konvertierungen zwischen verschiedenen Zeigertypen sowie zwischen Zeigertypen und ganzzahligen Typen durchzuführen.

Wenn Sie mehrere Zeiger innerhalb ein- und derselben Deklaration deklarieren, wird das Sternchen (*) nur einmal mit dem zugrunde liegenden Typ notiert und nicht als Präfix für jeden Zeigernamen verwendet. Zum Beispiel:

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

Ein Zeiger kann nicht auf einen Verweis oder eine [Struktur](../../language-reference/builtin-types/struct.md) verweisen, die Verweise enthält, da ein Objektverweis auch dann in die Garbage Collection aufgenommen werden kann, wenn ein Zeiger darauf verweist. In der Garbage Collection wird nicht nachgehalten, ob von einem der Zeigertypen auf ein Objekt verwiesen wird.

Der Wert der Zeigervariablen vom Typ `myType*` ist die Adresse einer Variablen vom Typ `myType`. Im Folgenden finden Sie Beispiele für Zeigertypdeklarationen:

|Beispiel|Beschreibung|
|-------------|-----------------|
|`int* p`|`p` ist ein Zeiger auf einen ganzzahligen Wert.|
|`int** p`|`p` ist ein Zeiger auf einen Zeiger auf einen ganzzahligen Wert.|
|`int*[] p`|`p` ist ein eindimensionales Array von Zeigern auf ganzzahlige Werte.|
|`char* p`|`p` ist ein Zeiger auf eine char-Variable.|
|`void* p`|`p` ist ein Zeiger auf einen unbekannten Typ.|

Sie können den Zeigerdereferenzierungsoperator * verwenden, um auf den Inhalt an der Speicherstelle zuzugreifen, auf die die Zeigervariable zeigt. Betrachten Sie beispielsweise die folgende Deklaration:

```csharp
int* myVariable;
```

Der Ausdruck `*myVariable` kennzeichnet die `int`-Variable, die sich an der in `myVariable` enthaltenen Adresse befindet.

Es gibt mehrere Beispiele von Zeigern in den Themen [fixed-Anweisung](../../language-reference/keywords/fixed-statement.md) und [Zeigerkonvertierungen](./pointer-conversions.md). Im folgenden Beispiel wird die Verwendung des `unsafe`-Schlüsselworts und der `fixed`-Anweisung sowie die Vorgehensweise zum Erhöhen eines inneren Zeigers veranschaulicht.  Sie können diesen Code in die Hauptmethode einer Konsolenanwendung einfügen, um ihn auszuführen. Diese Beispiele müssen mithilfe der Compileroption [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.

[!code-csharp[Using pointer types](snippets/FixedKeywordExamples.cs#5)]

Der Dereferenzierungsoperator kann nicht auf Zeiger vom Typ `void*` angewendet werden. Sie können jedoch eine Umwandlung verwenden, um einen void-Zeiger in einen anderen Zeigertyp und umgekehrt zu konvertieren.

Ein Zeiger kann den Wert `null` annehmen. Die Anwendung des Dereferenzierungsoperators auf einen NULL-Zeiger führt zu einem in der Implementierung definierten Verhalten.

Die Übergabe von Zeigern zwischen Methoden kann zu nicht definiertem Verhalten führen. Ziehen Sie eine Methode in Betracht, die einen Zeiger auf eine lokale Variable als einen `in`-, `out`- oder `ref`-Parameter oder als Funktionsergebnis zurückgibt. Wenn der Zeiger in einem fixed-Block festgelegt wurde, ist die Variable, auf die der Zeiger verweist, möglicherweise nicht fixiert.

In der folgenden Tabelle werden die Operatoren und Anweisungen aufgelistet, die in einem unsicheren Kontext auf Zeiger angewendet werden können.

|Operator/Anweisung|Verwendung|
|-------------------------|---------|
|`*`|Führt eine Zeigerdereferenzierung aus.|
|`->`|Greift über einen Zeiger auf einen Member einer Struktur zu.|
|`[]`|Indiziert einen Zeiger.|
|`&`|Ruft die Adresse einer Variablen ab.|
|`++` und `--`|Inkrementiert und dekrementiert Zeiger.|
|`+` und `-`|Führt Zeigerarithmetik aus.|
|`==`, `!=`, `<`, `>`, `<=` und `>=`|Vergleicht Zeiger.|
|[`stackalloc`](../../language-reference/operators/stackalloc.md)|Belegt Speicher für den Stapel.|
|[`fixed`-Anweisung](../../language-reference/keywords/fixed-statement.md)|Fixiert eine Variable vorübergehend, damit ihre Adresse gefunden werden kann.|

Weitere Informationen zu Zeigeroperatoren finden Sie unter [Operatoren im Zusammenhang mit Zeigern](../../language-reference/operators/pointer-related-operators.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Zeigertypen](~/_csharplang/spec/unsafe-code.md#pointer-types) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Unsicherer Code und Zeiger](index.md)
- [Zeigerkonvertierungen](pointer-conversions.md)
- [Verweistypen](../../language-reference/keywords/reference-types.md)
- [Werttypen](../../language-reference/builtin-types/value-types.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
