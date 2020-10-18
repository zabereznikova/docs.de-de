---
title: Der Ausdruck weist den Typ '<typename>' auf, einen eingeschränkten Typ, der nicht verwendet werden kann, um auf von 'Object' oder 'ValueType' geerbte Member zuzugreifen
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 3e19c0d71ee47ac61e9704f0fcd2637f01aa0896
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163050"
---
# <a name="bc31393-expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="16b62-102">BC31393: der Ausdruck weist den Typ ' \<typename> ' auf, bei dem es sich um einen eingeschränkten Typ handelt, der nicht für den Zugriff auf von ' Object ' oder ' ValueType ' geerbte Member verwendet</span><span class="sxs-lookup"><span data-stu-id="16b62-102">BC31393: Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>

<span data-ttu-id="16b62-103">Ein Ausdruck wird zu einem Typ ausgewertet, der nicht vom Common Language Runtime (CLR) gekapselt werden kann, aber auf einen Member zugreift, der Boxing erfordert.</span><span class="sxs-lookup"><span data-stu-id="16b62-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>

 <span data-ttu-id="16b62-104">*Boxing* bezieht sich auf die Verarbeitung, die zum Konvertieren eines Typs in `Object` oder gelegentlich in <xref:System.ValueType>erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="16b62-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="16b62-105">Der Common Language Runtime kann bestimmte Strukturtypen nicht einfeldern, <xref:System.ArgIterator> z <xref:System.RuntimeArgumentHandle> . b <xref:System.TypedReference> ., und.</span><span class="sxs-lookup"><span data-stu-id="16b62-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>

 <span data-ttu-id="16b62-106">Dieser Ausdruck versucht, den eingeschränkten Typ zu verwenden, um eine Methode aufzurufen, die von <xref:System.Object> oder geerbt <xref:System.ValueType> wird, z <xref:System.Object.GetHashCode%2A> . b <xref:System.Object.ToString%2A> . oder.</span><span class="sxs-lookup"><span data-stu-id="16b62-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="16b62-107">Für den Zugriff auf diese Methode hat Visual Basic versucht, eine implizite Boxing-Konvertierung auszuführen, die diesen Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="16b62-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>

 <span data-ttu-id="16b62-108">**Fehler-ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="16b62-108">**Error ID:** BC31393</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="16b62-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="16b62-109">To correct this error</span></span>

1. <span data-ttu-id="16b62-110">Suchen Sie den Ausdruck, der den angegebenen Typ ergibt.</span><span class="sxs-lookup"><span data-stu-id="16b62-110">Locate the expression that evaluates to the cited type.</span></span>

2. <span data-ttu-id="16b62-111">Suchen Sie den Teil der Anweisung, der versucht, die Methode aufzurufen, die von oder geerbt wurde <xref:System.Object> <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="16b62-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>

3. <span data-ttu-id="16b62-112">Schreiben Sie die Anweisung neu, um den Methodenaufrufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="16b62-112">Rewrite the statement to avoid the method call.</span></span>

## <a name="see-also"></a><span data-ttu-id="16b62-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16b62-113">See also</span></span>

- [<span data-ttu-id="16b62-114">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="16b62-114">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
