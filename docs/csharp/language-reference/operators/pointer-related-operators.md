---
title: 'Operatoren im Zusammenhang mit Zeigern: C#-Referenz'
description: Enthält Informationen zu C#-Operatoren, die Sie bei der Arbeit mit Zeigern verwenden können.
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: fd25cd419f8c3bfe905850e6a252f4a8cf65478c
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507099"
---
# <a name="pointer-related-operators-c-reference"></a>Operatoren im Zusammenhang mit Zeigern (C#-Referenz)

Sie können die folgenden Operatoren für Zeiger verwenden:

- Unärer Operator [`&` (Adresse von)](#address-of-operator-): Abrufen der Adresse einer Variablen
- Unärer Operator [`*` (Zeigerdereferenzierung)](#pointer-indirection-operator-): Abrufen der Variablen, auf die per Zeiger verwiesen wird
- Operatoren [`->` (Memberzugriff)](#pointer-member-access-operator--) und [`[]` (Elementzugriff)](#pointer-element-access-operator-)
- Arithmetische Operatoren [`+`, `-`, `++` und `--`](#pointer-arithmetic-operators)
- Vergleichsoperatoren [`==`, `!=`, `<`, `>`, `<=` und `>=`](#pointer-comparison-operators)

Informationen zu Zeigertypen finden Sie unter [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md).

> [!NOTE]
> Für alle Operationen mit Zeigern ist ein Kontext des Typs [unsafe](../keywords/unsafe.md) erforderlich. Code, in dem unsafe-Blöcke enthalten sind, muss mit der Compileroption [`-unsafe`](../compiler-options/unsafe-compiler-option.md) kompiliert werden.

## <a name="address-of-operator-amp"></a><a name="address-of-operator-"></a> Adressoperator &amp;

Der unäre Operator `&` gibt die Adresse seines Operanden zurück:

[!code-csharp[address of local](snippets/PointerOperators.cs#AddressOf)]

Der Operand des Operators `&` muss eine feste Variable sein. *Feste* Variablen befinden sich an Speicherorten, auf die sich [Garbage Collector](../../../standard/garbage-collection/index.md)-Operationen nicht auswirken. Im vorherigen Beispiel ist die lokale Variable `number` eine feste Variable, da sie im Stapel angeordnet ist. Variablen an Speicherorten, auf die sich der Garbage Collector auswirken kann (z. B. durch eine Verschiebung), werden als *bewegliche* Variablen bezeichnet. Objektfelder und Arrayelemente sind Beispiele für bewegliche Variablen. Sie können die Adresse einer beweglichen Variablen erhalten, wenn Sie sie mit einer [`fixed`-Anweisung](../keywords/fixed-statement.md) „fixieren“ bzw. „anheften“. Die erhaltene Adresse ist nur innerhalb des Blocks einer `fixed`-Anweisung gültig. Im folgenden Beispiel wird veranschaulicht, wie Sie eine `fixed`-Anweisung und den `&`-Operator verwenden:

[!code-csharp[address of fixed](snippets/PointerOperators.cs#AddressOfFixed)]

Sie können nicht die Adresse einer Konstanten oder eines Werts abrufen.

Weitere Informationen zu festen und beweglichen Variablen finden Sie im Abschnitt [Feste und verschiebbare Variablen](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).

Mit dem binären Operator `&` wird der Wert für [logisches UND](boolean-logical-operators.md#logical-and-operator-) der booleschen Operanden oder der Wert für [bitweise logisches UND](bitwise-and-shift-operators.md#logical-and-operator-) für die integralen Operanden berechnet.

## <a name="pointer-indirection-operator-"></a>Zeigerdereferenzierungsoperator *

Mit dem unären Zeigerdereferenzierungsoperator `*` wird die Variable abgerufen, auf die der Operand verweist. Er wird auch kurz als Dereferenzierungsoperator bezeichnet. Der Operand des Operators `*` muss einen Zeigertyp aufweisen.

[!code-csharp[pointer indirection](snippets/PointerOperators.cs#PointerIndirection)]

Sie können den Operator `*` nicht auf einen Ausdruck vom Typ `void*` anwenden.

Mit dem binären Operator `*` wird das [Produkt](arithmetic-operators.md#multiplication-operator-) seiner numerischen Operanden berechnet.

## <a name="pointer-member-access-operator--"></a>Zeigermember-Zugriffsoperator ->

Mit dem Operator `->` werden die [Zeigerdereferenzierung](#pointer-indirection-operator-) und der [Memberzugriff](member-access-operators.md#member-access-expression-) kombiniert. Wenn `x` ein Zeiger des Typs `T*` und `y` ein Member des Typs `T` ist, auf den zugegriffen werden kann, ist ein Ausdruck der Form

```csharp
x->y
```

für die folgende Syntax:

```csharp
(*x).y
```

Im folgenden Beispiel wird die Verwendung des `->`-Operators veranschaulicht:

[!code-csharp[pointer member access](snippets/PointerOperators.cs#MemberAccess)]

Sie können den Operator `->` nicht auf einen Ausdruck vom Typ `void*` anwenden.

## <a name="pointer-element-access-operator-"></a>Zeigerelementzugriff-Operator []

Für einen Ausdruck `p` mit einem Zeigertyp wird ein Zeigerelementzugriff der Form `p[n]` als `*(p + n)` ausgewertet. Hierbei muss `n` einen Typ aufweisen, der implizit in `int`, `uint`, `long` oder `ulong` konvertiert werden kann. Informationen zum Verhalten des Operators `+` mit Zeigern finden Sie im Abschnitt [Addieren oder Subtrahieren eines Integralwerts zu bzw. von einem Zeiger](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer).

Im folgenden Beispiel wird veranschaulicht, wie Sie mit einem Zeiger und dem Operator `[]` auf Arrayelemente zugreifen:

[!code-csharp[pointer element access](snippets/PointerOperators.cs#ElementAccess)]

Im vorangegangenen Beispiel ordnet ein [`stackalloc`-Ausdruck](stackalloc.md) einen Speicherblock im Stapel zu.

> [!NOTE]
> Der Zeigerelementzugriff-Operator führt keine Überprüfung auf Fehler vom Typ „Außerhalb des gültigen Bereichs“ durch.

Sie können `[]` nicht für den Zeigerelementzugriff mit einem Ausdruck vom Typ `void*` verwenden.

Sie können auch den Operator `[]` für den [Arrayelement- oder Indexerzugriff](member-access-operators.md#indexer-operator-) nutzen.

## <a name="pointer-arithmetic-operators"></a>Arithmetische Zeigeroperatoren

Sie können mit Zeigern die folgenden arithmetischen Operationen durchführen:

- Addieren oder Subtrahieren eines Integralwerts zu bzw. von einem Zeiger
- Subtrahieren von zwei Zeigern
- Inkrementieren oder Dekrementieren eines Zeigers

Sie können diese Operationen nicht mit Zeigern vom Typ `void*` durchführen.

Weitere Informationen zu unterstützten arithmetischen Operationen mit numerischen Typen finden Sie unter [Arithmetische Operatoren](arithmetic-operators.md).

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a>Addieren oder Subtrahieren eines Integralwerts zu bzw. von einem Zeiger

Für einen Zeiger `p` vom Typ `T*` und einen Ausdruck `n` eines Typs, der implizit in `int`, `uint`, `long` oder `ulong` konvertiert werden kann, sind die Addition und die Subtraktion wie folgt definiert:

- Für die Ausdrücke `p + n` und `n + p` wird jeweils ein Zeiger vom Typ `T*` erzeugt, der sich aus dem Addieren von `n * sizeof(T)` zur Adresse von `p` ergibt.
- Für den Ausdruck `p - n` wird ein Zeiger vom Typ `T*` erzeugt, der sich ergibt, indem `n * sizeof(T)` von der Adresse von `p` subtrahiert wird.

Mit dem Operator [`sizeof`](sizeof.md) wird die Größe eines Typs in Byte abgerufen.

Im folgenden Beispiel wird die Verwendung des Operators `+` mit einem Zeiger veranschaulicht:

[!code-csharp[pointer addition](snippets/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a>Zeigersubtraktion

Für die beiden Zeiger `p1` und `p2` vom Typ `T*` ergibt der Ausdruck `p1 - p2` den Unterschied zwischen den Adressen von `p1` und `p2` dividiert durch `sizeof(T)`. Das Ergebnis hat den Typ `long`. `p1 - p2` wird also als `((long)(p1) - (long)(p2)) / sizeof(T)` berechnet.

Im folgenden Beispiel ist die Zeigersubtraktion dargestellt:

[!code-csharp[pointer subtraction](snippets/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a>Inkrementieren und Dekrementieren von Zeigern

Mit dem Inkrementoperator `++` wird 1 zum Zeigeroperanden [addiert](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer). Mit dem Dekrementoperator `--` wird 1 vom Zeigeroperanden [subtrahiert](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer).

Für beide Operatoren werden zwei Formen unterstützt: Postfix (`p++` und `p--`) und Präfix (`++p` und `--p`). Das Ergebnis von `p++` und `p--` ist der Wert von `p` *vor* der Operation. Das Ergebnis von `++p` und `--p` ist der Wert von `p` *nach* der Operation.

Im folgenden Beispiel wird das Verhalten von Postfix- und Präfix-Inkrementoperatoren veranschaulicht:

[!code-csharp[pointer increment](snippets/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a>Vergleichsoperatoren für Zeiger

Sie können die Operatoren `==`, `!=`, `<`, `>`, `<=` und `>=` verwenden, um Operanden jedes Zeigertyps zu vergleichen, z. B. `void*`. Mit diesen Operatoren werden die Adressen der zwei Operanden so verglichen, als ob es sich um ganze Zahlen ohne Vorzeichen handeln würde.

Informationen zum Verhalten dieser Operatoren für Operanden anderer Typen finden Sie in den Artikeln zu [Gleichheitsoperatoren](equality-operators.md) und [Vergleichsoperatoren](comparison-operators.md).

## <a name="operator-precedence"></a>Operatorrangfolge

In der folgenden Liste sind die Zeigeroperatoren absteigend nach der Rangfolge sortiert:

- Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation (`x++` und `x--`) und die Operatoren `->` und `[]`
- Inkrementierungs- und Dekrementierungsoperatoren in Präfixnotation (`++x` und `--x`) und die Operatoren `&` und `*`
- Additive Operatoren `+` und `-`
- Vergleichsoperatoren `<`, `>`, `<=` und `>=`
- Gleichheitsoperatoren `==` und `!=`

Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch die Operatorrangfolge festgelegt ist.

Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie im Abschnitt [Operatorrangfolge](index.md#operator-precedence) im Artikel [C#-Operatoren](index.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Mit einem benutzerdefinierten Typ können die Zeigeroperatoren `&`, `*`, `->` und `[]` nicht überladen werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Fixed and moveable variables (Feste und verschiebbare Variablen)](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [Adresse-von-Operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [Zeigerdereferenzierung](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [Zeigermemberzugriff](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [Zeigerelementzugriff](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [Zeigerarithmetik](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [Inkrementieren und Dekrementieren von Zeigern](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [Zeigervergleich](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [unsafe (Schlüsselwort)](../keywords/unsafe.md)
- [fixed (Schlüsselwort)](../keywords/fixed-statement.md)
- [stackalloc](stackalloc.md)
- [sizeof (Operator)](sizeof.md)
