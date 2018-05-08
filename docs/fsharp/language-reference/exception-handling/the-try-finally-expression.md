---
title: 'Ausnahmen: Der try...finally-Ausdruck (F#)'
description: Erfahren Sie, wie die f#-' try … finally' Ausdruck ermöglicht es Ihnen, Bereinigungscode auszuführen, auch wenn Sie ein Codeblock eine Ausnahme auslöst.
ms.date: 05/16/2016
ms.openlocfilehash: a5fdec7b3986fc9a85c34b08d20dc31947c92b2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-the-tryfinally-expression"></a>Ausnahmen: Der try...finally-Ausdruck

Die `try...finally` Ausdruck ermöglicht es Ihnen, Bereinigungscode auszuführen, auch wenn Sie ein Codeblock eine Ausnahme auslöst.


## <a name="syntax"></a>Syntax

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>Hinweise
Die `try...finally` -Ausdruck kann verwendet werden, um den Code in auszuführen *expression2* in der vorherigen Syntax unabhängig davon, ob eine Ausnahme, während der Ausführung des generiert wird *expression1*.

Der Typ des *expression2* trägt nicht auf den Wert des gesamten Ausdrucks; der Typ zurückgegeben, wenn eine Ausnahme nicht auftritt, ist der letzte Wert im *expression1*. Wenn eine Ausnahme auftritt, wird kein Wert zurückgegeben, und die ablaufsteuerung an den passenden Ausnahmehandler oben in der Aufrufliste übertragen. Wenn keine Ausnahmehandler gefunden wird, wird das Programm beendet. Bevor der Code in einem entsprechenden Handler ausgeführt wird oder das Programm beendet wird, den Code in der `finally` Verzweigung ausgeführt.

Der folgende Code veranschaulicht die Verwendung von der `try...finally` Ausdruck.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

Die Ausgabe an die Konsole lautet wie folgt.

```
Closing stream
Exception handled.
```

Wie Sie aus der Ausgabe sehen können, wurde der Stream geschlossen, bevor die äußere Ausnahme behandelt wurde, und die Datei `test.txt` enthält den Text `test1`, was bedeutet, dass die Puffer geleert und, obwohl die Ausnahme übertragen auf den Datenträger geschrieben wurden die Steuerung an die äußere Ausnahmehandler.

Beachten Sie, dass die `try...with` -Konstrukt ist ein separater Konstrukt aus der `try...finally` erstellen. Aus diesem Grund Wenn Ihr Code erfordert, beide dass eine `with` Block und ein `finally` blockieren, müssen Sie die zwei Konstrukte, wie im folgenden Codebeispiel dargestellt zu schachteln.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

Im Kontext des Berechnungsausdrücke, einschließlich Sequenzausdrücke und asynchrone Workflows **try … schließlich** Ausdrücke können eine benutzerdefinierte Implementierung haben. Weitere Informationen finden Sie unter [Berechnungsausdrücke](../computation-expressions.md).


## <a name="see-also"></a>Siehe auch
[Ausnahmebehandlung](index.md)

[Ausnahmen: Der `try...with`-Ausdruck](the-try-with-expression.md)
