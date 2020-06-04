---
title: Ein Aufruf für eine Eigenschaft oder Methode darf keinen Verweis auf ein privates Objekt enthalten - weder als Argument, noch als Rückgabewert.
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 36c71cdb345d0fdc0da2b58865a1f11956bcb944
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409971"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="0aa7a-102">Ein Aufruf für eine Eigenschaft oder Methode darf keinen Verweis auf ein privates Objekt enthalten - weder als Argument, noch als Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-102">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>

<span data-ttu-id="0aa7a-103">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="0aa7a-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="0aa7a-104">Ein Client hat eine Eigenschaft oder Methode einer Out-of-Process-Komponente aufgerufen und versucht, einen Verweis auf ein privates Objekt als eines der Argumente zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-104">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>  
  
- <span data-ttu-id="0aa7a-105">Eine Out-of-Process-Komponente hat eine Callback-Methode für ihren Client aufgerufen und versucht, einen Verweis auf ein privates Objekt zu übergeben</span><span class="sxs-lookup"><span data-stu-id="0aa7a-105">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>  
  
- <span data-ttu-id="0aa7a-106">Eine Out-of-Process-Komponente hat versucht, einen Verweis auf ein privates Objekt als Argument eines Ereignisses zu übergeben, das von ihr ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-106">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>  
  
- <span data-ttu-id="0aa7a-107">Ein Client hat versucht, einem `ByRef` -Argument eines Ereignisses, das er verarbeitet hat, einen privaten Objektverweis zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-107">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0aa7a-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0aa7a-108">To correct this error</span></span>  
  
1. <span data-ttu-id="0aa7a-109">Entfernen Sie den Verweis.</span><span class="sxs-lookup"><span data-stu-id="0aa7a-109">Remove the reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa7a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0aa7a-110">See also</span></span>

- [<span data-ttu-id="0aa7a-111">Privat</span><span class="sxs-lookup"><span data-stu-id="0aa7a-111">Private</span></span>](../modifiers/private.md)
