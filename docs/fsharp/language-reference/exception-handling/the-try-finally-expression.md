---
title: 'Ausnahmen: Der try...finally-Ausdruck'
description: Erfahren Sie, F# wie die "Try... mithilfe von "Expression" können Sie auch dann Bereinigungs Code ausführen, wenn ein Codeblock eine Ausnahme auslöst.
ms.date: 05/16/2016
ms.openlocfilehash: 0ddb64ac13b307404864ec5b54f26fd8a7a3d7d8
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083008"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="a0cb7-103">Ausnahmen: Der try...finally-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="a0cb7-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="a0cb7-104">Der `try...finally` Ausdruck ermöglicht das Ausführen von Bereinigungs Code, auch wenn ein Codeblock eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0cb7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0cb7-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="a0cb7-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0cb7-106">Remarks</span></span>

<span data-ttu-id="a0cb7-107">Der `try...finally` Ausdruck kann verwendet werden, um den Code in *expression2* in der vorangehenden Syntax auszuführen, unabhängig davon, ob während der Ausführung von *expression1*eine Ausnahme generiert wird.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="a0cb7-108">Der *expression2* -Typ trägt nicht zum Wert des gesamten Ausdrucks bei. der Typ, der zurückgegeben wird, wenn keine Ausnahme auftritt, ist der letzte Wert in *expression1*.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="a0cb7-109">Wenn eine Ausnahme auftritt, wird kein Wert zurückgegeben, und die Ablauf Steuerung wird an den nächsten übereinstimmenden Ausnahmehandler in der aufrufsstapel übertragen.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="a0cb7-110">Wenn kein Ausnahmehandler gefunden wird, wird das Programm beendet.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="a0cb7-111">Bevor der Code in einem übereinstimmenden Handler ausgeführt oder das Programm beendet wird, wird der `finally` Code in der Verzweigung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="a0cb7-112">Der folgende Code veranschaulicht die Verwendung des `try...finally` -Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="a0cb7-113">Die Ausgabe an die Konsole lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-113">The output to the console is as follows.</span></span>

```console
Closing stream
Exception handled.
```

<span data-ttu-id="a0cb7-114">Wie Sie in der Ausgabe sehen können, wurde der Stream geschlossen, bevor die äußere Ausnahme behandelt wurde, und die `test.txt` Datei enthält den `test1`Text, der angibt, dass die Puffer geleert und auf den Datenträger geschrieben wurden, obwohl die Ausnahme übertragen wurde. Steuern Sie den äußeren Ausnahmehandler.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="a0cb7-115">Beachten Sie, `try...with` dass das-Konstrukt ein separates Konstrukt `try...finally` aus dem-Konstrukt ist.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="a0cb7-116">Wenn Ihr Code also sowohl einen `with` -Block als auch einen `finally` -Block erfordert, müssen Sie die beiden-Konstrukte Schachteln, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="a0cb7-117">Versuchen Sie im Kontext von Berechnungs Ausdrücken, einschließlich Sequenz Ausdrücken und asynchronen Workflows, **... Schließlich** können Ausdrücke über eine benutzerdefinierte Implementierung verfügen.</span><span class="sxs-lookup"><span data-stu-id="a0cb7-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="a0cb7-118">Weitere Informationen finden Sie unter [Berechnungs Ausdrücke](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a0cb7-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0cb7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0cb7-119">See also</span></span>

- [<span data-ttu-id="a0cb7-120">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="a0cb7-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="a0cb7-121">Ausnahmen: Der `try...with` Ausdruck</span><span class="sxs-lookup"><span data-stu-id="a0cb7-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
