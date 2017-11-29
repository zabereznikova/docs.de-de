---
title: 'Ausnahmen: Der try...finally-Ausdruck (F#)'
description: "Erfahren Sie, wie die f#-' try … finally' Ausdruck ermöglicht es Ihnen, Bereinigungscode auszuführen, auch wenn Sie ein Codeblock eine Ausnahme auslöst."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: af06b20c-8d87-4496-a0aa-6fdfe8b3a786
ms.openlocfilehash: 2e2445c42bf8129ea81beef56cb725ac0e37d202
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="0ed85-104">Ausnahmen: Der try...finally-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="0ed85-104">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="0ed85-105">Die `try...finally` Ausdruck ermöglicht es Ihnen, Bereinigungscode auszuführen, auch wenn Sie ein Codeblock eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="0ed85-105">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="0ed85-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ed85-106">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="0ed85-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ed85-107">Remarks</span></span>
<span data-ttu-id="0ed85-108">Die `try...finally` -Ausdruck kann verwendet werden, um den Code in auszuführen *expression2* in der vorherigen Syntax unabhängig davon, ob eine Ausnahme, während der Ausführung des generiert wird *expression1*.</span><span class="sxs-lookup"><span data-stu-id="0ed85-108">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="0ed85-109">Der Typ des *expression2* trägt nicht auf den Wert des gesamten Ausdrucks; der Typ zurückgegeben, wenn eine Ausnahme nicht auftritt, ist der letzte Wert im *expression1*.</span><span class="sxs-lookup"><span data-stu-id="0ed85-109">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="0ed85-110">Wenn eine Ausnahme auftritt, wird kein Wert zurückgegeben, und die ablaufsteuerung an den passenden Ausnahmehandler oben in der Aufrufliste übertragen.</span><span class="sxs-lookup"><span data-stu-id="0ed85-110">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="0ed85-111">Wenn keine Ausnahmehandler gefunden wird, wird das Programm beendet.</span><span class="sxs-lookup"><span data-stu-id="0ed85-111">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="0ed85-112">Bevor der Code in einem entsprechenden Handler ausgeführt wird oder das Programm beendet wird, den Code in der `finally` Verzweigung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0ed85-112">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="0ed85-113">Der folgende Code veranschaulicht die Verwendung von der `try...finally` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0ed85-113">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="0ed85-114">Die Ausgabe an die Konsole lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="0ed85-114">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="0ed85-115">Wie Sie aus der Ausgabe sehen können, wurde der Stream geschlossen, bevor die äußere Ausnahme behandelt wurde, und die Datei `test.txt` enthält den Text `test1`, was bedeutet, dass die Puffer geleert und, obwohl die Ausnahme übertragen auf den Datenträger geschrieben wurden die Steuerung an die äußere Ausnahmehandler.</span><span class="sxs-lookup"><span data-stu-id="0ed85-115">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="0ed85-116">Beachten Sie, dass die `try...with` -Konstrukt ist ein separater Konstrukt aus der `try...finally` erstellen.</span><span class="sxs-lookup"><span data-stu-id="0ed85-116">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="0ed85-117">Aus diesem Grund Wenn Ihr Code erfordert, beide dass eine `with` Block und ein `finally` blockieren, müssen Sie die zwei Konstrukte, wie im folgenden Codebeispiel dargestellt zu schachteln.</span><span class="sxs-lookup"><span data-stu-id="0ed85-117">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="0ed85-118">Im Kontext des Berechnungsausdrücke, einschließlich Sequenzausdrücke und asynchrone Workflows **try … schließlich** Ausdrücke können eine benutzerdefinierte Implementierung haben.</span><span class="sxs-lookup"><span data-stu-id="0ed85-118">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="0ed85-119">Weitere Informationen finden Sie unter [Berechnungsausdrücke](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0ed85-119">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="0ed85-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ed85-120">See Also</span></span>
[<span data-ttu-id="0ed85-121">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="0ed85-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="0ed85-122">Ausnahmen: Der `try...with`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="0ed85-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
