---
title: Ausdruck ist vom Typ &#39; &lt;Typename&gt; &#39; die eines eingeschränkten Typs ist, und kann nicht verwendet werden, um die von der geerbten Member zugreifen &#39;Objekt&#39; oder &#39;ValueType&#39;
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 2ba2298da77ac31abc0b1b4ad84328be7bc6dbb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587572"
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="abb5c-102">Ausdruck ist vom Typ &#39; &lt;Typename&gt; &#39; die eines eingeschränkten Typs ist, und kann nicht verwendet werden, um die von der geerbten Member zugreifen &#39;Objekt&#39; oder &#39;ValueType&#39;</span><span class="sxs-lookup"><span data-stu-id="abb5c-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="abb5c-103">Ein Ausdruck ergibt ein Typ, der von der common Language Runtime (CLR) geschachtelt werden kann, aber greift auf ein Element, das Boxing erfordert.</span><span class="sxs-lookup"><span data-stu-id="abb5c-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="abb5c-104">*Boxing* bezieht sich auf die Verarbeitung, die zum Konvertieren eines Typs in `Object` oder gelegentlich in <xref:System.ValueType>erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="abb5c-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="abb5c-105">Die common Language Runtime kann nicht bestimmte Typen, z. B. Feld <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, und <xref:System.TypedReference>.</span><span class="sxs-lookup"><span data-stu-id="abb5c-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="abb5c-106">Dieser Ausdruck versucht, den eingeschränkten Typ zu verwenden, zum Aufrufen einer Methode geerbt von <xref:System.Object> oder <xref:System.ValueType>, wie z. B. <xref:System.Object.GetHashCode%2A> oder <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="abb5c-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="abb5c-107">Um diese Methode zugreifen zu können, hat Visual Basic eine implizites Boxing-Konvertierung versucht, die diesen Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="abb5c-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="abb5c-108">**Fehler-ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="abb5c-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="abb5c-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="abb5c-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="abb5c-110">Suchen Sie den Ausdruck, der den angegebenen Typ ergibt.</span><span class="sxs-lookup"><span data-stu-id="abb5c-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="abb5c-111">Suchen Sie den Teil der Anweisung, die zum Aufrufen der Methode geerbt von versucht <xref:System.Object> oder <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="abb5c-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="abb5c-112">Schreiben Sie die Anweisung aus, um den Aufruf der Methode zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="abb5c-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb5c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abb5c-113">See Also</span></span>  
 [<span data-ttu-id="abb5c-114">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="abb5c-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
