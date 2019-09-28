---
title: <type1> '<typename>' muss '<methodname>' für die <interfacename>-Schnittstelle implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591599"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="a2337-102">\<Typ1 >'\<Typname > 'implementieren muss'\<Methodname > 'für Schnittstelle'\<Schnittstellenname >'</span><span class="sxs-lookup"><span data-stu-id="a2337-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="a2337-103">Eine Klasse oder Struktur beansprucht, eine Schnittstelle zu implementieren, implementiert jedoch keine durch die Schnittstelle definierte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="a2337-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="a2337-104">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a2337-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="a2337-105">**Fehler-ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="a2337-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a2337-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a2337-106">To correct this error</span></span>  
  
1. <span data-ttu-id="a2337-107">Deklarieren Sie eine Prozedur mit dem gleichen Namen und der gleichen Signatur wie in der-Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="a2337-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="a2337-108">Stellen Sie sicher, dass Sie mindestens die `End Function`-oder `End Sub`-Anweisung einschließen.</span><span class="sxs-lookup"><span data-stu-id="a2337-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="a2337-109">Fügen Sie am Ende der `Function`-oder `Sub`-Anweisung eine `Implements`-Klausel hinzu.</span><span class="sxs-lookup"><span data-stu-id="a2337-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="a2337-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a2337-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a2337-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2337-111">See also</span></span>

- [<span data-ttu-id="a2337-112">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a2337-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="a2337-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a2337-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
