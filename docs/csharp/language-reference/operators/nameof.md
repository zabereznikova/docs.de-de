---
title: Operator „nameof“ – C#-Referenz
ms.custom: seodec18
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: fa858db918cdaf04c757f2741265e359acb74f7b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036354"
---
# <a name="nameof-operator-c-reference"></a>Operator „nameof“ (C#-Referenz)

Der Operator `nameof` ruft den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante ab:

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.

Der Operator `nameof` wird zur Kompilierzeit ausgewertet und hat zum Zeitpunkt der Ausführung keine Auswirkung.

Der Operator `nameof` kann zur besseren Verwaltbarkeit des Argumentüberprüfungscodes beitragen:

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

Der Operator `nameof` ist ab C# 6 verfügbar.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
