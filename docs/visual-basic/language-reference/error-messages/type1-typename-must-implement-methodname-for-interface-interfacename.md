---
title: <type1><typename> muss <methodname> für die Schnittstelle <interfacename> implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 90d2b6d70390bfb732af4a5868c935de61d18f94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408496"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="545fb-102">\<type1>\<typename> muss \<methodname> für die Schnittstelle \<interfacename> implementieren.</span><span class="sxs-lookup"><span data-stu-id="545fb-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="545fb-103">Eine Klasse oder Struktur beansprucht, eine Schnittstelle zu implementieren, implementiert jedoch keine durch die Schnittstelle definierte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="545fb-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="545fb-104">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="545fb-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="545fb-105">**Fehler-ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="545fb-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="545fb-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="545fb-106">To correct this error</span></span>  
  
1. <span data-ttu-id="545fb-107">Deklarieren Sie eine Prozedur mit dem gleichen Namen und der gleichen Signatur wie in der-Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="545fb-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="545fb-108">Stellen Sie sicher, dass Sie mindestens die- `End Function` oder- `End Sub` Anweisung einschließen.</span><span class="sxs-lookup"><span data-stu-id="545fb-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="545fb-109">Fügen Sie eine- `Implements` Klausel am Ende der- `Function` oder-Anweisung hinzu `Sub` .</span><span class="sxs-lookup"><span data-stu-id="545fb-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="545fb-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="545fb-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="545fb-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="545fb-111">See also</span></span>

- [<span data-ttu-id="545fb-112">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="545fb-112">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="545fb-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="545fb-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
