---
title: Inlinefunktionen (F#)
description: Erfahren Sie, wie Sie mit F#-Inline-Funktionen, die direkt in den aufrufenden Code integriert sind.
ms.date: 05/16/2016
ms.openlocfilehash: 47fca0fe34630792aeb0908b0cee02a927e2567d
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45685672"
---
# <a name="inline-functions"></a>Inlinefunktionen

*Inlinefunktionen* sind Funktionen, die direkt in den aufrufenden Code integriert werden.

## <a name="using-inline-functions"></a>Verwendung von Inlinefunktionen

Wenn Sie statische Typparameter verwenden, müssen jede Funktion, die durch den Typparameter parametrisiert werden Inline sein. Dadurch wird sichergestellt, dass der Compiler diese Typparameter auflösen kann. Wenn Sie normale generischen Typparameter verwenden, besteht keine derartige Einschränkung.

Als die Verwendung der Member-Einschränkungen aktivieren, können Inline-Funktionen in die Optimierung von Code hilfreich sein. Übermäßiger Verwendung von Inlinefunktionen kann jedoch zu Ihrem Code weniger auf Änderungen compileroptimierungen und die Implementierung der Library-Funktionen zum Schutz vor Angriffen führen. Aus diesem Grund sollten Sie vermeiden, verwenden Inline-Funktionen für die Optimierung, es sei denn, Sie, alle anderen Techniken zur Optimierung versucht haben. Erstellen eine Funktion oder Methode Inline kann manchmal die Leistung verbessern, aber das ist nicht immer der Fall. Aus diesem Grund sollten Sie leistungsmessungen verwenden, um sicherzustellen, dass bestimmte Funktion Inline erstellen einen positiven Effekt in der Tat verfügt.

Die `inline` Modifizierer auf Funktionen auf der obersten Ebene, auf der Modulebene oder auf der Ebene der in einer Klasse angewendet werden kann.

Im folgenden Codebeispiel wird veranschaulicht, auf der obersten Ebene, die Methode eine Inline-Instanz und eine statische Inline-Methode eine Inline-Funktion.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a>Inlinefunktionen und Typrückschluss

Das Vorhandensein von `inline` wirkt sich auf den Typrückschluss. Dies ist da Inlinefunktionen Statisch aufgelöste Typparameter aufweisen können, während nicht-Inline-Funktionen nicht möglich. Das folgende Codebeispiel zeigt einen Fall, in denen `inline` ist hilfreich, da Sie eine Funktion verwenden, der einen statisch aufgelösten Typparameter hat den `float` Konvertierungsoperator.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

Ohne die `inline` Modifizierer, zwingt die Funktion ein bestimmtes Typs in diesem Fall wird der Typrückschluss `int`. Dabei sollen die `inline` Modifizierer, die Funktion so haben einen statisch aufgelösten Typparameter abgeleitet. Mit der `inline` Modifizierer, der Typ abgeleitet wird, werden die folgenden:

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

Dies bedeutet, dass die Funktion jeden Typ akzeptiert, die eine Konvertierung in unterstützt **"float"**.

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
- [Einschränkungen](../generics/constraints.md)
- [Statisch aufgelöste Typparameter](../generics/statically-resolved-type-parameters.md)
