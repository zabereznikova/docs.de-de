---
title: Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase.New" oder "MyClass.New" sein (Zugriff auf Konstruktor ohne Parameter nicht möglich)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: d29d7609f8f3f38eadda9a9c763f3ba8e6b99e61
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365086"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="f3fa6-102">Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase.New" oder "MyClass.New" sein (Zugriff auf Konstruktor ohne Parameter nicht möglich)</span><span class="sxs-lookup"><span data-stu-id="f3fa6-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="f3fa6-103">Die erste Anweisung dieser "Sub New" muss ein Aufruf von "MyBase.New" oder "MyClass.New" sein, da Basisklasse\<Basename >' von '\<Derivedname >' verfügt nicht über zugegriffen werden kann 'Sub New"hat, die ohne Argumente aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f3fa6-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="f3fa6-104">Jeder Konstruktor muss in einer abgeleiteten Klasse einen Basisklassenkonstruktor aufrufen (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="f3fa6-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="f3fa6-105">Wenn die Basisklasse der Klasse einen Konstruktor ohne Parameter verfügt, die abgeleiteten Klassen zugänglich ist `MyBase.New` automatisch aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f3fa6-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="f3fa6-106">Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f3fa6-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="f3fa6-107">In diesem Fall muss die erste Anweisung jeder abgeleiteten Klassenkonstruktor einen parametrisierten Konstruktor der Basisklasse aufrufen, oder rufen einen anderen Konstruktor in der abgeleiteten Klasse, mit der ein Konstruktor der Basisklasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f3fa6-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="f3fa6-108">**Fehler-ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="f3fa6-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f3fa6-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f3fa6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="f3fa6-110">Entweder Aufruf `MyBase.New` Angabe der erforderlichen Parameter, oder rufen Sie einen Peerkonstruktor, der solchen Aufruf ausführt.</span><span class="sxs-lookup"><span data-stu-id="f3fa6-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="f3fa6-111">Wenn die Basisklasse der Klasse einen Konstruktor verfügt, die als deklariert wird z. B. `Public Sub New(ByVal index as Integer)`, wird die erste Anweisung in der abgeleiteten Klassenkonstruktor möglicherweise `MyBase.New(100)`.</span><span class="sxs-lookup"><span data-stu-id="f3fa6-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3fa6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3fa6-112">See also</span></span>
- [<span data-ttu-id="f3fa6-113">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="f3fa6-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
