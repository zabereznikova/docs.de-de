---
title: Der Typ von '<variablename>' kann nicht abgeleitet werden, weil die Schleifenbegrenzungen und die step-Klausel nicht in denselben Typ konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 1330cbd6567b69df9bd811ced49c6df2e120a0b2
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161208"
---
# <a name="bc30982-type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="b87e5-102">BC30982: der Typ von " \<variablename> " kann nicht abgeleitet werden, da die Schleifen Begrenzungen und die Step-Variable nicht in denselben Typ erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="b87e5-102">BC30982: Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>

<span data-ttu-id="b87e5-103">Sie haben eine `For...Next` Schleife geschrieben, in der der Compiler einen Datentyp für die Schleifen Steuerungs Variable nicht ableiten kann, da die folgenden Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="b87e5-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>

- <span data-ttu-id="b87e5-104">Der Datentyp der Schleifensteuerungsvariablen wird nicht mit einer `As` -Klausel angegeben.</span><span class="sxs-lookup"><span data-stu-id="b87e5-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>

- <span data-ttu-id="b87e5-105">Die Schleifenbegrenzungen und die step-Variable enthalten mindestens zwei Datentypen.</span><span class="sxs-lookup"><span data-stu-id="b87e5-105">The loop bounds and step variable contain at least two data types.</span></span>

- <span data-ttu-id="b87e5-106">Zwischen den Datentypen sind keine Standard Konvertierungen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b87e5-106">No standard conversions exist between the data types.</span></span>

 <span data-ttu-id="b87e5-107">Daher kann der Compiler den Datentyp der Steuerungsvariablen einer Schleife nicht ableiten.</span><span class="sxs-lookup"><span data-stu-id="b87e5-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>

 <span data-ttu-id="b87e5-108">Im folgenden Beispiel ist die Step-Variable ein Zeichen, und die Schleifen Begrenzungen sind beide Integer.</span><span class="sxs-lookup"><span data-stu-id="b87e5-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="b87e5-109">Da es keine Standard Konvertierung zwischen Zeichen und ganzen Zahlen gibt, wird dieser Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="b87e5-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

<span data-ttu-id="b87e5-110">**Fehler-ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="b87e5-110">**Error ID:** BC30982</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b87e5-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b87e5-111">To correct this error</span></span>

- <span data-ttu-id="b87e5-112">Ändern Sie die Typen der Schleifen Begrenzungen und die Step-Variable nach Bedarf, damit mindestens einer der Typen ein Typ ist, zu dem die anderen erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="b87e5-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="b87e5-113">Ändern Sie im vorherigen Beispiel den Typ von `stepVar` in `Integer` .</span><span class="sxs-lookup"><span data-stu-id="b87e5-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>

  ```vb
  Dim stepVar = 1
  ```

  <span data-ttu-id="b87e5-114">Oder</span><span class="sxs-lookup"><span data-stu-id="b87e5-114">-or-</span></span>

  ```vb
  Dim stepVar As Integer = 1
  ```

- <span data-ttu-id="b87e5-115">Verwenden Sie explizite Konvertierungs Funktionen, um die Schleifen Begrenzungen und die Step-Variable in die entsprechenden Typen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="b87e5-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="b87e5-116">Wenden Sie im vorherigen Beispiel die- `Val` Funktion auf an `stepVar` .</span><span class="sxs-lookup"><span data-stu-id="b87e5-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a><span data-ttu-id="b87e5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b87e5-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="b87e5-118">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b87e5-118">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="b87e5-119">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b87e5-119">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="b87e5-120">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="b87e5-120">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="b87e5-121">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b87e5-121">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="b87e5-122">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="b87e5-122">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="b87e5-123">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="b87e5-123">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
