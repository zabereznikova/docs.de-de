---
title: <type1> '<typename>' muss '<membername>' für die <interfacename>-Schnittstelle implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 485680a2984a29037b2836fcba13cf1aa1e2e699
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822751"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="909d9-102">\<Typ1 >'\<Typename > 'implementieren müssen'\<Membername >' für die Schnittstelle '\<Schnittstellenname >'</span><span class="sxs-lookup"><span data-stu-id="909d9-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="909d9-103">'\<Typename >' implementieren muss '\<Membername >' für die Schnittstelle '\<Schnittstellenname >'.</span><span class="sxs-lookup"><span data-stu-id="909d9-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="909d9-104">Die implementierende Eigenschaft müssen übereinstimmen 'ReadOnly' / 'WriteOnly' Spezifizierer.</span><span class="sxs-lookup"><span data-stu-id="909d9-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="909d9-105">Eine Klasse oder Struktur vorgibt, eine Schnittstelle zu implementieren, aber eine Prozedur, Eigenschaft oder das Ereignis definiert, die von der Schnittstelle nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="909d9-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="909d9-106">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="909d9-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="909d9-107">**Fehler-ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="909d9-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="909d9-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="909d9-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="909d9-109">Deklarieren Sie ein Element mit dem gleichen Namen und die gleiche Signatur wie in der Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="909d9-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="909d9-110">Müssen Sie mindestens die `End Function`, `End Sub`, oder `End Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="909d9-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="909d9-111">Hinzufügen einer `Implements` Klausel am Ende der `Function`, `Sub`, `Property`, oder `Event` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="909d9-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="909d9-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="909d9-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="909d9-113">Wenn Sie eine Eigenschaft zu implementieren, stellen sicher, dass `ReadOnly` oder `WriteOnly` wird verwendet, auf die gleiche Weise wie die Schnittstellendefinition.</span><span class="sxs-lookup"><span data-stu-id="909d9-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="909d9-114">Wenn Sie eine Eigenschaft implementieren möchten, deklarieren `Get` und `Set` Verfahren nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="909d9-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909d9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="909d9-115">See also</span></span>

- [<span data-ttu-id="909d9-116">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="909d9-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="909d9-117">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="909d9-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
