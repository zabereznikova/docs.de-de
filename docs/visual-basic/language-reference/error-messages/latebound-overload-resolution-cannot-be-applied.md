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
ms.openlocfilehash: 7f2ae3bb0e7c09d966c53fb17b1cbe675dfce8b9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814054"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="a0fd7-102">Spät gebundene überladungsauflösung kann nicht angewendet werden, um "\<Prozedurname >', da die Zugreifende Instanz ein Schnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-102">Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>
<span data-ttu-id="a0fd7-103">Der Compiler versucht, einen Verweis auf eine überladene Eigenschaft oder Prozedur aufzulösen, aber der Verweis schlägt fehl, weil ein Argument des Typs `Object` und das verweisende Objekt weist den Datentyp einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="a0fd7-104">Die `Object` Argument erzwingt, dass der Compiler zum Auflösen des Verweises als spät gebunden.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="a0fd7-105">Unter diesen Umständen löst der Compiler die Überladung durch die implementierende Klasse statt über die zugrunde liegenden Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="a0fd7-106">Wenn die Klasse eine der überladenen Versionen umbenennt, berücksichtigt der Compiler nicht diese Version mit einer Überladung, da Sie einen anderen Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="a0fd7-107">Dies bewirkt wiederum, dass den Compiler die umbenannte Version ignoriert, wenn sie die richtige Wahl zum Auflösen des Verweises gegangen sein könnte.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="a0fd7-108">**Fehler-ID:** BC30933</span><span class="sxs-lookup"><span data-stu-id="a0fd7-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a0fd7-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a0fd7-109">To correct this error</span></span>  
  
-   <span data-ttu-id="a0fd7-110">Verwendung `CType` umzuwandelnde das Argument vom `Object` in den Typ angegeben wird, durch die Signatur der Überladung aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="a0fd7-111">Beachten Sie, dass es nicht hilfreich sein wird, das verweisende Objekt in der zugrunde liegenden Schnittstelle umwandeln.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="a0fd7-112">Sie müssen das Argument, um diesen Fehler zu vermeiden, umwandeln.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0fd7-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0fd7-113">Example</span></span>  
 <span data-ttu-id="a0fd7-114">Das folgende Beispiel zeigt einen Aufruf einer überladenen `Sub` Prozedur, die zum Zeitpunkt der Kompilierung diesen Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
```  
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
  
 <span data-ttu-id="a0fd7-115">Im vorherigen Beispiel, wenn der Compiler den Aufruf zugelassen `s1` laut würde die Auflösung ausgeführt, über die Klasse `c1` statt die Schnittstelle `i1`.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="a0fd7-116">Dies bedeutet, dass der Compiler nicht berücksichtigt, `s2` da seinen Namen unterscheidet `c1`, auch wenn es sich um die richtige Wahl ist gemäß `i1`.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="a0fd7-117">Sie können den Fehler korrigieren, ändern Sie den Aufruf an eines der folgenden Codezeilen:</span><span class="sxs-lookup"><span data-stu-id="a0fd7-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="a0fd7-118">Jede der vorausgehenden Zeilen Code explizit wandelt die `Object` Variable `o1` auf einen der Parametertypen für die Überladungen definiert.</span><span class="sxs-lookup"><span data-stu-id="a0fd7-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0fd7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0fd7-119">See also</span></span>

- [<span data-ttu-id="a0fd7-120">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="a0fd7-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="a0fd7-121">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="a0fd7-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="a0fd7-122">CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="a0fd7-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
