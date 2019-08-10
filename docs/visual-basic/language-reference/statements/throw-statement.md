---
title: Throw-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 9680700267f17c8e316de351fead61f1dc4aded0
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68869023"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="1dbcc-102">Throw-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1dbcc-102">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="1dbcc-103">Löst eine Ausnahme in einer Prozedur aus.</span><span class="sxs-lookup"><span data-stu-id="1dbcc-103">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="1dbcc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1dbcc-104">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="1dbcc-105">Segment</span><span class="sxs-lookup"><span data-stu-id="1dbcc-105">Part</span></span>

`expression`\
<span data-ttu-id="1dbcc-106">Stellt Informationen über die Ausnahme bereit, die ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="1dbcc-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="1dbcc-107">Optional, wenn in einer `Catch` -Anweisung gespeichert; andernfalls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1dbcc-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="1dbcc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1dbcc-108">Remarks</span></span>

<span data-ttu-id="1dbcc-109">Die `Throw` -Anweisung löst eine Ausnahme aus, die Sie mit strukturiertem Ausnahme Behandlungs`Try`Code behandeln können (... `Catch`... ) oder unstrukturierter Ausnahme Behandlungs Code (`On Error GoTo`). `Finally`</span><span class="sxs-lookup"><span data-stu-id="1dbcc-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="1dbcc-110">Sie können die `Throw` -Anweisung verwenden, um Fehler in Ihrem Code abzufangen, da Visual Basic die aufrufsstapel nach oben verschiebt, bis der entsprechende Ausnahme Behandlungs Code gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="1dbcc-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="1dbcc-111">Eine `Throw` -Anweisung ohne-Ausdruck kann nur in einer `Catch` -Anweisung verwendet werden. in diesem Fall löst die-Anweisung die Ausnahme erneut aus, `Catch` die zurzeit von der-Anweisung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="1dbcc-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="1dbcc-112">Die `Throw` -Anweisung setzt die-aufrufsstapel für die `expression` Ausnahme zurück.</span><span class="sxs-lookup"><span data-stu-id="1dbcc-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="1dbcc-113">Wenn `expression` nicht angegeben wird, bleibt die-aufrufsstapel unverändert.</span><span class="sxs-lookup"><span data-stu-id="1dbcc-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="1dbcc-114">Sie können über die <xref:System.Exception.StackTrace%2A> -Eigenschaft auf die-aufrufsstapel für die Ausnahme zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1dbcc-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="1dbcc-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1dbcc-115">Example</span></span>

<span data-ttu-id="1dbcc-116">Im folgenden Code wird die `Throw` -Anweisung verwendet, um eine Ausnahme auszulösen:</span><span class="sxs-lookup"><span data-stu-id="1dbcc-116">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="1dbcc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1dbcc-117">See also</span></span>

- [<span data-ttu-id="1dbcc-118">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1dbcc-118">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="1dbcc-119">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1dbcc-119">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
