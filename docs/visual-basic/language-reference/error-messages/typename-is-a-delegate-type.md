---
title: '&#39; &lt;Typename&gt;&#39; ein Delegattyp'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9428f0ac321b90e36d4d987381ed69b6c968894c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="08a3c-102">&#39; &lt;Typename&gt;&#39; ein Delegattyp</span><span class="sxs-lookup"><span data-stu-id="08a3c-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="08a3c-103">"\<Typname >' ein Delegattyp ist.</span><span class="sxs-lookup"><span data-stu-id="08a3c-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="08a3c-104">Erstellen eines Delegaten kann nur einen einzelnen AddressOf-Ausdruck als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="08a3c-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="08a3c-105">AddressOf-Ausdruck kann häufig statt eine Delegatkonstruktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08a3c-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="08a3c-106">Ein `New` -Klausel erstellt eine Instanz einer Delegatklasse liefert eine ungültige Argumentliste an den Delegatkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="08a3c-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="08a3c-107">Sie können angeben, dass nur ein einzelner `AddressOf` Ausdruck beim Erstellen einer neuen Delegatinstanz.</span><span class="sxs-lookup"><span data-stu-id="08a3c-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="08a3c-108">Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben wenn Sie mehr als ein Argument übergeben, oder wenn Sie ein einzelnes Argument übergeben, die keine gültige `AddressOf` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="08a3c-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="08a3c-109">**Fehler-ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="08a3c-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="08a3c-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="08a3c-110">To correct this error</span></span>  
  
-   <span data-ttu-id="08a3c-111">Ein einzelnes `AddressOf` Ausdruck in der Argumentliste für die Delegate-Klasse in der `New` Klausel.</span><span class="sxs-lookup"><span data-stu-id="08a3c-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a3c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08a3c-112">See Also</span></span>  
 [<span data-ttu-id="08a3c-113">New-Operator</span><span class="sxs-lookup"><span data-stu-id="08a3c-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="08a3c-114">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="08a3c-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="08a3c-115">Delegaten</span><span class="sxs-lookup"><span data-stu-id="08a3c-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="08a3c-116">Gewusst wie: Aufrufen einer Delegatenmethode</span><span class="sxs-lookup"><span data-stu-id="08a3c-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
