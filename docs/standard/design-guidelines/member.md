---
title: Entwurfsrichtlinien für Member
description: Lernen Sie die Entwurfs Richtlinien für Member in .net kennen. Zu den Membern zählen Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder.
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: 5070f45beccd89d6f051f1b1d8345390e915d471
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706592"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="b812c-104">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="b812c-104">Member Design Guidelines</span></span>

<span data-ttu-id="b812c-105">Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder werden zusammen als Member bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b812c-105">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="b812c-106">Member sind letztendlich die Mittel, mit denen Frameworkfunktionen den Endbenutzern eines Frameworks zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b812c-106">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="b812c-107">Mitglieder können virtuell oder nicht virtuell, konkret oder abstrakt, statisch oder eine Instanz sein und mehrere verschiedene Bereiche der Barrierefreiheit haben.</span><span class="sxs-lookup"><span data-stu-id="b812c-107">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="b812c-108">Diese ganze Zahl bietet eine unglaubliche Ausdruckskraft, aber gleichzeitig muss der Teil des frameworkdesigners berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="b812c-108">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="b812c-109">Dieses Kapitel enthält grundlegende Richtlinien, die beim Entwerfen von Membern eines beliebigen Typs befolgt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="b812c-109">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b812c-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b812c-110">In This Section</span></span>  

 [<span data-ttu-id="b812c-111">Element Überladung</span><span class="sxs-lookup"><span data-stu-id="b812c-111">Member Overloading</span></span>](member-overloading.md)  
 [<span data-ttu-id="b812c-112">Eigenschafts Entwurf</span><span class="sxs-lookup"><span data-stu-id="b812c-112">Property Design</span></span>](property.md)  
 [<span data-ttu-id="b812c-113">Konstruktorentwurf</span><span class="sxs-lookup"><span data-stu-id="b812c-113">Constructor Design</span></span>](constructor.md)  
 [<span data-ttu-id="b812c-114">Ereignis Entwurf</span><span class="sxs-lookup"><span data-stu-id="b812c-114">Event Design</span></span>](event.md)  
 [<span data-ttu-id="b812c-115">Feld Entwurf</span><span class="sxs-lookup"><span data-stu-id="b812c-115">Field Design</span></span>](field.md)  
 [<span data-ttu-id="b812c-116">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="b812c-116">Extension Methods</span></span>](extension-methods.md)  
 [<span data-ttu-id="b812c-117">Operator Überladungen</span><span class="sxs-lookup"><span data-stu-id="b812c-117">Operator Overloads</span></span>](operator-overloads.md)  
 [<span data-ttu-id="b812c-118">Parameter Entwurf</span><span class="sxs-lookup"><span data-stu-id="b812c-118">Parameter Design</span></span>](parameter-design.md)  
 <span data-ttu-id="b812c-119">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="b812c-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b812c-120">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b812c-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b812c-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b812c-121">See also</span></span>

- [<span data-ttu-id="b812c-122">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="b812c-122">Framework Design Guidelines</span></span>](index.md)
