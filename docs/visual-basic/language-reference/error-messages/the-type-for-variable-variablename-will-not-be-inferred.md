---
title: Der Typ für die Variable &#39; &lt;Variablename&gt; &#39; wird nicht abgeleitet werden, da er auf ein Feld in einem einschließenden Bereich gebunden ist
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: 6adcc1c2a449c9192e488a5d714e1c3271568be0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672382"
---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="e4657-102">Der Typ für die Variable &#39; &lt;Variablename&gt; &#39; wird nicht abgeleitet werden, da er auf ein Feld in einem einschließenden Bereich gebunden ist</span><span class="sxs-lookup"><span data-stu-id="e4657-102">The type for variable &#39;&lt;variablename&gt;&#39; will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="e4657-103">Der Typ für die Variable "\<Variablenname >' wird nicht abgeleitet werden, da er auf ein Feld in einem einschließenden Bereich gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="e4657-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="e4657-104">Ändern Sie den Namen des "\<Variablenname >', oder verwenden Sie den vollqualifizierten Namen (z. B. 'Me.Variablenname' oder 'MyBase.Variablenname').</span><span class="sxs-lookup"><span data-stu-id="e4657-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="e4657-105">Eine Schleifensteuerungsvariable im Code hat den gleichen Namen wie ein Feld der Klasse oder andere einschließende Bereiche.</span><span class="sxs-lookup"><span data-stu-id="e4657-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="e4657-106">Da die Steuerelementvariable ohne eine `As`-Klausel verwendet wird, ist sie an das Feld im einschließenden Bereich gebunden, und der Compiler erstellt weder eine neue Variable für sie noch leitet er ihren Typ ab.</span><span class="sxs-lookup"><span data-stu-id="e4657-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="e4657-107">Im folgenden Beispiel `Index` ist die Steuerelementvariable in der `For`-Anweisung an das `Index`-Feld in der `Customer`-Klasse gebunden.</span><span class="sxs-lookup"><span data-stu-id="e4657-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="e4657-108">Vom Compiler wird keine neue Variable für die Steuerelementvariable `Index` erstellt und ihr Typ nicht abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="e4657-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
```  
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
  
 <span data-ttu-id="e4657-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="e4657-109">By default, this message is a warning.</span></span> <span data-ttu-id="e4657-110">Weitere Informationen zum Ausblenden von Warnungen und zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e4657-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e4657-111">**Fehler-ID:** BC42110</span><span class="sxs-lookup"><span data-stu-id="e4657-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="e4657-112">So reagieren Sie auf diese Warnung</span><span class="sxs-lookup"><span data-stu-id="e4657-112">To address this warning</span></span>  
  
-   <span data-ttu-id="e4657-113">Machen Sie die Schleifensteuerungsvariable lokal verfügbar, indem Sie ihren Namen in einen Bezeichner ändern, der nicht mit dem Feldnamen der Klasse übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e4657-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   <span data-ttu-id="e4657-114">Stellen Sie sicher, dass die Schleifensteuerungsvariable an das Klassenfeld gebunden ist, indem Sie dem Variablennamen als Präfix `Me.` voranstellen.</span><span class="sxs-lookup"><span data-stu-id="e4657-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   <span data-ttu-id="e4657-115">Verwenden Sie eine `As`-Klausel, um einen Typ für die Schleifensteuerungsvariable festzulegen, anstatt sich auf den lokalen Typrückschluss zu verlassen.</span><span class="sxs-lookup"><span data-stu-id="e4657-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="e4657-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4657-116">Example</span></span>  
 <span data-ttu-id="e4657-117">Der folgende Code veranschaulicht das vorherige Beispiel mit der ersten Korrektur.</span><span class="sxs-lookup"><span data-stu-id="e4657-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="e4657-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4657-118">See also</span></span>
- [<span data-ttu-id="e4657-119">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e4657-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="e4657-120">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e4657-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="e4657-121">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e4657-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="e4657-122">Vorgehensweise: Verweisen Sie auf die aktuelle Instanz eines Objekts</span><span class="sxs-lookup"><span data-stu-id="e4657-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="e4657-123">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="e4657-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="e4657-124">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="e4657-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
