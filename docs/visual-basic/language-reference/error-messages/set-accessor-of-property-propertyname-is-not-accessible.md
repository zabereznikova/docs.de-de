---
title: '&#39;Legen Sie&#39; -Accessor der Eigenschaft &#39; &lt;Propertyname&gt; &#39; kann nicht zugegriffen werden'
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: a543506b06742f3ee9101edbac962e761ddd531d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606568"
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="91d8e-102">&#39;Legen Sie&#39; -Accessor der Eigenschaft &#39; &lt;Propertyname&gt; &#39; kann nicht zugegriffen werden</span><span class="sxs-lookup"><span data-stu-id="91d8e-102">&#39;Set&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="91d8e-103">Eine Anweisung versucht, den Wert einer Eigenschaft zu speichern, wenn sie den Zugriff auf die Eigenschaft keinen `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="91d8e-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="91d8e-104">Wenn die [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md) mit einem restriktiveren Zugriffsebene als markiert ist seine [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), beim Festlegen der Wert der Eigenschaft kann in den folgenden Fällen fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="91d8e-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="91d8e-105">Die `Set` Anweisung RuntimeCompatibility [Private](../../../visual-basic/language-reference/modifiers/private.md) und der aufrufende Code ist außerhalb der Klasse oder Struktur, in dem die Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="91d8e-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="91d8e-106">Die `Set` Anweisung RuntimeCompatibility [geschützte](../../../visual-basic/language-reference/modifiers/protected.md) und der aufrufende Code ist nicht in der Klasse oder Struktur, die in der die Eigenschaft definiert ist, noch in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="91d8e-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="91d8e-107">Die `Set` Anweisung RuntimeCompatibility [Friend](../../../visual-basic/language-reference/modifiers/friend.md) und der aufrufende Code ist nicht in der gleichen Assembly, in dem die Eigenschaft definiert wird.</span><span class="sxs-lookup"><span data-stu-id="91d8e-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="91d8e-108">**Fehler-ID:** BC31102</span><span class="sxs-lookup"><span data-stu-id="91d8e-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="91d8e-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="91d8e-109">To correct this error</span></span>  
  
-   <span data-ttu-id="91d8e-110">Wenn Sie die Kontrolle über den Quellcode, der die Eigenschaft haben, sollten Sie deklarieren die `Set` Prozedur mit die gleiche Zugriffsebene wie die Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="91d8e-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="91d8e-111">Wenn Sie keine Kontrolle über den Quellcode, der die Eigenschaft definieren, oder Sie einschränken, müssen die `Set` Prozedur Zugriffsebene mehr als die Eigenschaft selbst, versuchen Sie es, um die Anweisung zu verschieben, die den Wert der Eigenschaft um einen Codebereich festlegt, die besseren Zugriff auf die Diese Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="91d8e-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d8e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91d8e-112">See also</span></span>
- [<span data-ttu-id="91d8e-113">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="91d8e-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="91d8e-114">Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="91d8e-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
