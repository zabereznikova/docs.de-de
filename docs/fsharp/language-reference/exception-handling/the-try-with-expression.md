---
title: 'Ausnahmen: Der try...with-Ausdruck (F#)'
description: Erfahren Sie, wie der F#-"try...with" Ausdruck für die Ausnahmebehandlung zu verwenden.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 06e40b79fc1958918dc0615ce9d1004e0a6e74a5
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-trywith-expression"></a>Ausnahmen: Der try...with-Ausdruck

In diesem Thema wird beschrieben, die `try...with` Ausdruck, der Ausdruck, der für die Ausnahmebehandlung in der Programmiersprache f# verwendet wird.


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
Die `try...with` Ausdruck wird verwendet, um die Behandlung von Ausnahmen in F# erläutert werden. Ähnliches gilt für die `try...catch` -Anweisung in c#. In der vorherigen Syntax wird der Code in *expression1* möglicherweise eine Ausnahme generiert. Die `try...with` Ausdruck gibt einen Wert zurück. Wenn keine Ausnahme ausgelöst wird, wird der gesamte Ausdruck gibt den Wert der *expression1*. Wenn eine Ausnahme ausgelöst wird, jede *Muster* wiederum verglichen wird, mit der Ausnahme und für das erste übereinstimmende Muster für den entsprechenden *Ausdruck*, bekannt als die *Ausnahmehandler*für die Verzweigung wird ausgeführt, und der gesamte Ausdruck den Wert des Ausdrucks in dieser Ausnahmehandler gibt. Wenn keine Muster übereinstimmt, wird die Ausnahme der Aufrufliste weitergegeben, bis ein entsprechender Handler gefunden wird. Die Typen der von jeder Ausdruck in der Ausnahmehandler zurückgegebenen Werte übereinstimmen der Rückgabetyp der Ausdruck in der `try` Block.

In vielen Fällen bedeutet die Tatsache, dass auch ein Fehler aufgetreten ist, dass es keinen gültiger Wert, der die Ausdrücke in jeder Ausnahmehandler zurückgegeben werden kann. Ein häufig verwendetes Muster ist die Angabe des Ausdrucks ein Optionstyp werden festgelegt. Im folgenden Codebeispiel wird veranschaulicht, dieses Muster.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

Ausnahmen können Ausnahmen von .NET sein, oder es F#-Ausnahmen. Sie können mit F#-Ausnahmen definieren die `exception` Schlüsselwort.

Eine Vielzahl von Mustern können Sie den Ausnahmetyp und andere Bedingungen gefiltert; in der folgenden Tabelle werden die Optionen zusammengefasst.


|Muster|Beschreibung|
|-------|-----------|
|:? *Typ der Ausnahme*|Entspricht den angegebenen .NET Ausnahmetyp an.|
|:? *Ausnahmetyp* als *Bezeichner*|Entspricht den angegebenen .NET Ausnahmetyp, aber bietet der Ausnahme einen benannten Wert.|
|*Name des Ausnahmefehlers*(*Argumente*)|Einen f#-Ausnahmetyp entspricht, und bindet die Argumente.|
|*identifier*|Entspricht einer beliebigen Ausnahme und bindet den Namen an das Ausnahmeobjekt. Entspricht **:? System.Exception als *** Bezeichner*|
|*Bezeichner* Wenn *Bedingung*|Entspricht einer beliebigen Ausnahme aus, wenn die Bedingung "true" ergibt.|

## <a name="examples"></a>Beispiele
Die folgenden Codebeispiele veranschaulichen die Verwendung der verschiedenen Ausnahme-Handler-Muster.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
Die `try...with` Konstrukt ist ein separater Ausdruck aus der `try...finally` Ausdruck. Aus diesem Grund Wenn Code sowohl erfordert eine `with` Block und ein `finally` blockieren, müssen die beiden Ausdrücke schachteln.

>[!NOTE] 
Sie können `try...with` in asynchronen Workflows und anderen Berechnungsausdrücken, in dem Fall wird einer angepassten Version von der `try...with` Ausdruck verwendet wird. Weitere Informationen finden Sie unter [asynchrone Workflows](../asynchronous-workflows.md), und [Berechnungsausdrücke](../computation-expressions.md).


## <a name="see-also"></a>Siehe auch
[Ausnahmebehandlung](index.md)

[Ausnahmetypen](exception-types.md)

[Ausnahmen: Der `try...finally`-Ausdruck](the-try-finally-expression.md)
