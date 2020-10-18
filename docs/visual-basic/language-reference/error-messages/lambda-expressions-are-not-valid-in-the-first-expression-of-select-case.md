---
title: Lambda-Ausdrücke sind im ersten Ausdruck einer 'Select Case'-Anweisung nicht gültig
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 448a685a7c174ce212389842c31066f1c4557cdf
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162530"
---
# <a name="bc36635-lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="efd37-102">BC36635: Lambda Ausdrücke sind im ersten Ausdruck einer "Select Case"-Anweisung nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="efd37-102">BC36635: Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>

<span data-ttu-id="efd37-103">Ein Lambda-Ausdruck kann nicht für den Test Ausdruck in einer-Anweisung verwendet werden `Select Case` .</span><span class="sxs-lookup"><span data-stu-id="efd37-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="efd37-104">Lambda-Ausdrucks Definitionen geben Funktionen zurück, und der Test Ausdruck einer `Select Case` Anweisung muss ein grundlegender Datentyp sein.</span><span class="sxs-lookup"><span data-stu-id="efd37-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>

 <span data-ttu-id="efd37-105">Der folgende Code verursacht diesen Fehler:</span><span class="sxs-lookup"><span data-stu-id="efd37-105">The following code causes this error:</span></span>

```vb
' Select Case (Function(arg) arg Is Nothing)
    ' List of the cases.
' End Select
```

 <span data-ttu-id="efd37-106">**Fehler-ID:** BC36635</span><span class="sxs-lookup"><span data-stu-id="efd37-106">**Error ID:** BC36635</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="efd37-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="efd37-107">To correct this error</span></span>

- <span data-ttu-id="efd37-108">Überprüfen Sie den Code, um festzustellen, ob eine andere bedingte Konstruktion für Sie geeignet wäre, z. B. eine `If...Then...Else` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="efd37-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>

- <span data-ttu-id="efd37-109">Möglicherweise haben Sie die Funktion aufgerufen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="efd37-109">You may have intended to call the function, as shown in the following code:</span></span>

```vb
Dim num? As Integer
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))
    ' List of the cases
End Select
```

## <a name="see-also"></a><span data-ttu-id="efd37-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efd37-110">See also</span></span>

- [<span data-ttu-id="efd37-111">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="efd37-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="efd37-112">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="efd37-112">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="efd37-113">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="efd37-113">Select...Case Statement</span></span>](../statements/select-case-statement.md)
