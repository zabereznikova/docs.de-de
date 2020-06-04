---
title: Die Friend-Funktion eines Objekts, das keine Instanz der definierenden Klasse ist, kann nicht aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: c18c04470c4c49113e8195b92185326c5c4197c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400847"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="7ff28-102">Die Friend-Funktion eines Objekts, das keine Instanz der definierenden Klasse ist, kann nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7ff28-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="7ff28-103">Entweder haben Sie versucht, die `Friend` -Prozedur einer Klasse aufzurufen, oder prozess- bzw. threadübergreifend auf eine `Friend` -Eigenschaft oder -Methode zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7ff28-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="7ff28-104">Eine `Friend` -Prozedur kann über ein Modul außerhalb der Klasse aufgerufen werden, ist jedoch Teil des Projekts, in dem die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7ff28-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7ff28-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7ff28-105">To correct this error</span></span>  
  
- <span data-ttu-id="7ff28-106">Stellen Sie sicher, dass Sie die Prozedur über ein Modul aufrufen bzw. auf sie zugreifen, das Teil des Projekts ist, in dem die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7ff28-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff28-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ff28-107">See also</span></span>

- [<span data-ttu-id="7ff28-108">Kollegen</span><span class="sxs-lookup"><span data-stu-id="7ff28-108">Friend</span></span>](../language-reference/modifiers/friend.md)
