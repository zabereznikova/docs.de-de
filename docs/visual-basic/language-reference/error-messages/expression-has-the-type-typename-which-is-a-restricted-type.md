---
title: Der Ausdruck weist den Typ '<typename>' auf, einen eingeschränkten Typ, der nicht verwendet werden kann, um auf von 'Object' oder 'ValueType' geerbte Member zuzugreifen
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 0eb30488312cc7519f39a6b819aea15489f2f70a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409519"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="eb964-102">Der Ausdruck weist den Typ '\<typename>' auf, einen eingeschränkten Typ, der nicht verwendet werden kann, um auf von 'Object' oder 'ValueType' geerbte Member zuzugreifen</span><span class="sxs-lookup"><span data-stu-id="eb964-102">Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>
<span data-ttu-id="eb964-103">Ein Ausdruck wird zu einem Typ ausgewertet, der nicht vom Common Language Runtime (CLR) gekapselt werden kann, aber auf einen Member zugreift, der Boxing erfordert.</span><span class="sxs-lookup"><span data-stu-id="eb964-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="eb964-104">*Boxing* bezieht sich auf die Verarbeitung, die zum Konvertieren eines Typs in `Object` oder gelegentlich in <xref:System.ValueType>erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="eb964-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="eb964-105">Der Common Language Runtime kann bestimmte Strukturtypen nicht einfeldern, <xref:System.ArgIterator> z <xref:System.RuntimeArgumentHandle> . b <xref:System.TypedReference> ., und.</span><span class="sxs-lookup"><span data-stu-id="eb964-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="eb964-106">Dieser Ausdruck versucht, den eingeschränkten Typ zu verwenden, um eine Methode aufzurufen, die von <xref:System.Object> oder geerbt <xref:System.ValueType> wird, z <xref:System.Object.GetHashCode%2A> . b <xref:System.Object.ToString%2A> . oder.</span><span class="sxs-lookup"><span data-stu-id="eb964-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="eb964-107">Für den Zugriff auf diese Methode hat Visual Basic versucht, eine implizite Boxing-Konvertierung auszuführen, die diesen Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="eb964-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="eb964-108">**Fehler-ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="eb964-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eb964-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="eb964-109">To correct this error</span></span>  
  
1. <span data-ttu-id="eb964-110">Suchen Sie den Ausdruck, der den angegebenen Typ ergibt.</span><span class="sxs-lookup"><span data-stu-id="eb964-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2. <span data-ttu-id="eb964-111">Suchen Sie den Teil der Anweisung, der versucht, die Methode aufzurufen, die von oder geerbt wurde <xref:System.Object> <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="eb964-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3. <span data-ttu-id="eb964-112">Schreiben Sie die Anweisung neu, um den Methodenaufrufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="eb964-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb964-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb964-113">See also</span></span>

- [<span data-ttu-id="eb964-114">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="eb964-114">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
