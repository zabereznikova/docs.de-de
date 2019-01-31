---
title: Der Ausdruck weist den Typ '<typename>' auf, einen eingeschränkten Typ, der nicht verwendet werden kann, um auf von 'Object' oder 'ValueType' geerbte Member zuzugreifen
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 6d366ec750ea5a4505ae5ea618e27f47406ba959
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274018"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="fdd1d-102">Ausdruck weist den Typ "\<Typname >', einen eingeschränkten Typ, kann nicht verwendet werden, um von 'Object' oder 'ValueType' geerbte Member zuzugreifen</span><span class="sxs-lookup"><span data-stu-id="fdd1d-102">Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>
<span data-ttu-id="fdd1d-103">Ein Ausdruck ergibt einen Typ, der von der common Language Runtime (CLR) geschachtelt werden kann, aber greift auf ein Element, das Boxing erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fdd1d-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="fdd1d-104">*Boxing* bezieht sich auf die Verarbeitung, die zum Konvertieren eines Typs in `Object` oder gelegentlich in <xref:System.ValueType>erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fdd1d-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="fdd1d-105">Die common Language Runtime kann nicht bestimmte Typen, z. B. Feld <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, und <xref:System.TypedReference>.</span><span class="sxs-lookup"><span data-stu-id="fdd1d-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="fdd1d-106">Dieser Ausdruck versucht, mithilfe der eingeschränkten Typs zum Aufrufen einer Methode geerbt von <xref:System.Object> oder <xref:System.ValueType>, z. B. <xref:System.Object.GetHashCode%2A> oder <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="fdd1d-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="fdd1d-107">Um diese Methode zugreifen zu können, hat Visual Basic eine implizites Boxing-Konvertierung versucht, die diesen Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="fdd1d-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="fdd1d-108">**Fehler-ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="fdd1d-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fdd1d-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fdd1d-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="fdd1d-110">Suchen Sie den Ausdruck, der den angegebenen Typ ergibt.</span><span class="sxs-lookup"><span data-stu-id="fdd1d-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="fdd1d-111">Suchen Sie den Teil der Anweisung, die versucht, die zum Aufrufen der Methode geerbt von <xref:System.Object> oder <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="fdd1d-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="fdd1d-112">Schreiben Sie Anweisung um den Methodenaufruf zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="fdd1d-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd1d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdd1d-113">See also</span></span>
- [<span data-ttu-id="fdd1d-114">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="fdd1d-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
