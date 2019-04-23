---
title: <type1> '<typename>' muss '<methodname>' für die <interfacename>-Schnittstelle implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 432f089bc77928308820d7456d930fba8dc513f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304908"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="4eae1-102">\<Typ1 >'\<Typname > 'implementieren muss'\<Methodname > 'für Schnittstelle'\<Schnittstellenname >'</span><span class="sxs-lookup"><span data-stu-id="4eae1-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="4eae1-103">Eine Klasse oder Struktur vorgibt, eine Schnittstelle zu implementieren, ohne dass eine Prozedur, die von der Schnittstelle definierten implementiert.</span><span class="sxs-lookup"><span data-stu-id="4eae1-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="4eae1-104">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="4eae1-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="4eae1-105">**Fehler-ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="4eae1-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4eae1-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4eae1-106">To correct this error</span></span>  
  
1. <span data-ttu-id="4eae1-107">Deklarieren Sie eine Prozedur mit dem gleichen Namen und die gleiche Signatur wie in der Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="4eae1-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="4eae1-108">Müssen Sie mindestens die `End Function` oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4eae1-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="4eae1-109">Hinzufügen einer `Implements` Klausel am Ende der `Function` oder `Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4eae1-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="4eae1-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4eae1-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4eae1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4eae1-111">See also</span></span>

- [<span data-ttu-id="4eae1-112">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4eae1-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="4eae1-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4eae1-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
