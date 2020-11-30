---
description: ':::no-loc text=interface::: (C#-Referenz)'
title: interface – C#-Referenz
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 24f95e828522f467c519c0c8a7ba9410aa97af4e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89134587"
---
# <a name="no-loc-textinterface-c-reference"></a>:::no-loc text="interface"::: (C#-Referenz)

Eine Schnittstelle definiert einen Vertrag. Jede [`class`](class.md) oder [`struct`](../builtin-types/struct.md), die diesen Vertrag implementiert, muss eine Implementierung der in der Schnittstelle definierten Member bereitstellen. Ab C# 8.0 kann eine Schnittstelle eine Standardimplementierung für Member definieren. Sie kann auch [`static`](static.md)-Member definieren, um eine einzelne Implementierung für allgemeine Funktionen bereitzustellen.

Im folgenden Beispiel muss die Klasse `ImplementationClass` eine Methode mit dem Namen `SampleMethod` implementieren, die keine Parameter hat und `void` zurückgibt.

Weitere Informationen und Beispiele finden Sie unter [Schnittstellen](../../programming-guide/interfaces/index.md).

## <a name="example"></a>Beispiel

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

Eine Schnittstelle kann ein Member eines Namespaces oder einer Klasse sein. Eine Schnittstellendeklaration kann Deklarationen der folgenden Member enthalten (Signaturen ohne Implementierungen):

- [Methoden](../../programming-guide/classes-and-structs/methods.md)
- [Eigenschaften](../../programming-guide/classes-and-structs/using-properties.md)
- [Indexer](../../programming-guide/indexers/using-indexers.md)
- [Ereignisse](event.md)

Diese vorangehenden Memberdeklarationen enthalten in der Regel keinen Text. Ab C# 8.0 kann ein Schnittstellenmember einen Text deklarieren. Dies wird als *Standardimplementierung* bezeichnet. Member mit Text ermöglichen der Schnittstelle, eine „Standardimplementierung“ für Klassen und Strukturen bereitzustellen, die keine überschreibende Implementierung bereitstellen. Außerdem kann eine Schnittstelle ab C# 8.0 Folgendes umfassen:

- [Konstanten](const.md)
- [Operatoren](../operators/operator-overloading.md)
- [Statischer Konstruktor](../../programming-guide/classes-and-structs/constructors.md#static-constructors)
- [Geschachtelte Typen](../../programming-guide/classes-and-structs/nested-types.md)
- [Statische Felder, Methoden, Eigenschaften, Indexer und Ereignisse](static.md)
- Memberdeklarationen, die die Syntax der explizite Schnittstellenimplementierung verwenden
- Explizite Zugriffsmodifizierer (der Standardzugriff ist [`public`](access-modifiers.md))

Schnittstellen dürfen keinen Instanzstatus enthalten. Obwohl statische Felder jetzt zulässig sind, sind Instanzfelder in Schnittstellen nicht zulässig. [Automatische Eigenschaften von Instanzen](../../programming-guide/classes-and-structs/auto-implemented-properties.md) werden in Schnittstellen nicht unterstützt, da sie implizit ein ausgeblendetes Feld deklarieren würden. Diese Regel hat eine fast unmerkliche Auswirkung auf Eigenschaftsdeklarationen. In einer Schnittstellendeklaration deklariert der folgende Code anders als bei `class` und `struct` keine automatisch implementierte Eigenschaft. Stattdessen wird eine Eigenschaft deklariert, die keine Standardimplementierung hat, sondern in jedem Typ implementiert werden muss, der die Schnittstelle implementiert:

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

Eine Schnittstelle kann von einer oder mehreren Basisschnittstellen erben. Wenn eine Schnittstelle [eine Methode überschreibt](override.md) die in einer Basisschnittstelle implementiert ist, muss sie die Syntax der [expliziten Schnittstellenimplementierung](../../programming-guide/interfaces/explicit-interface-implementation.md) verwenden.

Wenn eine Basistypliste sowohl eine Basisklasse als auch Schnittstellen umfasst, muss die Basisklasse zuerst in der Liste stehen.

Eine Klasse, die eine Schnittstelle implementiert, kann Member dieser Schnittstelle explizit implementieren. Auf einen explizit implementierten Member kann nicht durch eine Klasseninstanz zugegriffen werden, sondern nur durch eine Schnittstelleninstanz. Außerdem kann auf Standardschnittstellenmember nur über eine Instanz der Schnittstelle zugegriffen werden.

Weitere Informationen zur expliziten Implementierung finden Sie unter [Explizite Schnittstellenimplementierung](../../programming-guide/interfaces/explicit-interface-implementation.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Schnittstellenimplementierung. In diesem Beispiel enthält die Schnittstelle die Eigenschaftendeklaration, und die Klasse enthält die Implementierung. Eine beliebige Instanz einer Klasse, die `IPoint` implementiert, hat die ganzzahligen Eigenschaften `x` und `y`.

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Schnittstellen](~/_csharplang/spec/interfaces.md) der [C# -Sprachspezifikation](~/_csharplang/spec/introduction.md) und in der Featurespezifikation für [Standardschnittstellenmember – C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Verweistypen](reference-types.md)
- [Schnittstellen](../../programming-guide/interfaces/index.md)
- [Verwenden von Eigenschaften](../../programming-guide/classes-and-structs/using-properties.md)
- [Verwenden von Indexern](../../programming-guide/indexers/using-indexers.md)
