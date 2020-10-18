---
title: Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase.New" oder "MyClass.New" sein (Zugriff auf Konstruktor ohne Parameter nicht möglich)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: bce8ad10bc201386f34d6623741c7d41a5dec27e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163024"
---
# <a name="bc30148-first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="8bf2d-102">BC30148: die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase. New" oder "MyClass. New" sein (kein zugreif barer Konstruktor ohne Parameter).</span><span class="sxs-lookup"><span data-stu-id="8bf2d-102">BC30148: First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>

<span data-ttu-id="8bf2d-103">Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase. New" oder "MyClass. New" sein, da die Basisklasse "" \<basename> von "" keine zugreif Bare \<derivedname> "Sub New" hat, die ohne Argumente aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bf2d-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>

 <span data-ttu-id="8bf2d-104">In einer abgeleiteten Klasse muss jeder Konstruktor einen Basisklassenkonstruktor () aufzurufen `MyBase.New` .</span><span class="sxs-lookup"><span data-stu-id="8bf2d-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="8bf2d-105">Wenn die Basisklasse über einen Konstruktor ohne Parameter verfügt, auf den abgeleitete Klassen zugegriffen `MyBase.New` werden kann, kann automatisch aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8bf2d-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="8bf2d-106">Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch erfolgen.</span><span class="sxs-lookup"><span data-stu-id="8bf2d-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="8bf2d-107">In diesem Fall muss die erste Anweisung jedes abgeleiteten Klassenkonstruktors einen parametrisierten Konstruktor für die Basisklasse oder einen anderen Konstruktor in der abgeleiteten Klasse, der einen basisklassenkonstruktoraufzurufen, aufruft.</span><span class="sxs-lookup"><span data-stu-id="8bf2d-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>

 <span data-ttu-id="8bf2d-108">**Fehler-ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="8bf2d-108">**Error ID:** BC30148</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8bf2d-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8bf2d-109">To correct this error</span></span>

- <span data-ttu-id="8bf2d-110">Wenden Sie entweder an `MyBase.New` , um die erforderlichen Parameter anzugeben, oder nennen Sie einen Peerkonstruktor, der einen solchen aufruft.</span><span class="sxs-lookup"><span data-stu-id="8bf2d-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>

     <span data-ttu-id="8bf2d-111">Wenn die Basisklasse z. b. über einen Konstruktor verfügt, der als deklariert ist `Public Sub New(ByVal index as Integer)` , kann die erste Anweisung im Konstruktor der abgeleiteten Klasse sein `MyBase.New(100)` .</span><span class="sxs-lookup"><span data-stu-id="8bf2d-111">For example, if the base class has a constructor that's declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bf2d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bf2d-112">See also</span></span>

- [<span data-ttu-id="8bf2d-113">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="8bf2d-113">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
