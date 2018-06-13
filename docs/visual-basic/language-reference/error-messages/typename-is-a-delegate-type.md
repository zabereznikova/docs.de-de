---
title: '&#39;&lt;TypeName&gt; &#39; ein Delegattyp'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c6d4244ce72dedee50b65ba19978149ce86b9e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595647"
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="82266-102">&#39;&lt;TypeName&gt; &#39; ein Delegattyp</span><span class="sxs-lookup"><span data-stu-id="82266-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="82266-103">"\<Typname >' ein Delegattyp ist.</span><span class="sxs-lookup"><span data-stu-id="82266-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="82266-104">Erstellen eines Delegaten kann nur einen einzelnen AddressOf-Ausdruck als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="82266-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="82266-105">AddressOf-Ausdruck kann häufig statt eine Delegatkonstruktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82266-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="82266-106">Ein `New` -Klausel erstellt eine Instanz einer Delegatklasse liefert eine ungültige Argumentliste an den Delegatkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="82266-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="82266-107">Sie können angeben, dass nur ein einzelner `AddressOf` Ausdruck beim Erstellen einer neuen Delegatinstanz.</span><span class="sxs-lookup"><span data-stu-id="82266-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="82266-108">Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben wenn Sie mehr als ein Argument übergeben, oder wenn Sie ein einzelnes Argument übergeben, die keine gültige `AddressOf` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="82266-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="82266-109">**Fehler-ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="82266-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="82266-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="82266-110">To correct this error</span></span>  
  
-   <span data-ttu-id="82266-111">Ein einzelnes `AddressOf` Ausdruck in der Argumentliste für die Delegate-Klasse in der `New` Klausel.</span><span class="sxs-lookup"><span data-stu-id="82266-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82266-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82266-112">See Also</span></span>  
 [<span data-ttu-id="82266-113">New-Operator</span><span class="sxs-lookup"><span data-stu-id="82266-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="82266-114">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="82266-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="82266-115">Delegaten</span><span class="sxs-lookup"><span data-stu-id="82266-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="82266-116">Gewusst wie: Aufrufen einer Delegatenmethode</span><span class="sxs-lookup"><span data-stu-id="82266-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
