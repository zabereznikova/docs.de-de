---
title: Spät gebundene überladungsauflösung. kann nicht angewendet werden, um &#39; &lt;Prozedurname&gt; &#39; , da die Instanz beim Zugriff auf ein Schnittstellentyp ist.
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: e41cbf30f06547ef39553e31542e4e8b6df49a3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589879"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="24050-102">Spät gebundene überladungsauflösung. kann nicht angewendet werden, um &#39; &lt;Prozedurname&gt; &#39; , da die Instanz beim Zugriff auf ein Schnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="24050-102">Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type</span></span>
<span data-ttu-id="24050-103">Der Compiler versucht, einen Verweis auf eine überladene Eigenschaft oder Prozedur aufzulösen, aber der Verweis schlägt fehl, da ein Argument des Typs ist `Object` und das verweisende Objekt weist den Datentyp einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="24050-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="24050-104">Die `Object` Argument zwingt den Compiler zum Auflösen des Verweises als spät gebunden.</span><span class="sxs-lookup"><span data-stu-id="24050-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="24050-105">Unter diesen Umständen löst der Compiler die Überladung über die implementierende Klasse anstelle von über die zugrunde liegenden Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="24050-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="24050-106">Wenn die Klasse mit einer der überladenen Versionen umbenennt, berücksichtigt der Compiler nicht diese Version mit einer Überladung, da Sie einen anderen Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="24050-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="24050-107">Dies Compiler wiederum der die umbenannte Version ignoriert, wenn sie die richtige Auswahl den Verweis aufgelöst gegangen sein könnte.</span><span class="sxs-lookup"><span data-stu-id="24050-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="24050-108">**Fehler-ID:** BC30933</span><span class="sxs-lookup"><span data-stu-id="24050-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="24050-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="24050-109">To correct this error</span></span>  
  
-   <span data-ttu-id="24050-110">Verwendung `CType` das Argument aus umwandeln `Object` in den angegebenen, durch die Signatur der Überladung, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="24050-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="24050-111">Beachten Sie, dass er nicht behoben wird, das verweisende Objekt, das die zugrunde liegende Schnittstelle umwandeln.</span><span class="sxs-lookup"><span data-stu-id="24050-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="24050-112">Das Argument, um diesen Fehler vermeiden, müssen Sie eine Umwandlung.</span><span class="sxs-lookup"><span data-stu-id="24050-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24050-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24050-113">Example</span></span>  
 <span data-ttu-id="24050-114">Das folgende Beispiel zeigt einen Aufruf einer überladenen `Sub` Prozedur, die diesen Fehler zur Kompilierzeit verursacht.</span><span class="sxs-lookup"><span data-stu-id="24050-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
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
  
 <span data-ttu-id="24050-115">Im vorherigen Beispiel, wenn der Compiler den Aufruf zugelassen `s1` geschrieben, die Auflösung erfolgt über die Klasse `c1` anstelle der Schnittstelle `i1`.</span><span class="sxs-lookup"><span data-stu-id="24050-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="24050-116">Dies bedeutet, dass der Compiler nicht berücksichtigt, `s2` weil dieser Name in verschiedenen ist `c1`, auch wenn es sich um die richtige Wahl ist gemäß der Definition von `i1`.</span><span class="sxs-lookup"><span data-stu-id="24050-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="24050-117">Sie können den Fehler behoben, durch den Aufruf an einen der folgenden Codezeilen ändern:</span><span class="sxs-lookup"><span data-stu-id="24050-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="24050-118">Jede der vorangehenden Zeilen des Codes explizit wandelt die `Object` Variable `o1` auf einen der Parametertypen für die Überladungen definiert.</span><span class="sxs-lookup"><span data-stu-id="24050-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24050-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24050-119">See Also</span></span>  
 [<span data-ttu-id="24050-120">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="24050-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [<span data-ttu-id="24050-121">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="24050-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [<span data-ttu-id="24050-122">CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="24050-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
