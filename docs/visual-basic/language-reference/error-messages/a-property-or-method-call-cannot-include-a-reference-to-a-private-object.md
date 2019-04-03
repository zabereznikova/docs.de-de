---
title: Ein Aufruf für eine Eigenschaft oder Methode darf keinen Verweis auf ein privates Objekt enthalten - weder als Argument, noch als Rückgabewert.
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 0a8d6603bf5c97b966d29f000b21435cec8040d8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840951"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="9c70b-102">Ein Aufruf für eine Eigenschaft oder Methode darf keinen Verweis auf ein privates Objekt enthalten - weder als Argument, noch als Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="9c70b-102">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>
<span data-ttu-id="9c70b-103">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="9c70b-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="9c70b-104">Ein Client hat eine Eigenschaft oder Methode einer Out-of-Process-Komponente aufgerufen und versucht, einen Verweis auf ein privates Objekt als eines der Argumente zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="9c70b-104">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>  
  
-   <span data-ttu-id="9c70b-105">Eine Out-of-Process-Komponente hat eine Callback-Methode für ihren Client aufgerufen und versucht, einen Verweis auf ein privates Objekt zu übergeben</span><span class="sxs-lookup"><span data-stu-id="9c70b-105">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>  
  
-   <span data-ttu-id="9c70b-106">Eine Out-of-Process-Komponente hat versucht, einen Verweis auf ein privates Objekt als Argument eines Ereignisses zu übergeben, das von ihr ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="9c70b-106">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>  
  
-   <span data-ttu-id="9c70b-107">Ein Client hat versucht, einem `ByRef` -Argument eines Ereignisses, das er verarbeitet hat, einen privaten Objektverweis zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9c70b-107">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9c70b-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9c70b-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="9c70b-109">Entfernen Sie den Verweis.</span><span class="sxs-lookup"><span data-stu-id="9c70b-109">Remove the reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c70b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c70b-110">See also</span></span>

- [<span data-ttu-id="9c70b-111">Private</span><span class="sxs-lookup"><span data-stu-id="9c70b-111">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
