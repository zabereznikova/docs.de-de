---
title: Initialisierer erwartet
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: cbe77bab3e4f8bf2094c70c1c16d95ee897c729e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163011"
---
# <a name="bc30996-initializer-expected"></a><span data-ttu-id="843aa-102">BC30996: Initialisierer erwartet</span><span class="sxs-lookup"><span data-stu-id="843aa-102">BC30996: Initializer expected</span></span>

<span data-ttu-id="843aa-103">Sie haben versucht, eine Instanz einer Klasse zu deklarieren, indem Sie einen Objektinitialisierer verwenden, in dem die Initialisierungs Liste leer ist, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="843aa-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>

 `' Not valid.`

 `' Dim aStudent As New Student With {}`

 <span data-ttu-id="843aa-104">Mindestens ein Feld oder eine Eigenschaft muss in der Initialisiererliste initialisiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="843aa-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>

 `Dim aStudent As New Student With {.year = "Senior"}`

 <span data-ttu-id="843aa-105">**Fehler-ID:** BC30996</span><span class="sxs-lookup"><span data-stu-id="843aa-105">**Error ID:** BC30996</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="843aa-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="843aa-106">To correct this error</span></span>

- <span data-ttu-id="843aa-107">Initialisieren Sie mindestens ein Feld oder eine Eigenschaft im Initialisierer, oder verwenden Sie keinen Objektinitialisierer.</span><span class="sxs-lookup"><span data-stu-id="843aa-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>

## <a name="see-also"></a><span data-ttu-id="843aa-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="843aa-108">See also</span></span>

- [<span data-ttu-id="843aa-109">Objektinitialisierer: benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="843aa-109">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="843aa-110">Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers</span><span class="sxs-lookup"><span data-stu-id="843aa-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
