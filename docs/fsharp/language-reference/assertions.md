---
title: Assertionen (F#)
description: Erfahren Sie, wie den Ausdruck "assert" als eine Debugfunktion für das Testen von Ausdrücken in der Programmiersprache f# verwendet.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 195b4a34977a63d92559003b5cd0bb89490a1e7a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="assertions"></a>Assertionen

Die `assert` Ausdruck ist eine Debugfunktion, die Sie verwenden können, um einen Ausdruck zu testen. Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.

## <a name="syntax"></a>Syntax

```fsharp
assert condition
```

## <a name="remarks"></a>Hinweise

Die `assert` Ausdruck weist den Typ `bool -> unit`.

In der vorherigen Syntax *Bedingung* stellt einen booleschen Ausdruck, der getestet werden soll. Wenn der ausgewertete Ausdruck `true`, Ausführung wird fortgeführt, hat keine Auswirkung. Ergibt die Auswertung `false`, wird ein Systemfehlerdialogfeld generiert. Das Dialogfeld "Fehler" hat einer Beschriftung, die die Zeichenfolge enthält **"Assertionsfehler"**. Das Dialogfeld enthält eine stapelüberwachung, die angibt, in der Assertionsfehler aufgetreten ist.

Assertionsüberprüfung ist nur aktiviert, wenn Sie im Debugmodus kompiliert; d. h., wenn die Konstante `DEBUG` definiert ist. Im Projektsystem wird standardmäßig die `DEBUG` Konstante ist, aber nicht in der Releasekonfiguration in der Debugkonfiguration automatisch definiert.

Der Assertionsfehler kann nicht mit der f#-Ausnahmebehandlung abgefangen werden.

>[!NOTE]
Die `assert` Funktion löst in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht die Verwendung von der `assert` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a>Siehe auch

[F#-Sprachreferenz](index.md)
