---
title: Die Friend-Funktion eines Objekts, das keine Instanz der definierenden Klasse ist, kann nicht aufgerufen werden.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f1ac1ea14efb0cdf0d8ca03257e4da33d35e368
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="4a937-102">Die Friend-Funktion eines Objekts, das keine Instanz der definierenden Klasse ist, kann nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4a937-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="4a937-103">Entweder haben Sie versucht, die `Friend` -Prozedur einer Klasse aufzurufen, oder prozess- bzw. threadübergreifend auf eine `Friend` -Eigenschaft oder -Methode zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4a937-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="4a937-104">Eine `Friend` -Prozedur kann über ein Modul außerhalb der Klasse aufgerufen werden, ist jedoch Teil des Projekts, in dem die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4a937-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4a937-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4a937-105">To correct this error</span></span>  
  
-   <span data-ttu-id="4a937-106">Stellen Sie sicher, dass Sie die Prozedur über ein Modul aufrufen bzw. auf sie zugreifen, das Teil des Projekts ist, in dem die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4a937-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a937-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a937-107">See Also</span></span>  
 [<span data-ttu-id="4a937-108">Friend</span><span class="sxs-lookup"><span data-stu-id="4a937-108">Friend</span></span>](../../visual-basic/language-reference/modifiers/friend.md)
