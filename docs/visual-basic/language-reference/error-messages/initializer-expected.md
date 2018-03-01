---
title: Initialisierer erwartet
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46ff91ec240212571f7ec9f26e82d9d128263545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="initializer-expected"></a><span data-ttu-id="eb12a-102">Initialisierer erwartet</span><span class="sxs-lookup"><span data-stu-id="eb12a-102">Initializer expected</span></span>
<span data-ttu-id="eb12a-103">Sie haben versucht, eine Instanz einer Klasse mithilfe eines Objektinitialisierers, in dem eine die Initialisierungsliste leer ist, wie im folgenden Beispiel gezeigt, deklarieren.</span><span class="sxs-lookup"><span data-stu-id="eb12a-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="eb12a-104">Mindestens ein Feld oder eine Eigenschaft muss in der Initialisiererliste initialisiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb12a-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="eb12a-105">**Fehler-ID:** BC30996</span><span class="sxs-lookup"><span data-stu-id="eb12a-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eb12a-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="eb12a-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="eb12a-107">Mindestens ein Feld oder eine Eigenschaft im Initialisierer zu initialisieren, oder einen Objektinitialisierer nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb12a-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb12a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb12a-108">See Also</span></span>  
 [<span data-ttu-id="eb12a-109">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="eb12a-109">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="eb12a-110">Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers</span><span class="sxs-lookup"><span data-stu-id="eb12a-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
