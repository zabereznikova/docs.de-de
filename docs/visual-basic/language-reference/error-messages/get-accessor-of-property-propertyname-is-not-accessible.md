---
title: Auf den Get-Accessor der <propertyname>-Eigenschaft kann nicht zugegriffen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 92cc6d732b59617a6043bd71a9549649ff1ad356
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662045"
---
# <a name="get-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="6792d-102">"Get-Accessor der Eigenschaft"\<Propertyname >' kann nicht zugegriffen werden</span><span class="sxs-lookup"><span data-stu-id="6792d-102">'Get' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="6792d-103">Eine Anweisung versucht, den Wert einer Eigenschaft abzurufen, wenn sie den Zugriff auf die Eigenschaft keinen `Get` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="6792d-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>  
  
 <span data-ttu-id="6792d-104">Wenn die [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) mit einem restriktiveren Zugriffsebene als markiert ist seine [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), beim Lesen des Eigenschaftswerts kann fehlschlagen, in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="6792d-104">If the [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>  
  
- <span data-ttu-id="6792d-105">Die `Get` Anweisung RuntimeCompatibility [Private](../../../visual-basic/language-reference/modifiers/private.md) und der aufrufende Code ist außerhalb der Klasse oder Struktur, in dem die Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6792d-105">The `Get` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
- <span data-ttu-id="6792d-106">Die `Get` Anweisung RuntimeCompatibility [geschützte](../../../visual-basic/language-reference/modifiers/protected.md) und der aufrufende Code ist nicht in der Klasse oder Struktur, die in der die Eigenschaft definiert ist, noch in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="6792d-106">The `Get` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
- <span data-ttu-id="6792d-107">Die `Get` Anweisung RuntimeCompatibility [Friend](../../../visual-basic/language-reference/modifiers/friend.md) und der aufrufende Code ist nicht in der gleichen Assembly, in dem die Eigenschaft definiert wird.</span><span class="sxs-lookup"><span data-stu-id="6792d-107">The `Get` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="6792d-108">**Fehler-ID:** BC31103</span><span class="sxs-lookup"><span data-stu-id="6792d-108">**Error ID:** BC31103</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6792d-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6792d-109">To correct this error</span></span>  
  
- <span data-ttu-id="6792d-110">Wenn Sie die Kontrolle über den Quellcode, der die Eigenschaft haben, sollten Sie deklarieren die `Get` Prozedur mit die gleiche Zugriffsebene wie die Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="6792d-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>  
  
- <span data-ttu-id="6792d-111">Wenn Sie keine Kontrolle über den Quellcode, der die Eigenschaft definieren, oder Sie einschränken, müssen die `Get` Prozedur Zugriffsebene mehr als die Eigenschaft selbst, versuchen Sie es, um die Anweisung zu verschieben, die Wert der Eigenschaft, um einen Codebereich liest, die besseren Zugriff auf die Diese Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6792d-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6792d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6792d-112">See also</span></span>

- [<span data-ttu-id="6792d-113">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="6792d-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="6792d-114">Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="6792d-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
