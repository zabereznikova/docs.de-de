---
title: '&#39;Abrufen&#39; Accessor der Eigenschaft &#39; &lt;Propertyname&gt; &#39; kann nicht zugegriffen werden'
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 0972c0909f8b07aa1c6700ec32d1a1ca55d00cc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590204"
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="b31b6-102">&#39;Abrufen&#39; Accessor der Eigenschaft &#39; &lt;Propertyname&gt; &#39; kann nicht zugegriffen werden</span><span class="sxs-lookup"><span data-stu-id="b31b6-102">&#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="b31b6-103">Eine Anweisung versucht, den Wert einer Eigenschaft abzurufen, wenn er keinen Zugriff auf der Eigenschaft hat `Get` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b31b6-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>  
  
 <span data-ttu-id="b31b6-104">Wenn die [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md) RuntimeCompatibility mit einer restriktiveren Zugriffsebene als seine [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md), beim Lesen des Eigenschaftswerts kann fehlschlagen, in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="b31b6-104">If the [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="b31b6-105">Die `Get` Anweisung RuntimeCompatibility [Private](../../../visual-basic/language-reference/modifiers/private.md) und der aufrufende Code außerhalb der Klasse oder Struktur, die in der die Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b31b6-105">The `Get` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="b31b6-106">Die `Get` Anweisung RuntimeCompatibility [geschützte](../../../visual-basic/language-reference/modifiers/protected.md) und der aufrufende Code befindet sich nicht in der Klasse oder Struktur, die in der die Eigenschaft definiert ist, noch in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="b31b6-106">The `Get` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="b31b6-107">Die `Get` Anweisung RuntimeCompatibility ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md) und der aufrufende Code ist nicht in der gleichen Assembly, in dem die Eigenschaft definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b31b6-107">The `Get` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="b31b6-108">**Fehler-ID:** BC31103</span><span class="sxs-lookup"><span data-stu-id="b31b6-108">**Error ID:** BC31103</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b31b6-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b31b6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="b31b6-110">Wenn Sie die Kontrolle des Quellcodes die-Eigenschaft definiert haben, sollten Sie deklarieren die `Get` Prozedur mit die gleiche Zugriffsebene wie die Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="b31b6-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="b31b6-111">Wenn Sie keine Kontrolle über den Quellcode der-Eigenschaft definiert wird, oder Sie einschränken, müssen die `Get` Prozedur Zugriffsebene mehr als die Eigenschaft selbst, versuchen Sie es so verschieben Sie die Anweisung, die Wert der Eigenschaft auf einen Codebereich liest, die besseren Zugriff auf die Diese Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b31b6-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b31b6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b31b6-112">See Also</span></span>  
 [<span data-ttu-id="b31b6-113">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="b31b6-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="b31b6-114">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="b31b6-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
