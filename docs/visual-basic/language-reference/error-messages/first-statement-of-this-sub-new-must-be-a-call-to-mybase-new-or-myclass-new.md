---
title: Die erste Anweisung dieser &#39;Sub New&#39; muss ein Aufruf von &#39;MyBase.New&#39; oder &#39;MyClass.New&#39; (Konstruktor ohne Parameter nicht möglich)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 75832ae88908094c1cb74ce04ad84c0d2ae91e68
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728894"
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a><span data-ttu-id="d8e91-102">Die erste Anweisung dieser &#39;Sub New&#39; muss ein Aufruf von &#39;MyBase.New&#39; oder &#39;MyClass.New&#39; (Konstruktor ohne Parameter nicht möglich)</span><span class="sxs-lookup"><span data-stu-id="d8e91-102">First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="d8e91-103">Die erste Anweisung dieser "Sub New" muss ein Aufruf von "MyBase.New" oder "MyClass.New" sein, da Basisklasse\<Basename >' von '\<Derivedname >' verfügt nicht über zugegriffen werden kann 'Sub New"hat, die ohne Argumente aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8e91-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="d8e91-104">Jeder Konstruktor muss in einer abgeleiteten Klasse einen Basisklassenkonstruktor aufrufen (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="d8e91-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="d8e91-105">Wenn die Basisklasse der Klasse einen Konstruktor ohne Parameter verfügt, die abgeleiteten Klassen zugänglich ist `MyBase.New` automatisch aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8e91-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="d8e91-106">Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d8e91-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="d8e91-107">In diesem Fall muss die erste Anweisung jeder abgeleiteten Klassenkonstruktor einen parametrisierten Konstruktor der Basisklasse aufrufen, oder rufen einen anderen Konstruktor in der abgeleiteten Klasse, mit der ein Konstruktor der Basisklasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d8e91-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="d8e91-108">**Fehler-ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="d8e91-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8e91-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d8e91-109">To correct this error</span></span>  
  
-   <span data-ttu-id="d8e91-110">Entweder Aufruf `MyBase.New` Angabe der erforderlichen Parameter, oder rufen Sie einen Peerkonstruktor, der solchen Aufruf ausführt.</span><span class="sxs-lookup"><span data-stu-id="d8e91-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="d8e91-111">Wenn die Basisklasse der Klasse einen Konstruktor verfügt, die als deklariert wird z. B. `Public Sub New(ByVal index as Integer)`, wird die erste Anweisung in der abgeleiteten Klassenkonstruktor möglicherweise `MyBase.New(100)`.</span><span class="sxs-lookup"><span data-stu-id="d8e91-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e91-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8e91-112">See also</span></span>
- [<span data-ttu-id="d8e91-113">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="d8e91-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
