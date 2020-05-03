---
title: nameof-Ausdruck – C#-Referenz
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: d71acf0cf7d5cdcfa5310455af2120fa1f82d567
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135918"
---
# <a name="nameof-expression-c-reference"></a>nameof-Ausdruck (C#-Referenz)

Ein `nameof`-Ausdruck erzeugt den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante:

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.

Im Fall von [ausführlichen Bezeichnern](../tokens/verbatim.md) ist das `@`-Zeichen nicht der Teil eines Namens, wie im folgenden Beispiel gezeigt:

[!code-csharp-interactive[nameof verbatim](snippets/NameOfOperator.cs#Verbatim)]

Ein `nameof`-Ausdruck wird zur Kompilierzeit ausgewertet und hat zur Laufzeit keine Auswirkung.

Sie können einen `nameof`-Ausdruck nutzen, um den Code zur Argumentüberprüfung besser verwalten zu können:

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

Der `nameof`-Ausdruck ist ab C# 6 verfügbar.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
