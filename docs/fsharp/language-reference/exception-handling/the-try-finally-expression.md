---
title: 'Ausnahmen: Der try...finally-Ausdruck (F#)'
description: Erfahren Sie, wie der F#-' try-finally "Ausdruck können Sie Bereinigungscode auszuführen, auch wenn Sie ein Codeblock eine Ausnahme auslöst.
ms.date: 05/16/2016
ms.openlocfilehash: 546a6b0619de6f51044600dc1ead73c6d5211299
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515171"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="f0141-103">Ausnahmen: Der try...finally-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="f0141-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="f0141-104">Die `try...finally` Ausdruck können Sie Bereinigungscode auszuführen, auch wenn Sie ein Codeblock eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="f0141-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="f0141-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0141-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="f0141-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0141-106">Remarks</span></span>

<span data-ttu-id="f0141-107">Die `try...finally` Ausdruck kann verwendet werden, zum Ausführen des Codes in *expression2* in der vorherigen Syntax unabhängig davon, ob eine Ausnahme, während der Ausführung des generiert wird *expression1*.</span><span class="sxs-lookup"><span data-stu-id="f0141-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="f0141-108">Der Typ des *expression2* trägt nicht auf den Wert des gesamten Ausdrucks ist; der Typ zurückgegeben, wenn eine Ausnahme auftritt, wird der letzte Wert im *expression1*.</span><span class="sxs-lookup"><span data-stu-id="f0141-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="f0141-109">Wenn eine Ausnahme auftritt, wird kein Wert zurückgegeben, und die ablaufsteuerung an den nächsten übereinstimmenden Ausnahmehandler der Aufrufliste nach oben übertragen.</span><span class="sxs-lookup"><span data-stu-id="f0141-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="f0141-110">Wenn kein Ausnahmehandler gefunden wird, wird das Programm beendet.</span><span class="sxs-lookup"><span data-stu-id="f0141-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="f0141-111">Bevor der Code in ein entsprechender Handler ausgeführt wird oder das Programm beendet wird, den Code in die `finally` Branch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0141-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="f0141-112">Der folgende Code veranschaulicht die Verwendung der `try...finally` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f0141-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="f0141-113">Die Ausgabe an die Konsole ist wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="f0141-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="f0141-114">Wie Sie in der Ausgabe sehen, wurde der Stream geschlossen, bevor die äußere Ausnahme behandelt wurde, und die Datei `test.txt` enthält den Text `test1`, was bedeutet, dass die Puffer geleert und auf den Datenträger, auch wenn die Ausnahme übertragen geschrieben wurden die Steuerung an den äußeren Ausnahmehandler übergeben.</span><span class="sxs-lookup"><span data-stu-id="f0141-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="f0141-115">Beachten Sie, dass die `try...with` -Konstrukt ist ein separater Konstrukt aus der `try...finally` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0141-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="f0141-116">Aus diesem Grund Wenn der Code sowohl erfordert eine `with` Block und einem `finally` blockieren, müssen Sie die zwei Konstrukte schachteln, wie im folgenden Codebeispiel wird.</span><span class="sxs-lookup"><span data-stu-id="f0141-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="f0141-117">Im Kontext des Berechnungsausdrücke, einschließlich der Sequence-Ausdrücke und asynchrone Workflows, **try-finally** Ausdrücke können eine benutzerdefinierte Implementierung haben.</span><span class="sxs-lookup"><span data-stu-id="f0141-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="f0141-118">Weitere Informationen finden Sie unter [Berechnungsausdrücke](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f0141-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0141-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0141-119">See also</span></span>

- [<span data-ttu-id="f0141-120">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="f0141-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="f0141-121">Ausnahmen: Der `try...with`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="f0141-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
