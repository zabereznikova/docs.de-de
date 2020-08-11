---
title: nameof-Ausdruck – C#-Referenz
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: b00c5f6f97d27290fb3773dcbb422bf9fb4c425b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916777"
---
# <a name="nameof-expression-c-reference"></a>nameof-Ausdruck (C#-Referenz)

Ein `nameof`-Ausdruck erzeugt den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante:

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.

Im Fall von [ausführlichen Bezeichnern](../tokens/verbatim.md) ist das `@`-Zeichen nicht der Teil eines Namens, wie im folgenden Beispiel gezeigt:

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

Ein `nameof`-Ausdruck wird zur Kompilierzeit ausgewertet und hat zur Laufzeit keine Auswirkung.

Sie können einen `nameof`-Ausdruck nutzen, um den Code zur Argumentüberprüfung besser verwalten zu können:

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

Der `nameof`-Ausdruck ist ab C# 6 verfügbar.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
