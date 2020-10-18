---
title: Der Lambdaausdruck wird nicht aus diesem Ereignishandler entfernt
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 5a30e63044b51f8176dfeebdcc9eb8fd517739ae
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163115"
---
# <a name="bc42326-lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="da755-102">BC42326: der Lambda Ausdruck wird nicht aus diesem Ereignishandler entfernt.</span><span class="sxs-lookup"><span data-stu-id="da755-102">BC42326: Lambda expression will not be removed from this event handler</span></span>

<span data-ttu-id="da755-103">Der Lambda-Ausdruck wird nicht aus diesem Ereignishandler entfernt.</span><span class="sxs-lookup"><span data-stu-id="da755-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="da755-104">Weisen Sie den Lambda-Ausdruck einer Variablen zu, und verwenden Sie die Variable, um das Ereignis hinzuzufügen und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="da755-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>

<span data-ttu-id="da755-105">Wenn Lambda-Ausdrücke mit Ereignis Handlern verwendet werden, wird das erwartete Verhalten möglicherweise nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da755-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="da755-106">Der Compiler generiert eine neue Methode für jede Lambda-Ausdrucks Definition, auch wenn diese identisch sind.</span><span class="sxs-lookup"><span data-stu-id="da755-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="da755-107">Der folgende Code zeigt daher an `False` .</span><span class="sxs-lookup"><span data-stu-id="da755-107">Therefore, the following code displays `False`.</span></span>

```vb
Module Module1

    Sub Main()
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1
        Console.WriteLine(fun1 = fun2)
    End Sub

    Delegate Function ChangeInteger(ByVal x As Integer) As Integer

End Module
```

<span data-ttu-id="da755-108">Wenn Lambda-Ausdrücke mit Ereignis Handlern verwendet werden, kann dies zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="da755-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="da755-109">Im folgenden Beispiel wird der von hinzugefügte Lambda-Ausdruck `AddHandler` nicht durch die- `RemoveHandler` Anweisung entfernt.</span><span class="sxs-lookup"><span data-stu-id="da755-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>

```vb
Module Module1

    Event ProcessInteger(ByVal x As Integer)

    Sub Main()

        ' The following line adds one listener to the event.
        AddHandler ProcessInteger, Function(m As Integer) m

        ' The following statement searches the current listeners
        ' for a match to remove. However, this lambda is not the same
        ' as the previous one, so nothing is removed.
        RemoveHandler ProcessInteger, Function(m As Integer) m

    End Sub
End Module
```

<span data-ttu-id="da755-110">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="da755-110">By default, this message is a warning.</span></span> <span data-ttu-id="da755-111">Weitere Informationen zum Ausblenden von Warnungen und zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="da755-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="da755-112">**Fehler-ID:** BC42326</span><span class="sxs-lookup"><span data-stu-id="da755-112">**Error ID:** BC42326</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="da755-113">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="da755-113">To correct this error</span></span>

<span data-ttu-id="da755-114">Um die Warnung zu vermeiden und den Lambda-Ausdruck zu entfernen, weisen Sie den Lambda-Ausdruck einer Variablen zu, und verwenden Sie die-Variable in der `AddHandler` -und der- `RemoveHandler` Anweisung, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="da755-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>

```vb
Module Module1

    Event ProcessInteger(ByVal x As Integer)

    Dim PrintHandler As ProcessIntegerEventHandler

    Sub Main()

        ' Assign the lambda expression to a variable.
        PrintHandler = Function(m As Integer) m

        ' Use the variable to add the listener.
        AddHandler ProcessInteger, PrintHandler

        ' Use the variable again when you want to remove the listener.
        RemoveHandler ProcessInteger, PrintHandler

    End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="da755-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da755-115">See also</span></span>

- [<span data-ttu-id="da755-116">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="da755-116">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="da755-117">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="da755-117">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="da755-118">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="da755-118">Events</span></span>](../../programming-guide/language-features/events/index.md)
