---
title: <type1><typename> muss <methodname> für die Schnittstelle <interfacename> implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 68c6f65e6be229cc74458fa56fe3d3aa889c18f7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161867"
---
# <a name="bc30149-type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="9c12f-102">BC30149: \<type1> ' \<typename> ' muss ' \<methodname> ' für die-Schnittstelle implementieren \<interfacename> .</span><span class="sxs-lookup"><span data-stu-id="9c12f-102">BC30149: \<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="9c12f-103">Eine Klasse oder Struktur beansprucht, eine Schnittstelle zu implementieren, implementiert jedoch keine durch die Schnittstelle definierte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="9c12f-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="9c12f-104">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="9c12f-104">Every member of the interface must be implemented.</span></span>

 <span data-ttu-id="9c12f-105">**Fehler-ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="9c12f-105">**Error ID:** BC30149</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="9c12f-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9c12f-106">To correct this error</span></span>

1. <span data-ttu-id="9c12f-107">Deklarieren Sie eine Prozedur mit dem gleichen Namen und der gleichen Signatur wie in der-Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="9c12f-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="9c12f-108">Stellen Sie sicher, dass Sie mindestens die- `End Function` oder- `End Sub` Anweisung einschließen.</span><span class="sxs-lookup"><span data-stu-id="9c12f-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>

2. <span data-ttu-id="9c12f-109">Fügen Sie eine- `Implements` Klausel am Ende der- `Function` oder-Anweisung hinzu `Sub` .</span><span class="sxs-lookup"><span data-stu-id="9c12f-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="9c12f-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9c12f-110">For example:</span></span>

    ```vb
    Public Sub DoSomething() Implements IBaseInterface.DoSomething
    ```

## <a name="see-also"></a><span data-ttu-id="9c12f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c12f-111">See also</span></span>

- [<span data-ttu-id="9c12f-112">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9c12f-112">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="9c12f-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9c12f-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
