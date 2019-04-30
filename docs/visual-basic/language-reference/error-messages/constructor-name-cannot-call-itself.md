---
title: 'Der Konstruktor "<name>" kann sich nicht selbst aufrufen:'
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 8459ee7fec6d761161a721c88ccdc88e513fc95f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936694"
---
# <a name="constructor-name-cannot-call-itself"></a><span data-ttu-id="4592d-102">Konstruktor '\<Name >' kann nicht selbst aufrufen</span><span class="sxs-lookup"><span data-stu-id="4592d-102">Constructor '\<name>' cannot call itself</span></span>
<span data-ttu-id="4592d-103">Ein `Sub New` Prozedur in einer Klasse oder Struktur ruft sich selbst.</span><span class="sxs-lookup"><span data-stu-id="4592d-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="4592d-104">Gibt einen Überblick einen Konstruktor zum Initialisieren einer Instanz einer Klasse oder Struktur bei erstellt.</span><span class="sxs-lookup"><span data-stu-id="4592d-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="4592d-105">Eine Klasse oder Struktur haben mehrere Konstruktoren, sofern diese unterschiedlichen Parameterlisten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4592d-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="4592d-106">Ein Konstruktor ist zulässig, einen anderen Konstruktor, um ihre Funktionalität zusätzlich zu seiner eigenen auszuführen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4592d-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="4592d-107">Aber es ist ohne Bedeutung für einen Konstruktor selbst aufrufen, und in der Tat hätte dies Endlosschleife, wenn zulässig.</span><span class="sxs-lookup"><span data-stu-id="4592d-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="4592d-108">**Fehler-ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="4592d-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4592d-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4592d-109">To correct this error</span></span>  
  
1. <span data-ttu-id="4592d-110">Überprüfen Sie die Parameterliste des Konstruktors aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4592d-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="4592d-111">Es sollte sich von der Konstruktor den Aufruf sein.</span><span class="sxs-lookup"><span data-stu-id="4592d-111">It should be different from that of the constructor making the call.</span></span>  
  
2. <span data-ttu-id="4592d-112">Wenn Sie nicht beabsichtigen, einen anderen Konstruktor aufrufen, entfernen Sie die `Sub New` ganz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4592d-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4592d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4592d-113">See also</span></span>

- [<span data-ttu-id="4592d-114">Objektlebensdauer: Wie die Objekte erstellt und zerstört werden</span><span class="sxs-lookup"><span data-stu-id="4592d-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
