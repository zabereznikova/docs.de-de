---
title: <type1><typename> muss <membername> für die Schnittstelle <interfacename> implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 4ffe18e11c388a8c69ef0592bde1b78f5b219680
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386853"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="d66bf-102">\<type1>\<typename> muss \<membername> für die Schnittstelle \<interfacename> implementieren.</span><span class="sxs-lookup"><span data-stu-id="d66bf-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="d66bf-103">' \<typename> ' muss ' \<membername> ' für die-Schnittstelle implementieren \<interfacename> .</span><span class="sxs-lookup"><span data-stu-id="d66bf-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="d66bf-104">Die implementierende Eigenschaft muss über übereinstimmende "schreibgeschützte"/"schreibgeschützte"-spezifiatoren verfügen.</span><span class="sxs-lookup"><span data-stu-id="d66bf-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="d66bf-105">Eine Klasse oder Struktur beansprucht, eine Schnittstelle zu implementieren, implementiert jedoch keine Prozedur, Eigenschaft oder ein Ereignis, das von der Schnittstelle definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d66bf-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="d66bf-106">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d66bf-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="d66bf-107">**Fehler-ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="d66bf-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d66bf-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d66bf-108">To correct this error</span></span>  
  
1. <span data-ttu-id="d66bf-109">Deklarieren Sie einen Member mit dem gleichen Namen und der gleichen Signatur wie in der-Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="d66bf-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="d66bf-110">Stellen Sie sicher, dass Sie mindestens die- `End Function` ,- `End Sub` oder-Anweisung einschließen `End Property` .</span><span class="sxs-lookup"><span data-stu-id="d66bf-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="d66bf-111">Fügen Sie eine-Klausel am Ende der-,-,- `Implements` oder- `Function` Anweisung hinzu `Sub` `Property` `Event` .</span><span class="sxs-lookup"><span data-stu-id="d66bf-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="d66bf-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d66bf-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="d66bf-113">Wenn Sie eine Eigenschaft implementieren, stellen Sie sicher, dass `ReadOnly` oder `WriteOnly` auf die gleiche Weise wie in der Schnittstellen Definition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d66bf-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="d66bf-114">Wenn Sie eine Eigenschaft implementieren, deklarieren Sie nach Bedarf `Get` -und- `Set` Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="d66bf-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d66bf-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d66bf-115">See also</span></span>

- [<span data-ttu-id="d66bf-116">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d66bf-116">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="d66bf-117">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d66bf-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
