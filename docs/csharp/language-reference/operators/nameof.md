---
title: Operator „nameof“ – C#-Referenz
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: ffbc801acf61bf72db1c88912dc2142a478fa280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846271"
---
# <a name="nameof-operator-c-reference"></a>Operator „nameof“ (C#-Referenz)

Der Operator `nameof` ruft den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante ab:

[!code-csharp-interactive[nameof operator](snippets/NameOfOperator.cs#Examples)]

Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.

Der Operator `nameof` wird zur Kompilierzeit ausgewertet und hat zum Zeitpunkt der Ausführung keine Auswirkung.

Der Operator `nameof` kann zur besseren Verwaltbarkeit des Argumentüberprüfungscodes beitragen:

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

Der Operator `nameof` ist ab C# 6 verfügbar.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
