---
title: Assertionen
description: Erfahren Sie, wie Sie den Assert-Ausdruck als Debuggingfunktion zum Testen von F# Ausdrücken in der Programmiersprache verwenden.
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799060"
---
# <a name="assertions"></a>Assertionen

Der `assert` Ausdruck ist ein Debugfeature, das Sie zum Testen eines Ausdrucks verwenden können. Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.

## <a name="syntax"></a>Syntax

```fsharp
assert condition
```

## <a name="remarks"></a>Hinweise

Der `assert` Ausdruck hat den Typ `bool -> unit`.

Die `assert`-Funktion wird in <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>aufgelöst. Dies bedeutet, dass das Verhalten identisch mit dem direkten Aufrufen von <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> ist.

Die Überprüfung der Überprüfung ist nur aktiviert, wenn Sie im Debugmodus kompilieren. Das heißt, wenn die Konstante `DEBUG` definiert ist. Im Projekt System ist die `DEBUG` Konstante standardmäßig in der Debugkonfiguration, aber nicht in der Releasekonfiguration definiert.

Der Fehler bei der Fehlerbehebung kann nicht mithilfe F# der Ausnahmebehandlung abgefangen werden.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Verwendung des `assert` Ausdrucks veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
