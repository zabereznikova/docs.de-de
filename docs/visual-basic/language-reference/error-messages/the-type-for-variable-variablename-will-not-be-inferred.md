---
title: "Der Typ für die Variable &quot;&lt;Variablename&gt;&quot; wird nicht abgeleitet werden, da es an ein Feld in einem einschließenden Bereich gebunden ist | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42110
- bc42110
dev_langs:
- VB
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 0f954fda84c9fd1a4af5315be2329de117e6d169
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="37d48-102">Der Typ für die Variable "&lt;Variablename&gt;' wird nicht abgeleitet werden, da es an ein Feld in einem einschließenden Bereich gebunden ist</span><span class="sxs-lookup"><span data-stu-id="37d48-102">The type for variable &#39;&lt;variablename&gt;&#39; will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="37d48-103">Der Typ für die Variable "\<Variablename >' wird nicht abgeleitet werden, da es an ein Feld in einem einschließenden Bereich gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="37d48-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="37d48-104">Ändern Sie entweder den Namen des "\<Variablename >', oder verwenden Sie den vollqualifizierten Namen (z. B. 'Me.Variablenname' oder 'MyBase.Variablenname').</span><span class="sxs-lookup"><span data-stu-id="37d48-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="37d48-105">Eine Schleifensteuerungsvariable im Code hat den gleichen Namen wie ein Feld der Klasse oder andere einschließende Bereiche.</span><span class="sxs-lookup"><span data-stu-id="37d48-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="37d48-106">Da die Steuerelementvariable ohne eine `As`-Klausel verwendet wird, ist sie an das Feld im einschließenden Bereich gebunden, und der Compiler erstellt weder eine neue Variable für sie noch leitet er ihren Typ ab.</span><span class="sxs-lookup"><span data-stu-id="37d48-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="37d48-107">Im folgenden Beispiel `Index` ist die Steuerelementvariable in der `For`-Anweisung an das `Index`-Feld in der `Customer`-Klasse gebunden.</span><span class="sxs-lookup"><span data-stu-id="37d48-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="37d48-108">Vom Compiler wird keine neue Variable für die Steuerelementvariable `Index` erstellt und ihr Typ nicht abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="37d48-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
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
  
 <span data-ttu-id="37d48-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="37d48-109">By default, this message is a warning.</span></span> <span data-ttu-id="37d48-110">Informationen zum Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="37d48-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="37d48-111">**Fehler-ID:** BC42110</span><span class="sxs-lookup"><span data-stu-id="37d48-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="37d48-112">So reagieren Sie auf diese Warnung</span><span class="sxs-lookup"><span data-stu-id="37d48-112">To address this warning</span></span>  
  
-   <span data-ttu-id="37d48-113">Machen Sie die Schleifensteuerungsvariable lokal verfügbar, indem Sie ihren Namen in einen Bezeichner ändern, der nicht mit dem Feldnamen der Klasse übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="37d48-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   <span data-ttu-id="37d48-114">Stellen Sie sicher, dass die Schleifensteuerungsvariable an das Klassenfeld gebunden ist, indem Sie dem Variablennamen als Präfix `Me.` voranstellen.</span><span class="sxs-lookup"><span data-stu-id="37d48-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   <span data-ttu-id="37d48-115">Verwenden Sie eine `As`-Klausel, um einen Typ für die Schleifensteuerungsvariable festzulegen, anstatt sich auf den lokalen Typrückschluss zu verlassen.</span><span class="sxs-lookup"><span data-stu-id="37d48-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="37d48-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37d48-116">Example</span></span>  
 <span data-ttu-id="37d48-117">Der folgende Code veranschaulicht das vorherige Beispiel mit der ersten Korrektur.</span><span class="sxs-lookup"><span data-stu-id="37d48-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="37d48-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37d48-118">See Also</span></span>  
 <span data-ttu-id="37d48-119">[Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="37d48-119">[Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="37d48-120"> [Für jede... Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="37d48-120"> [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="37d48-121"> [Für... Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="37d48-121"> [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) </span></span>  
<span data-ttu-id="37d48-122"> [Gewusst wie: Verweisen auf die aktuelle Instanz eines Objekts](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="37d48-122"> [How to: Refer to the Current Instance of an Object](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span></span>  
<span data-ttu-id="37d48-123"> [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="37d48-123"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="37d48-124"> [Me, My, MyBase und MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="37d48-124"> [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>

