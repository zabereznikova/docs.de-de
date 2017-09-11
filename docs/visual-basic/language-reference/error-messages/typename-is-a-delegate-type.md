---
title: '&quot;&lt;Typename&gt;&quot;ist ein Delegattyp | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
dev_langs:
- VB
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 55532e269a7d6756157d324a2db14320df5d3f55
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="96e29-102">'&lt;Typename&gt;"ist ein Delegattyp</span><span class="sxs-lookup"><span data-stu-id="96e29-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="96e29-103">'\<Typename > "ist ein Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="96e29-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="96e29-104">Erstellen eines Delegaten kann nur einen einzelnen AddressOf-Ausdruck als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="96e29-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="96e29-105">Ein AddressOf-Ausdruck kann oft statt einen Delegaten zu erstellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96e29-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="96e29-106">Ein `New` -Klausel erstellt eine Instanz einer Delegatklasse gibt eine ungültige Argumentliste an den Delegatkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="96e29-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="96e29-107">Sie können angeben, dass nur eine einzige `AddressOf` Ausdruck beim Erstellen einer neuen Delegatinstanz.</span><span class="sxs-lookup"><span data-stu-id="96e29-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="96e29-108">Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben wenn Sie mehr als ein Argument übergeben, oder wenn Sie ein einzelnes Argument übergeben, die keine gültige `AddressOf` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="96e29-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="96e29-109">**Fehler-ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="96e29-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96e29-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="96e29-110">To correct this error</span></span>  
  
-   <span data-ttu-id="96e29-111">Verwenden Sie einen einzelnen `AddressOf` Ausdruck in der Argumentliste für die Delegatklasse der `New` Klausel.</span><span class="sxs-lookup"><span data-stu-id="96e29-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e29-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96e29-112">See Also</span></span>  
 <span data-ttu-id="96e29-113">[New-Operator](../../../visual-basic/language-reference/operators/new-operator.md) </span><span class="sxs-lookup"><span data-stu-id="96e29-113">[New Operator](../../../visual-basic/language-reference/operators/new-operator.md) </span></span>  
<span data-ttu-id="96e29-114"> [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="96e29-114"> [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="96e29-115"> [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="96e29-115"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="96e29-116"> [Gewusst wie: Aufrufen einer Delegatenmethode](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span><span class="sxs-lookup"><span data-stu-id="96e29-116"> [How to: Invoke a Delegate Method](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span></span>
