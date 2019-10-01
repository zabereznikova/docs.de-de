---
title: <type1> '<typename>' muss '<membername>' für die <interfacename>-Schnittstelle implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a824b66eaad964049ced5cae5eb2cc370d00ba7f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696894"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="9c4e7-102">\<Typ1 >'\<Typename > 'implementieren müssen'\<Membername >' für die Schnittstelle '\<Schnittstellenname >'</span><span class="sxs-lookup"><span data-stu-id="9c4e7-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="9c4e7-103">'\<Typename >' implementieren muss '\<Membername >' für die Schnittstelle '\<Schnittstellenname >'.</span><span class="sxs-lookup"><span data-stu-id="9c4e7-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="9c4e7-104">Die implementierende Eigenschaft muss über übereinstimmende "schreibgeschützte"/"schreibgeschützte"-spezifiatoren verfügen.</span><span class="sxs-lookup"><span data-stu-id="9c4e7-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="9c4e7-105">Eine Klasse oder Struktur beansprucht, eine Schnittstelle zu implementieren, implementiert jedoch keine Prozedur, Eigenschaft oder ein Ereignis, das von der Schnittstelle definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9c4e7-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="9c4e7-106">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="9c4e7-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="9c4e7-107">**Fehler-ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="9c4e7-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9c4e7-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9c4e7-108">To correct this error</span></span>  
  
1. <span data-ttu-id="9c4e7-109">Deklarieren Sie einen Member mit dem gleichen Namen und der gleichen Signatur wie in der-Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="9c4e7-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="9c4e7-110">Stellen Sie sicher, dass Sie mindestens die `End Function`-, `End Sub`-oder `End Property`-Anweisung einschließen.</span><span class="sxs-lookup"><span data-stu-id="9c4e7-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="9c4e7-111">Fügen Sie am Ende der `Function`-, `Sub`-, `Property`-oder `Event`-Anweisung eine `Implements`-Klausel hinzu.</span><span class="sxs-lookup"><span data-stu-id="9c4e7-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="9c4e7-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9c4e7-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="9c4e7-113">Wenn Sie eine Eigenschaft implementieren, stellen Sie sicher, dass `ReadOnly` oder `WriteOnly` auf die gleiche Weise wie in der Schnittstellen Definition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c4e7-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="9c4e7-114">Wenn Sie eine Eigenschaft implementieren, deklarieren Sie nach Bedarf `Get`-und `Set`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="9c4e7-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4e7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c4e7-115">See also</span></span>

- [<span data-ttu-id="9c4e7-116">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9c4e7-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="9c4e7-117">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9c4e7-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
