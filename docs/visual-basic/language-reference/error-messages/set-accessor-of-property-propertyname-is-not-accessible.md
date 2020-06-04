---
title: Auf den Set-Accessor der <propertyname>-Eigenschaft kann nicht zugegriffen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 077533a5b1fe241b61ded9516ad8f450d7dbbf5e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400343"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="e5b49-102">Auf den Set-Accessor der \<propertyname>-Eigenschaft kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e5b49-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="e5b49-103">Eine-Anweisung versucht, den Wert einer Eigenschaft zu speichern, wenn Sie keinen Zugriff auf die Prozedur der Eigenschaft hat `Set` .</span><span class="sxs-lookup"><span data-stu-id="e5b49-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="e5b49-104">Wenn die [Set-Anweisung](../statements/set-statement.md) mit einer restriktiveren Zugriffsebene als die- [Eigenschafts Anweisung](../statements/property-statement.md)gekennzeichnet ist, kann der Versuch, den Eigenschafts Wert festzulegen, in den folgenden Fällen fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="e5b49-104">If the [Set Statement](../statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
- <span data-ttu-id="e5b49-105">Die `Set` -Anweisung ist als [Privat](../modifiers/private.md) gekennzeichnet, und der Aufruf Code befindet sich außerhalb der Klasse oder Struktur, in der die Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5b49-105">The `Set` statement is marked [Private](../modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
- <span data-ttu-id="e5b49-106">Die `Set` -Anweisung ist als [geschützt](../modifiers/protected.md) markiert, und der Aufruf Code ist nicht in der Klasse oder Struktur, in der die Eigenschaft definiert ist, oder in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="e5b49-106">The `Set` statement is marked [Protected](../modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
- <span data-ttu-id="e5b49-107">Die `Set` -Anweisung ist als [Friend](../modifiers/friend.md) gekennzeichnet, und der Aufruf Code befindet sich nicht in derselben Assembly, in der die-Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5b49-107">The `Set` statement is marked [Friend](../modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="e5b49-108">**Fehler-ID:** BC31102</span><span class="sxs-lookup"><span data-stu-id="e5b49-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e5b49-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e5b49-109">To correct this error</span></span>  
  
- <span data-ttu-id="e5b49-110">Wenn Sie die Kontrolle über den Quellcode haben, der die Eigenschaft definiert, sollten Sie die `Set` Prozedur mit der gleichen Zugriffsebene wie die Eigenschaft selbst deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e5b49-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
- <span data-ttu-id="e5b49-111">Wenn Sie nicht über die Kontrolle über den Quellcode verfügen, der die Eigenschaft definiert, oder Sie die `Set` Prozedur Zugriffsebene über die Eigenschaft selbst einschränken müssen, versuchen Sie, die Anweisung zu verschieben, die den Eigenschafts Wert auf einen Code Bereich festlegt, der einen besseren Zugriff auf die Eigenschaft hat.</span><span class="sxs-lookup"><span data-stu-id="e5b49-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b49-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5b49-112">See also</span></span>

- [<span data-ttu-id="e5b49-113">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="e5b49-113">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="e5b49-114">Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="e5b49-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
