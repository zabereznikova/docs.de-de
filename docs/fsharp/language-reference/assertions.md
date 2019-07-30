---
title: Assertionen
description: Erfahren Sie, wie Sie mit der Ausdruck "assert" als eine Debugfunktion zum Testen von Ausdrücken in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630024"
---
# <a name="assertions"></a>Assertionen

Der `assert` Ausdruck ist ein Debugfeature, das Sie zum Testen eines Ausdrucks verwenden können. Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.

## <a name="syntax"></a>Syntax

```fsharp
assert condition
```

## <a name="remarks"></a>Hinweise

Der `assert` Ausdruck weist den `bool -> unit`Typ auf.

In der vorherigen Syntax stellt *Condition* einen booleschen Ausdruck dar, der getestet werden soll. Wenn der Ausdruck als `true`ausgewertet wird, wird die Ausführung nicht beeinträchtigt. Wenn ausgewertet `false`wird, wird ein Systemfehler Dialogfeld generiert. Das Fehler Dialogfeld enthält eine Beschriftung, die die **Zeichen folgen**-Assertionen enthält. Das Dialogfeld enthält eine Stapel Überwachung, die angibt, wo der Fehler bei der Übersetzung aufgetreten ist.

Die Überprüfung der Überprüfung ist nur aktiviert, wenn Sie im Debugmodus kompilieren. Das heißt, wenn die Konstante `DEBUG` definiert ist. Im Projekt System ist die `DEBUG` Konstante standardmäßig in der Debugkonfiguration definiert, jedoch nicht in der Releasekonfiguration.

Der Fehler bei der Fehlerbehebung kann nicht mithilfe F# der Ausnahmebehandlung abgefangen werden.

> [!NOTE]
> Die `assert` -Funktion wird <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>in aufgelöst.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Verwendung des `assert` -Ausdrucks veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
