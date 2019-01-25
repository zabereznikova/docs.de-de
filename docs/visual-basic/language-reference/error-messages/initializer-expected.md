---
title: Initialisierer erwartet
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 1fa66a3c50b5c1eadd4c63b92c57ab60e1a11076
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595993"
---
# <a name="initializer-expected"></a><span data-ttu-id="5df8b-102">Initialisierer erwartet</span><span class="sxs-lookup"><span data-stu-id="5df8b-102">Initializer expected</span></span>
<span data-ttu-id="5df8b-103">Sie haben versucht, eine Instanz einer Klasse deklarieren, indem Sie mit einem Objektinitialisierer, in dem eine die Initialisierungsliste leer ist, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5df8b-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="5df8b-104">Mindestens ein Feld oder eine Eigenschaft muss in der Initialisiererliste initialisiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5df8b-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="5df8b-105">**Fehler-ID:** BC30996</span><span class="sxs-lookup"><span data-stu-id="5df8b-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5df8b-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5df8b-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="5df8b-107">Initialisieren Sie mindestens ein Feld oder eine Eigenschaft im Initialisierer zu, oder verwenden Sie einen Objektinitialisierer nicht.</span><span class="sxs-lookup"><span data-stu-id="5df8b-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df8b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5df8b-108">See also</span></span>
- [<span data-ttu-id="5df8b-109">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="5df8b-109">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="5df8b-110">Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers</span><span class="sxs-lookup"><span data-stu-id="5df8b-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
