---
title: 'Ausnahmen: Der try...with-Ausdruck'
description: Erfahren Sie, wie Sie F# "Try... with ' Ausdruck für die Ausnahmebehandlung.
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630245"
---
# <a name="exceptions-the-trywith-expression"></a>Ausnahmen: Der try...with-Ausdruck

In diesem Thema wird beschrieben, die `try...with` Ausdruck, der Ausdruck, der für die Ausnahmebehandlung in der Sprache F# verwendet wird.

## <a name="syntax"></a>Syntax

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a>Hinweise

Der `try...with` Ausdruck wird zum Behandeln von Ausnahmen in F#verwendet. Sie ähnelt der `try...catch` -Anweisung in. C# In der vorangehenden Syntax generiert der Code in *expression1* möglicherweise eine Ausnahme. Der `try...with` Ausdruck gibt einen Wert zurück. Wenn keine Ausnahme ausgelöst wird, gibt der gesamte Ausdruck den Wert von *expression1*zurück. Wenn eine Ausnahme ausgelöst wird, wird jedes *Muster* wiederum mit der Ausnahme verglichen, und für das erste übereinstimmende Muster wird der entsprechende *Ausdruck*, der als *Ausnahmehandler*bezeichnet wird, für diesen Branch ausgeführt und der allgemeine Ausdruck Gibt den Wert des Ausdrucks in diesem Ausnahmehandler zurück. Wenn kein Muster übereinstimmt, wird die aufrufsstapel von der Ausnahme weitergegeben, bis ein übereinstimmender Handler gefunden wird. Die Typen der Werte, die von jedem Ausdruck in den Ausnahme Handlern zurückgegeben werden, müssen mit dem Typ identisch sein `try` , der vom Ausdruck im-Block zurückgegeben wird.

Häufig bedeutet die Tatsache, dass ein Fehler aufgetreten ist, dass es keinen gültigen Wert gibt, der von den Ausdrücken in den einzelnen Ausnahme Handlern zurückgegeben werden kann. Ein häufiges Muster ist, dass der Typ des Ausdrucks ein Optionstyp ist. Dieses Muster wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

Ausnahmen können .NET-Ausnahmen oder F# Ausnahmen sein. Ausnahmen können mithilfe F# des `exception` -Schlüssel Worts definiert werden.

Sie können eine Vielzahl von Mustern verwenden, um nach dem Ausnahmetyp und anderen Bedingungen zu filtern. die Optionen sind in der folgenden Tabelle zusammengefasst.

|Muster|Beschreibung|
|-------|-----------|
|:? *Ausnahmetyp*|Entspricht dem angegebenen .net-Ausnahmetyp.|
|:? *Exception-Typ* als *Bezeichner*|Entspricht dem angegebenen .net-Ausnahmetyp, gibt jedoch der Ausnahme einen benannten Wert.|
|*Ausnahme Name* (*Argumente*)|Entspricht einem F# Ausnahmetyp und bindet die Argumente.|
|*identifier*|Findet eine Übereinstimmung mit jeder Ausnahme und bindet den Namen an das Ausnahme Objekt. Äquivalent zu **:? System. Exception als**_Bezeichner_|
|*Bezeichner* , wenn *Bedingung*|Findet eine Übereinstimmung mit jeder Ausnahme, wenn die Bedingung erfüllt ist.|

## <a name="examples"></a>Beispiele

Die folgenden Codebeispiele veranschaulichen die Verwendung der verschiedenen Ausnahmehandler.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> Das `try...with` Konstrukt ist ein separater Ausdruck aus dem `try...finally` Ausdruck. Wenn Ihr Code also sowohl einen `with` -Block als auch einen `finally` -Block erfordert, müssen Sie die beiden Ausdrücke verschachteln.

> [!NOTE]
> Sie können in `try...with` asynchronen Workflows und anderen Berechnungs Ausdrücken verwenden. in diesem Fall wird eine angepasste Version `try...with` des Ausdrucks verwendet. Weitere Informationen finden Sie unter [asynchrone Workflows](../asynchronous-workflows.md)und [Berechnungs Ausdrücke](../computation-expressions.md).

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Der `try...finally` Ausdruck](the-try-finally-expression.md)
