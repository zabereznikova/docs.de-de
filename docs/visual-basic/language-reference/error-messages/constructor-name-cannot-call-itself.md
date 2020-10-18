---
title: 'Der Konstruktor "<name>" kann sich nicht selbst aufrufen:'
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: f40319cde8388b17e27cfaec2117ebd519ebd4ff
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160944"
---
# <a name="bc30298-constructor-name-cannot-call-itself"></a><span data-ttu-id="f436e-102">BC30298: der Konstruktor " \<name> " kann sich nicht selbst anrufen.</span><span class="sxs-lookup"><span data-stu-id="f436e-102">BC30298: Constructor '\<name>' cannot call itself</span></span>

<span data-ttu-id="f436e-103">Eine `Sub New` Prozedur in einer Klasse oder Struktur ruft sich selbst auf.</span><span class="sxs-lookup"><span data-stu-id="f436e-103">A `Sub New` procedure in a class or structure calls itself.</span></span>

 <span data-ttu-id="f436e-104">Der Zweck eines Konstruktors besteht darin, eine Instanz einer Klasse oder Struktur zu initialisieren, wenn Sie erstmalig erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f436e-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="f436e-105">Eine Klasse oder Struktur kann mehrere Konstruktoren aufweisen, vorausgesetzt, Sie verfügen über unterschiedliche Parameterlisten.</span><span class="sxs-lookup"><span data-stu-id="f436e-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="f436e-106">Ein Konstruktor ist berechtigt, einen anderen Konstruktor aufzurufen, um seine Funktionalität zusätzlich zu seiner eigenen Funktionalität auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f436e-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="f436e-107">Es ist jedoch nicht bedeutungslos, dass sich ein Konstruktor selbst aufruft, und es würde tatsächlich zu einer unendlichen Rekursion kommen, wenn dies zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="f436e-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>

 <span data-ttu-id="f436e-108">**Fehler-ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="f436e-108">**Error ID:** BC30298</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f436e-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f436e-109">To correct this error</span></span>

1. <span data-ttu-id="f436e-110">Überprüfen Sie die Parameterliste des aufgerufenen Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="f436e-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="f436e-111">Er sollte sich von dem des aufzurufenden Konstruktors unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f436e-111">It should be different from that of the constructor making the call.</span></span>

2. <span data-ttu-id="f436e-112">Wenn Sie nicht beabsichtigen, einen anderen Konstruktor aufzurufen, entfernen Sie den-Befehl `Sub New` vollständig.</span><span class="sxs-lookup"><span data-stu-id="f436e-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>

## <a name="see-also"></a><span data-ttu-id="f436e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f436e-113">See also</span></span>

- [<span data-ttu-id="f436e-114">Objektlebensdauer: Erstellen und Zerstören von Objekten</span><span class="sxs-lookup"><span data-stu-id="f436e-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
