---
title: Auf den Get-Accessor der <propertyname>-Eigenschaft kann nicht zugegriffen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: bd6830e16ba3d1f76c61519b4456832a2efec716
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162907"
---
# <a name="bc31103-get-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="c0c9a-102">BC31103: auf den Get-Accessor der Eigenschaft "" kann nicht zugegriffen werden. \<propertyname></span><span class="sxs-lookup"><span data-stu-id="c0c9a-102">BC31103: 'Get' accessor of property '\<propertyname>' is not accessible</span></span>

<span data-ttu-id="c0c9a-103">Eine-Anweisung versucht, den Wert einer Eigenschaft abzurufen, wenn Sie keinen Zugriff auf die Prozedur der Eigenschaft hat `Get` .</span><span class="sxs-lookup"><span data-stu-id="c0c9a-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>

 <span data-ttu-id="c0c9a-104">Wenn die [Get-Anweisung](../statements/get-statement.md) mit einer restriktiveren Zugriffsebene als die- [Eigenschafts Anweisung](../statements/property-statement.md)gekennzeichnet ist, kann der Versuch, den Eigenschafts Wert zu lesen, in den folgenden Fällen fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="c0c9a-104">If the [Get Statement](../statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>

- <span data-ttu-id="c0c9a-105">Die `Get` -Anweisung ist als [Privat](../modifiers/private.md) gekennzeichnet, und der Aufruf Code befindet sich außerhalb der Klasse oder Struktur, in der die Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c0c9a-105">The `Get` statement is marked [Private](../modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>

- <span data-ttu-id="c0c9a-106">Die `Get` -Anweisung ist als [geschützt](../modifiers/protected.md) markiert, und der Aufruf Code ist nicht in der Klasse oder Struktur, in der die Eigenschaft definiert ist, oder in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="c0c9a-106">The `Get` statement is marked [Protected](../modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>

- <span data-ttu-id="c0c9a-107">Die `Get` -Anweisung ist als [Friend](../modifiers/friend.md) gekennzeichnet, und der Aufruf Code befindet sich nicht in derselben Assembly, in der die-Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c0c9a-107">The `Get` statement is marked [Friend](../modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>

 <span data-ttu-id="c0c9a-108">**Fehler-ID:** BC31103</span><span class="sxs-lookup"><span data-stu-id="c0c9a-108">**Error ID:** BC31103</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c0c9a-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c0c9a-109">To correct this error</span></span>

- <span data-ttu-id="c0c9a-110">Wenn Sie die Kontrolle über den Quellcode haben, der die Eigenschaft definiert, sollten Sie die `Get` Prozedur mit der gleichen Zugriffsebene wie die Eigenschaft selbst deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c0c9a-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>

- <span data-ttu-id="c0c9a-111">Wenn Sie nicht über die Kontrolle über den Quellcode verfügen, der die Eigenschaft definiert, oder wenn Sie die `Get` Prozedur Zugriffsebene mehr als die Eigenschaft selbst einschränken müssen, versuchen Sie, die Anweisung zu verschieben, die den Eigenschafts Wert liest, in einen Code Bereich, der einen besseren Zugriff auf die Eigenschaft hat.</span><span class="sxs-lookup"><span data-stu-id="c0c9a-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0c9a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0c9a-112">See also</span></span>

- [<span data-ttu-id="c0c9a-113">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="c0c9a-113">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="c0c9a-114">Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="c0c9a-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
