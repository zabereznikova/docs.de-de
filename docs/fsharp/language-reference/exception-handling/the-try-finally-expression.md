---
title: 'Ausnahmen: Der try...finally-Ausdruck'
description: Erfahren Sie, F# wie die "Try... mithilfe von "Expression" können Sie auch dann Bereinigungs Code ausführen, wenn ein Codeblock eine Ausnahme auslöst.
ms.date: 05/16/2016
ms.openlocfilehash: 03fbda1ef5d55560232f0217f603fc04c0af0eb4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630273"
---
# <a name="exceptions-the-tryfinally-expression"></a>Ausnahmen: Der try...finally-Ausdruck

Der `try...finally` Ausdruck ermöglicht das Ausführen von Bereinigungs Code, auch wenn ein Codeblock eine Ausnahme auslöst.

## <a name="syntax"></a>Syntax

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>Hinweise

Der `try...finally` Ausdruck kann verwendet werden, um den Code in *expression2* in der vorangehenden Syntax auszuführen, unabhängig davon, ob während der Ausführung von *expression1*eine Ausnahme generiert wird.

Der *expression2* -Typ trägt nicht zum Wert des gesamten Ausdrucks bei. der Typ, der zurückgegeben wird, wenn keine Ausnahme auftritt, ist der letzte Wert in *expression1*. Wenn eine Ausnahme auftritt, wird kein Wert zurückgegeben, und die Ablauf Steuerung wird an den nächsten übereinstimmenden Ausnahmehandler in der aufrufsstapel übertragen. Wenn kein Ausnahmehandler gefunden wird, wird das Programm beendet. Bevor der Code in einem übereinstimmenden Handler ausgeführt oder das Programm beendet wird, wird der `finally` Code in der Verzweigung ausgeführt.

Der folgende Code veranschaulicht die Verwendung des `try...finally` -Ausdrucks.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

Die Ausgabe an die Konsole lautet wie folgt.

```
Closing stream
Exception handled.
```

Wie Sie in der Ausgabe sehen können, wurde der Stream geschlossen, bevor die äußere Ausnahme behandelt wurde, und die `test.txt` Datei enthält den `test1`Text, der angibt, dass die Puffer geleert und auf den Datenträger geschrieben wurden, obwohl die Ausnahme übertragen wurde. Steuern Sie den äußeren Ausnahmehandler.

Beachten Sie, `try...with` dass das-Konstrukt ein separates Konstrukt `try...finally` aus dem-Konstrukt ist. Wenn Ihr Code also sowohl einen `with` -Block als auch einen `finally` -Block erfordert, müssen Sie die beiden-Konstrukte Schachteln, wie im folgenden Codebeispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

Versuchen Sie im Kontext von Berechnungs Ausdrücken, einschließlich Sequenz Ausdrücken und asynchronen Workflows, **... Schließlich** können Ausdrücke über eine benutzerdefinierte Implementierung verfügen. Weitere Informationen finden Sie unter [Berechnungs Ausdrücke](../computation-expressions.md).

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmen: Der `try...with` Ausdruck](the-try-with-expression.md)
