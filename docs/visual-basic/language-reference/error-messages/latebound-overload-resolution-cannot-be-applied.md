---
title: Die spät gebundene Überladungsauflösung kann nicht auf "<procedurename>" angewendet werden, da die zugreifende Instanz ein Schnittstellentyp ist.
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 090ec6f3bbf56350fda2ab15c974b0bc6b15e3d3
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162517"
---
# <a name="bc30933-latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="3870c-102">BC30933: die lategebundene Überladungs Auflösung kann nicht auf "" angewendet werden, \<procedurename> da die Zugriffs Instanz ein Schnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="3870c-102">BC30933: Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>

<span data-ttu-id="3870c-103">Der Compiler versucht, einen Verweis auf eine überladene Eigenschaft oder Prozedur aufzulösen, aber der Verweis schlägt fehl, da ein Argument vom Typ ist `Object` und das verweisende Objekt den Datentyp einer Schnittstelle aufweist.</span><span class="sxs-lookup"><span data-stu-id="3870c-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="3870c-104">Das- `Object` Argument zwingt den Compiler, den Verweis als spät gebunden aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="3870c-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>

<span data-ttu-id="3870c-105">In diesen Fällen löst der Compiler die Überladung durch die implementierende Klasse anstelle der zugrunde liegenden Schnittstelle auf.</span><span class="sxs-lookup"><span data-stu-id="3870c-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="3870c-106">Wenn die Klasse eine der überladenen Versionen umbenennt, betrachtet der Compiler diese Version nicht als Überladung, da der Name anders ist.</span><span class="sxs-lookup"><span data-stu-id="3870c-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="3870c-107">Dies bewirkt wiederum, dass der Compiler die umbenannte Version ignoriert, wenn es möglicherweise die richtige Wahl war, den Verweis aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="3870c-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>

<span data-ttu-id="3870c-108">**Fehler-ID:** BC30933</span><span class="sxs-lookup"><span data-stu-id="3870c-108">**Error ID:** BC30933</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="3870c-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="3870c-109">To correct this error</span></span>

- <span data-ttu-id="3870c-110">Verwenden `CType` Sie, um das-Argument von `Object` in den Typ umzuwandeln, der von der Signatur der aufzurufenden Überladung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3870c-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>

  <span data-ttu-id="3870c-111">Beachten Sie, dass es nicht hilfreich ist, das verweisende Objekt in die zugrunde liegende-Schnittstelle umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="3870c-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="3870c-112">Sie müssen das-Argument umwandeln, um diesen Fehler zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="3870c-112">You must cast the argument to avoid this error.</span></span>

## <a name="example"></a><span data-ttu-id="3870c-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3870c-113">Example</span></span>

<span data-ttu-id="3870c-114">Im folgenden Beispiel wird ein Aufruf einer überladenen `Sub` Prozedur veranschaulicht, die diesen Fehler zur Kompilierzeit verursacht.</span><span class="sxs-lookup"><span data-stu-id="3870c-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>

```vb
Module m1
    Interface i1
        Sub s1(ByVal p1 As Integer)
        Sub s1(ByVal p1 As Double)
    End Interface
    Class c1
        Implements i1
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1
        End Sub
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1
        End Sub
    End Class
    Sub Main()
        Dim refer As i1 = New c1
        Dim o1 As Object = 3.1415
        ' The following reference is INVALID and causes a compiler error.
        refer.s1(o1)
    End Sub
End Module
```

<span data-ttu-id="3870c-115">Wenn der Compiler im vorherigen Beispiel den-Aufrufvorgang `s1` als geschrieben hat, würde die Auflösung durch die-Klasse `c1` anstelle der-Schnittstelle stattfinden `i1` .</span><span class="sxs-lookup"><span data-stu-id="3870c-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="3870c-116">Dies bedeutet, dass der Compiler nicht in Erwägung zieht `s2` , weil der Name in anders ist `c1` , obwohl er die richtige Wahl ist, wie durch definiert `i1` .</span><span class="sxs-lookup"><span data-stu-id="3870c-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>

<span data-ttu-id="3870c-117">Sie können den Fehler beheben, indem Sie den-Befehl in einer der folgenden Codezeilen ändern:</span><span class="sxs-lookup"><span data-stu-id="3870c-117">You can correct the error by changing the call to either of the following lines of code:</span></span>

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

<span data-ttu-id="3870c-118">Jede der vorangehenden Codezeilen wandelt die Variable explizit `Object` `o1` in einen der für die über Ladungen definierten Parametertypen um.</span><span class="sxs-lookup"><span data-stu-id="3870c-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>

## <a name="see-also"></a><span data-ttu-id="3870c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3870c-119">See also</span></span>

- [<span data-ttu-id="3870c-120">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="3870c-120">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="3870c-121">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="3870c-121">Overload Resolution</span></span>](../../programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="3870c-122">CType Function</span><span class="sxs-lookup"><span data-stu-id="3870c-122">CType Function</span></span>](../functions/ctype-function.md)
