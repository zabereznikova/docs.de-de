---
title: Die Friend-Funktion eines Objekts, das keine Instanz der definierenden Klasse ist, kann nicht aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: c65bbb5028cf042b702bb2b8336d40512c980790
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912690"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="fcd71-102">Die Friend-Funktion eines Objekts, das keine Instanz der definierenden Klasse ist, kann nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fcd71-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="fcd71-103">Entweder haben Sie versucht, die `Friend` -Prozedur einer Klasse aufzurufen, oder prozess- bzw. threadübergreifend auf eine `Friend` -Eigenschaft oder -Methode zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="fcd71-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="fcd71-104">Eine `Friend` -Prozedur kann über ein Modul außerhalb der Klasse aufgerufen werden, ist jedoch Teil des Projekts, in dem die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fcd71-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fcd71-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fcd71-105">To correct this error</span></span>  
  
- <span data-ttu-id="fcd71-106">Stellen Sie sicher, dass Sie die Prozedur über ein Modul aufrufen bzw. auf sie zugreifen, das Teil des Projekts ist, in dem die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fcd71-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd71-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcd71-107">See also</span></span>

- [<span data-ttu-id="fcd71-108">Friend</span><span class="sxs-lookup"><span data-stu-id="fcd71-108">Friend</span></span>](../../visual-basic/language-reference/modifiers/friend.md)
