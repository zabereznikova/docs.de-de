---
title: nameof-Ausdruck – C#-Referenz
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5a68161be7bb03122d2a63ccef4365c5853862b2
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507138"
---
# <a name="nameof-expression-c-reference"></a>nameof-Ausdruck (C#-Referenz)

Ein `nameof`-Ausdruck erzeugt den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante:

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.

Ein `nameof`-Ausdruck wird zur Kompilierzeit ausgewertet und hat zur Laufzeit keine Auswirkung.

Sie können einen `nameof`-Ausdruck nutzen, um den Code zur Argumentüberprüfung besser verwalten zu können:

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

Der `nameof`-Ausdruck ist ab C# 6 verfügbar.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
