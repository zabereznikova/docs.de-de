---
title: Der Typ für die Variable '<variablename>' wird nicht abgeleitet, da er an ein Feld in einem einschließenden Bereich gebunden ist
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: 1ad7b9d0a610842dd6c50ee198f5bb5fa3eb68cf
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870485"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="90293-102">Der Typ für die Variable '\<variablename>' wird nicht abgeleitet, da er an ein Feld in einem einschließenden Bereich gebunden ist</span><span class="sxs-lookup"><span data-stu-id="90293-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>

<span data-ttu-id="90293-103">Der Typ für die Variable ' \<variablename> ' wird nicht abgeleitet, da er an ein Feld in einem einschließenden Bereich gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="90293-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="90293-104">Ändern Sie den Namen von ' \<variablename> ', oder verwenden Sie den voll qualifizierten Namen (z. b. ' me. variablename ' oder ' MyBase. variablename ').</span><span class="sxs-lookup"><span data-stu-id="90293-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>

<span data-ttu-id="90293-105">Eine Schleifensteuerungsvariable im Code hat den gleichen Namen wie ein Feld der Klasse oder andere einschließende Bereiche.</span><span class="sxs-lookup"><span data-stu-id="90293-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="90293-106">Da die Steuerelementvariable ohne eine `As`-Klausel verwendet wird, ist sie an das Feld im einschließenden Bereich gebunden, und der Compiler erstellt weder eine neue Variable für sie noch leitet er ihren Typ ab.</span><span class="sxs-lookup"><span data-stu-id="90293-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>

<span data-ttu-id="90293-107">Im folgenden Beispiel `Index` ist die Steuerelementvariable in der `For`-Anweisung an das `Index`-Feld in der `Customer`-Klasse gebunden.</span><span class="sxs-lookup"><span data-stu-id="90293-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="90293-108">Vom Compiler wird keine neue Variable für die Steuerelementvariable `Index` erstellt und ihr Typ nicht abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="90293-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

    ' The following line will raise this warning.
        For Index = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

<span data-ttu-id="90293-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="90293-109">By default, this message is a warning.</span></span> <span data-ttu-id="90293-110">Weitere Informationen zum Ausblenden von Warnungen und zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="90293-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="90293-111">**Fehler-ID:** BC42110</span><span class="sxs-lookup"><span data-stu-id="90293-111">**Error ID:** BC42110</span></span>

### <a name="to-address-this-warning"></a><span data-ttu-id="90293-112">So reagieren Sie auf diese Warnung</span><span class="sxs-lookup"><span data-stu-id="90293-112">To address this warning</span></span>

- <span data-ttu-id="90293-113">Machen Sie die Schleifensteuerungsvariable lokal verfügbar, indem Sie ihren Namen in einen Bezeichner ändern, der nicht mit dem Feldnamen der Klasse übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="90293-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>

  ```vb
  For I = 1 To 10
  ```

- <span data-ttu-id="90293-114">Stellen Sie sicher, dass die Schleifensteuerungsvariable an das Klassenfeld gebunden ist, indem Sie dem Variablennamen als Präfix `Me.` voranstellen.</span><span class="sxs-lookup"><span data-stu-id="90293-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>

  ```vb
  For Me.Index = 1 To 10
  ```

- <span data-ttu-id="90293-115">Verwenden Sie eine `As`-Klausel, um einen Typ für die Schleifensteuerungsvariable festzulegen, anstatt sich auf den lokalen Typrückschluss zu verlassen.</span><span class="sxs-lookup"><span data-stu-id="90293-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a><span data-ttu-id="90293-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90293-116">Example</span></span>

 <span data-ttu-id="90293-117">Der folgende Code veranschaulicht das vorherige Beispiel mit der ersten Korrektur.</span><span class="sxs-lookup"><span data-stu-id="90293-117">The following code shows the earlier example with the first correction in place.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

        For I = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="90293-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90293-118">See also</span></span>

- [<span data-ttu-id="90293-119">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="90293-119">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="90293-120">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="90293-120">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="90293-121">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="90293-121">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="90293-122">Vorgehensweise: Verweisen auf die aktuelle Instanz eines Objekts</span><span class="sxs-lookup"><span data-stu-id="90293-122">How to: Refer to the Current Instance of an Object</span></span>](../../programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="90293-123">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="90293-123">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="90293-124">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="90293-124">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
