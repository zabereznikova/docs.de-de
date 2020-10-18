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
ms.openlocfilehash: 85798e6453bc6cea6174ecc536b35835865e0459
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163453"
---
# <a name="bc36647-and-bc36644-data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="5a996-102">BC36647 und BC36644: die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5a996-102">BC36647 and BC36644: Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>

<span data-ttu-id="5a996-103">Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5a996-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="5a996-104">Sie können diesen Fehler möglicherweise beheben, indem Sie die Datentypen explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="5a996-104">Specifying the data type(s) explicitly might correct this error.</span></span>

<span data-ttu-id="5a996-105">Dieser Fehler tritt auf, wenn bei der Überladungsauflösung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="5a996-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="5a996-106">Er wird als untergeordnete Meldung angezeigt, die den Grund für die Entfernung einer bestimmten Überladung angibt.</span><span class="sxs-lookup"><span data-stu-id="5a996-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="5a996-107">In der Fehlermeldung wird erläutert, dass der Compiler den Typrückschluss nicht zum Suchen von Datentypen für die Typparameter verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="5a996-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="5a996-108">Wenn die Angabe von Argumenten keine Option ist (z. B. für Abfrageoperatoren in Abfrageausdrücken), wird nur der erste Satz der Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a996-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>

<span data-ttu-id="5a996-109">Im folgenden Code wird der Fehler veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5a996-109">The following code demonstrates the error.</span></span>

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

<span data-ttu-id="5a996-110">**Fehler-ID:** BC36647 und BC36644</span><span class="sxs-lookup"><span data-stu-id="5a996-110">**Error ID:** BC36647 and BC36644</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5a996-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5a996-111">To correct this error</span></span>

<span data-ttu-id="5a996-112">Anstelle des Typrückschlusses können Sie einen Datentyp für den oder die Typparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="5a996-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a996-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a996-113">See also</span></span>

- [<span data-ttu-id="5a996-114">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="5a996-114">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="5a996-115">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a996-115">Generic Procedures in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="5a996-116">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a996-116">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
