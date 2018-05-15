---
title: Das Argument kann nicht 'Nothing' sein.
ms.date: 07/20/2015
f1_keywords:
- vbrGeneral_ArgumentNullException
ms.assetid: 2abd995b-36a5-45f0-b3c1-6e0c3b31a875
ms.openlocfilehash: 7b08dd41f638138df4c2f92fbe9f05f1312c2d03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="argument-cannot-be-nothing"></a><span data-ttu-id="72417-102">Das Argument kann nicht 'Nothing' sein.</span><span class="sxs-lookup"><span data-stu-id="72417-102">Argument cannot be Nothing</span></span>
<span data-ttu-id="72417-103">Ein NULL-Wert wurde für ein Argument angegeben, das einen Wert aufweisen muss.</span><span class="sxs-lookup"><span data-stu-id="72417-103">A null value has been supplied for an argument that must have a value.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72417-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="72417-104">To correct this error</span></span>  
  
-   <span data-ttu-id="72417-105">Sie haben möglicherweise versucht, ein Objekt zu verwenden, ohne eine Instanz des Objekts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="72417-105">You might have tried to use an object without providing an instance of the object.</span></span> <span data-ttu-id="72417-106">Verwenden Sie in solchen Fällen das `New` -Schlüsselwort, um die Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72417-106">In such a case, use the `New` keyword to create the instance.</span></span>  
  
-   <span data-ttu-id="72417-107">Überprüfen Sie, ob der Wert ordnungsgemäß berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="72417-107">Check that the value is calculated correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72417-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72417-108">See Also</span></span>  
 <xref:System.NullReferenceException>
