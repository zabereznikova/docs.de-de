---
title: Auf den Set-Accessor der <propertyname>-Eigenschaft kann nicht zugegriffen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 3cf828eb5f11090a74a65388e2b89a191046a456
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162244"
---
# <a name="bc31102-set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="57435-102">BC31102: auf den Set-Accessor der Eigenschaft "" kann nicht zugegriffen werden. \<propertyname></span><span class="sxs-lookup"><span data-stu-id="57435-102">BC31102: 'Set' accessor of property '\<propertyname>' is not accessible</span></span>

<span data-ttu-id="57435-103">Eine-Anweisung versucht, den Wert einer Eigenschaft zu speichern, wenn Sie keinen Zugriff auf die Prozedur der Eigenschaft hat `Set` .</span><span class="sxs-lookup"><span data-stu-id="57435-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>

 <span data-ttu-id="57435-104">Wenn die [Set-Anweisung](../statements/set-statement.md) mit einer restriktiveren Zugriffsebene als die- [Eigenschafts Anweisung](../statements/property-statement.md)gekennzeichnet ist, kann der Versuch, den Eigenschafts Wert festzulegen, in den folgenden Fällen fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="57435-104">If the [Set Statement](../statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>

- <span data-ttu-id="57435-105">Die `Set` -Anweisung ist als [Privat](../modifiers/private.md) gekennzeichnet, und der Aufruf Code befindet sich außerhalb der Klasse oder Struktur, in der die Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="57435-105">The `Set` statement is marked [Private](../modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>

- <span data-ttu-id="57435-106">Die `Set` -Anweisung ist als [geschützt](../modifiers/protected.md) markiert, und der Aufruf Code ist nicht in der Klasse oder Struktur, in der die Eigenschaft definiert ist, oder in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="57435-106">The `Set` statement is marked [Protected](../modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>

- <span data-ttu-id="57435-107">Die `Set` -Anweisung ist als [Friend](../modifiers/friend.md) gekennzeichnet, und der Aufruf Code befindet sich nicht in derselben Assembly, in der die-Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="57435-107">The `Set` statement is marked [Friend](../modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>

 <span data-ttu-id="57435-108">**Fehler-ID:** BC31102</span><span class="sxs-lookup"><span data-stu-id="57435-108">**Error ID:** BC31102</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="57435-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="57435-109">To correct this error</span></span>

- <span data-ttu-id="57435-110">Wenn Sie die Kontrolle über den Quellcode haben, der die Eigenschaft definiert, sollten Sie die `Set` Prozedur mit der gleichen Zugriffsebene wie die Eigenschaft selbst deklarieren.</span><span class="sxs-lookup"><span data-stu-id="57435-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>

- <span data-ttu-id="57435-111">Wenn Sie nicht über die Kontrolle über den Quellcode verfügen, der die Eigenschaft definiert, oder Sie die `Set` Prozedur Zugriffsebene über die Eigenschaft selbst einschränken müssen, versuchen Sie, die Anweisung zu verschieben, die den Eigenschafts Wert auf einen Code Bereich festlegt, der einen besseren Zugriff auf die Eigenschaft hat.</span><span class="sxs-lookup"><span data-stu-id="57435-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>

## <a name="see-also"></a><span data-ttu-id="57435-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57435-112">See also</span></span>

- [<span data-ttu-id="57435-113">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="57435-113">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="57435-114">Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="57435-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
