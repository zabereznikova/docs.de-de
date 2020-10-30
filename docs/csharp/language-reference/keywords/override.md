---
description: override-Modifizierer – C#-Referenz
title: override-Modifizierer – C#-Referenz
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434880"
---
# <a name="override-c-reference"></a>override (C#-Referenz)

Der `override`-Modifizierer wird benötigt, um die abstrakte oder virtuelle Implementierung einer geerbten Methode, Eigenschaft, eines Indexers oder Ereignisses zu erweitern oder ändern.

Im folgenden Beispiel muss die `Square`-Klasse eine überschriebene Implementierung von `GetArea` bereitstellen, weil `GetArea` von der abstrakten Klasse `Shape` geerbt wird:

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

Eine `override`-Methode stellt eine neue Implementierung der Methode bereit, die von einer Basisklasse geerbt wurde. Die Methode, die durch eine `override`-Deklaration überschrieben wird, wird als die überschriebene Basismethode bezeichnet. Eine `override`-Methode muss dieselbe Signatur wie die überschriebene Basismethode haben. Ab C# 9.0 unterstützen `override`-Methoden kovariante Rückgabetypen. Dies bedeutet, dass der Rückgabetyp einer `override`-Methode vom Rückgabetyp der entsprechenden Basismethode abgeleitet werden kann. In C# 8.0 und früher müssen die Rückgabetypen einer `override`-Methode und die der überschriebenen Basismethode identisch sein.

Sie können keine nicht virtuelle oder statische Methode überschreiben. Die überschriebene Basismethode muss `virtual`, `abstract` oder `override` sein.

Ein `override`-Deklaration kann nicht die Erreichbarkeit auf die `virtual` Methode ändern. Sowohl die Methode `override` als auch `virtual` müssen den gleichen [Zugriffsebenenmodifizierer](access-modifiers.md) besitzen.

Sie können die Modifizierer `new`, `static` oder `virtual` nicht verwenden, um eine `override`-Methode zu ändern.

Eine überschreibende Eigenschaftsdeklaration muss genau denselben Zugriffsmodifizierer, Typ und Namen wie die geerbte Eigenschaft angeben. Ab C# 9.0 unterstützen schreibgeschützte überschreibende Eigenschaften kovariante Rückgabetypen. Die überschriebene Eigenschaft muss `virtual`, `abstract` oder `override` entsprechen.

Weitere Informationen zur Verwendung des `override`-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md). Weitere Informationen zur Vererbung in C# finden Sie unter [Vererbung](../../programming-guide/classes-and-structs/inheritance.md).

## <a name="example"></a>Beispiel

In diesem Beispiel wird eine Basisklasse namens `Employee` und eine abgeleitete Klasse namens `SalesEmployee` definiert. Die `SalesEmployee`-Klasse enthält ein zusätzliches Feld `salesbonus`, und überschreibt die `CalculatePay`-Methode, um dies zu berücksichtigen.

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [override-Methoden](~/_csharplang/spec/classes.md#override-methods) der [Sprachspezifikation für C#](~/_csharplang/spec/introduction.md).

Weitere Informationen zu kovarianten Rückgabetypen finden Sie im [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Vererbung](../../programming-guide/classes-and-structs/inheritance.md)
- [C#-Schlüsselwörter](index.md)
- [Modifizierer](index.md)
- [abstract](abstract.md)
- [virtual](virtual.md)
- [new (Modifizierer)](new-modifier.md)
- [Polymorphismus](../../programming-guide/classes-and-structs/polymorphism.md)
