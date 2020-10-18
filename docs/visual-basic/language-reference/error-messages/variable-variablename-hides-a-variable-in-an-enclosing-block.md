---
title: Die Variable "<variablename>" verbirgt eine Variable in einem einschließenden Block.
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 408acaafd5e266266b5191313611b94b72a5c270
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161347"
---
# <a name="bc30616-variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="e6281-102">BC30616: die Variable " \<variablename> " verbirgt eine Variable in einem einschließenden Block.</span><span class="sxs-lookup"><span data-stu-id="e6281-102">BC30616: Variable '\<variablename>' hides a variable in an enclosing block</span></span>

<span data-ttu-id="e6281-103">Eine in einen-Block eingeschlossene Variable hat denselben Namen wie eine andere lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="e6281-103">A variable enclosed in a block has the same name as another local variable.</span></span>

 <span data-ttu-id="e6281-104">**Fehler-ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="e6281-104">**Error ID:** BC30616</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e6281-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e6281-105">To correct this error</span></span>

- <span data-ttu-id="e6281-106">Benennen Sie die Variable im eingeschlossenen Block so um, dass Sie nicht mit allen anderen lokalen Variablen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="e6281-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="e6281-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e6281-107">For example:</span></span>

    ```vb
    Dim a, b, x As Integer
    If a = b Then
       Dim y As Integer = 20 ' Uniquely named block variable.
    End If
    ```

- <span data-ttu-id="e6281-108">Eine häufige Ursache für diesen Fehler ist die Verwendung von `Catch e As Exception` innerhalb eines Ereignis Handlers.</span><span class="sxs-lookup"><span data-stu-id="e6281-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="e6281-109">Wenn dies der Fall ist, benennen Sie die `Catch` Block Variable `ex` anstelle von `e` .</span><span class="sxs-lookup"><span data-stu-id="e6281-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>

- <span data-ttu-id="e6281-110">Eine weitere häufige Ursache für diesen Fehler ist der Versuch, auf eine lokale Variable zuzugreifen, die `Try` in einem Block in einem separaten Block deklariert ist `Catch` .</span><span class="sxs-lookup"><span data-stu-id="e6281-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="e6281-111">Um dies zu korrigieren, deklarieren Sie die Variable außerhalb der- `Try...Catch...Finally` Struktur.</span><span class="sxs-lookup"><span data-stu-id="e6281-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6281-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6281-112">See also</span></span>

- [<span data-ttu-id="e6281-113">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e6281-113">Try...Catch...Finally Statement</span></span>](../statements/try-catch-finally-statement.md)
- [<span data-ttu-id="e6281-114">Variablen Deklaration</span><span class="sxs-lookup"><span data-stu-id="e6281-114">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
