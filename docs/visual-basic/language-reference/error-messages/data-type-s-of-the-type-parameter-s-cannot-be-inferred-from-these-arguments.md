---
title: Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 4167905ca6ddab66b2cbc6c8c40dc7c984e94b8b
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913194"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="9e071-102">Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="9e071-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>
<span data-ttu-id="9e071-103">Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9e071-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="9e071-104">Sie können diesen Fehler möglicherweise beheben, indem Sie die Datentypen explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="9e071-104">Specifying the data type(s) explicitly might correct this error.</span></span>  
  
 <span data-ttu-id="9e071-105">Dieser Fehler tritt auf, wenn die Überladungsauflösung fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="9e071-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="9e071-106">Er wird als untergeordnete Meldung angezeigt, die den Grund für die Entfernung einer bestimmten Überladung angibt.</span><span class="sxs-lookup"><span data-stu-id="9e071-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="9e071-107">Die Fehlermeldung wird erläutert, dass der Compiler den Typrückschluss verwenden kann, um die Datentypen der Typparameter zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9e071-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e071-108">Wenn die Angabe von Argumenten keine Option ist (z. B. für Abfrageoperatoren in Abfrageausdrücken), wird nur der erste Satz der Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e071-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>  
  
 <span data-ttu-id="9e071-109">Der folgende Code verdeutlicht den Fehler.</span><span class="sxs-lookup"><span data-stu-id="9e071-109">The following code demonstrates the error.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 <span data-ttu-id="9e071-110">**Fehler-ID:** BC36647 und BC36644</span><span class="sxs-lookup"><span data-stu-id="9e071-110">**Error ID:** BC36647 and BC36644</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9e071-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9e071-111">To correct this error</span></span>  
  
- <span data-ttu-id="9e071-112">Anstelle des Typrückschlusses können Sie einen Datentyp für den oder die Typparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="9e071-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e071-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e071-113">See also</span></span>

- [<span data-ttu-id="9e071-114">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="9e071-114">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="9e071-115">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e071-115">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="9e071-116">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e071-116">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
