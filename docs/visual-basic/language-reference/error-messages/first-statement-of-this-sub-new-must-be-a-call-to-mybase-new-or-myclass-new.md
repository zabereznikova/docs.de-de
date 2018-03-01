---
title: Die erste Anweisung dieser &#39; Sub New &#39; Hierbei muss es sich um einen Aufruf von &#39;sein. MyBase.New &#39; oder &#39; MyClass.New &#39; (Kein zugreifbarer Konstruktor ohne Parameter)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1065643e1f6c868092fbad839af0dbbd33afaf01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a><span data-ttu-id="5e82a-102">Die erste Anweisung dieser &#39; Sub New &#39; Hierbei muss es sich um einen Aufruf von &#39;sein. MyBase.New &#39; oder &#39; MyClass.New &#39; (Kein zugreifbarer Konstruktor ohne Parameter)</span><span class="sxs-lookup"><span data-stu-id="5e82a-102">First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="5e82a-103">Die erste Anweisung dieser "Sub New" muss ein Aufruf von "MyBase.New" oder "MyClass.New" sein, da Basisklasse\<Basename >' von '\<Derivedname >' besitzt keine zugegriffen werden kann "Sub New" hat, die ohne Argumente aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5e82a-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="5e82a-104">Jeder Konstruktor muss in einer abgeleiteten Klasse einen Basisklassenkonstruktor aufrufen (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="5e82a-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="5e82a-105">Wenn die Basisklasse der Klasse einen Konstruktor ohne Parameter verfügt, die für den abgeleiteten Klassen zugänglich ist `MyBase.New` automatisch aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5e82a-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="5e82a-106">Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5e82a-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="5e82a-107">In diesem Fall muss die erste Anweisung jeder abgeleiteten Klassenkonstruktor einen parametrisierten Konstruktor der Basisklasse aufrufen, oder rufen Sie einen anderen Konstruktor in der abgeleiteten Klasse, mit der ein Konstruktor der Basisklasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5e82a-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="5e82a-108">**Fehler-ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="5e82a-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5e82a-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5e82a-109">To correct this error</span></span>  
  
-   <span data-ttu-id="5e82a-110">Entweder Aufruf `MyBase.New` Geben Sie die erforderlichen Parameter, oder rufen Sie einen Peerkonstruktor, der solch einen Aufruf macht.</span><span class="sxs-lookup"><span data-stu-id="5e82a-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="5e82a-111">Angenommen, wenn die Basisklasse der Klasse einen Konstruktor verfügt, die als deklariert ist `Public Sub New(ByVal index as Integer)`, die erste Anweisung in der abgeleiteten Klassenkonstruktor möglicherweise `MyBase.New(100)`.</span><span class="sxs-lookup"><span data-stu-id="5e82a-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e82a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e82a-112">See Also</span></span>  
 [<span data-ttu-id="5e82a-113">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="5e82a-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
