---
title: 'Ausnahmen: Der try...finally-Ausdruck'
description: Erfahren Sie, wie die F# "try-finally' Ausdruck können Sie Bereinigungscode auszuführen, auch wenn Sie ein Codeblock eine Ausnahme auslöst.
ms.date: 05/16/2016
ms.openlocfilehash: 24613185818c8ea30b27dcf639b22af320c4b401
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611619"
---
# <a name="exceptions-the-tryfinally-expression"></a>Ausnahmen: Der try...finally-Ausdruck

Die `try...finally` Ausdruck können Sie Bereinigungscode auszuführen, auch wenn Sie ein Codeblock eine Ausnahme auslöst.

## <a name="syntax"></a>Syntax

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>Hinweise

Die `try...finally` Ausdruck kann verwendet werden, zum Ausführen des Codes in *expression2* in der vorherigen Syntax unabhängig davon, ob eine Ausnahme, während der Ausführung des generiert wird *expression1*.

Der Typ des *expression2* trägt nicht auf den Wert des gesamten Ausdrucks ist; der Typ zurückgegeben, wenn eine Ausnahme auftritt, wird der letzte Wert im *expression1*. Wenn eine Ausnahme auftritt, wird kein Wert zurückgegeben, und die ablaufsteuerung an den nächsten übereinstimmenden Ausnahmehandler der Aufrufliste nach oben übertragen. Wenn kein Ausnahmehandler gefunden wird, wird das Programm beendet. Bevor der Code in ein entsprechender Handler ausgeführt wird oder das Programm beendet wird, den Code in die `finally` Branch ausgeführt wird.

Der folgende Code veranschaulicht die Verwendung der `try...finally` Ausdruck.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

Die Ausgabe an die Konsole ist wie folgt aus.

```
Closing stream
Exception handled.
```

Wie Sie in der Ausgabe sehen, wurde der Stream geschlossen, bevor die äußere Ausnahme behandelt wurde, und die Datei `test.txt` enthält den Text `test1`, was bedeutet, dass die Puffer geleert und auf den Datenträger, auch wenn die Ausnahme übertragen geschrieben wurden die Steuerung an den äußeren Ausnahmehandler übergeben.

Beachten Sie, dass die `try...with` -Konstrukt ist ein separater Konstrukt aus der `try...finally` zu erstellen. Aus diesem Grund Wenn der Code sowohl erfordert eine `with` Block und einem `finally` blockieren, müssen Sie die zwei Konstrukte schachteln, wie im folgenden Codebeispiel wird.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

Im Kontext des Berechnungsausdrücke, einschließlich der Sequence-Ausdrücke und asynchrone Workflows, **try-finally** Ausdrücke können eine benutzerdefinierte Implementierung haben. Weitere Informationen finden Sie unter [Berechnungsausdrücke](../computation-expressions.md).

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmen: Die `try...with` Ausdruck](the-try-with-expression.md)