---
title: Inlinefunktionen
description: Erfahren Sie, wie F# Inline Funktionen verwendet werden, die direkt in den aufrufenden Code integriert sind.
ms.date: 05/16/2016
ms.openlocfilehash: 2830d1ada5b3005c3fcae975a44e85a7c84554f7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630677"
---
# <a name="inline-functions"></a>Inlinefunktionen

*Inline Funktionen* sind Funktionen, die direkt in den aufrufenden Code integriert sind.

## <a name="using-inline-functions"></a>Verwenden von Inline Funktionen

Wenn Sie statische Typparameter verwenden, müssen alle Funktionen, die von Typparametern parametrisiert werden, Inline sein. Dadurch wird sichergestellt, dass der Compiler diese Typparameter auflösen kann. Wenn Sie gewöhnliche generische Typparameter verwenden, gibt es keine derartige Einschränkung.

Wenn Sie die Verwendung von Element Einschränkungen nicht aktivieren, können Inline Funktionen beim Optimieren von Code hilfreich sein. Die übermäßige Verwendung von Inline Funktionen kann jedoch dazu führen, dass Ihr Code weniger gegen Änderungen an Compileroptimierungen und die Implementierung von Bibliotheksfunktionen ist. Aus diesem Grund sollten Sie die Verwendung von Inline Funktionen für die Optimierung vermeiden, es sei denn, Sie haben alle anderen Optimierungstechniken ausprobiert. Wenn eine Funktion oder Methode Inline ist, kann die Leistung manchmal verbessert werden, dies ist jedoch nicht immer der Fall. Daher sollten Sie auch Leistungsmessungen verwenden, um zu überprüfen, ob das Erstellen einer bestimmten Funktion in der Tat eine positive Wirkung hat.

Der `inline` -Modifizierer kann auf Funktionen auf der obersten Ebene, auf Modulebene oder auf Methoden Ebene in einer Klasse angewendet werden.

Im folgenden Codebeispiel wird eine Inline Funktion auf oberster Ebene, eine Inline-Instanzmethode und eine statische Inline-Methode veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a>Inline Funktionen und Typrückschluss

Das vorhanden sein `inline` von beeinflusst den Typrückschluss. Dies liegt daran, dass Inline Funktionen statisch aufgelöste Typparameter aufweisen können, während nicht Inline Funktionen nicht. Das folgende Codebeispiel zeigt einen Fall, `inline` bei dem hilfreich ist, da Sie eine Funktion verwenden, die einen statisch aufgelösten Typparameter `float` aufweist, den Konvertierungs Operator.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

Ohne den `inline` -Modifizierer zwingt der Typrückschluss, dass die Funktion einen bestimmten Typ annimmt `int`, in diesem Fall. Mit dem `inline` -Modifizierer wird jedoch auch die-Funktion abgeleitet, um einen statisch aufgelösten Typparameter zu erhalten. Mit dem `inline` -Modifizierer wird der Typ wie folgt abgeleitet:

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

Dies bedeutet, dass die Funktion einen beliebigen Typ akzeptiert, der eine Konvertierung in **float**unterstützt.

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
- [Einschränkungen](../generics/constraints.md)
- [Statisch aufgelöste Typparameter](../generics/statically-resolved-type-parameters.md)
