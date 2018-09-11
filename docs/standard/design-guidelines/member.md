---
title: Entwurfsrichtlinien für Member
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1598ac63af38f1ca3e11104bc8e1cd6323d35ed
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259966"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="56226-102">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="56226-102">Member Design Guidelines</span></span>
<span data-ttu-id="56226-103">Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder werden zusammen als Mitglieder bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="56226-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="56226-104">Elemente sind schließlich die Möglichkeit, die mit denen Framework-Funktionen für die Benutzer von einem Framework verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="56226-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="56226-105">Mitglieder können virtuell oder nicht virtuelle, konkrete oder abstrakt statischen oder werden und können mehrere unterschiedliche Bereiche der Barrierefreiheit haben.</span><span class="sxs-lookup"><span data-stu-id="56226-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="56226-106">Alle diese Reihe unglaublich Ausdruckskraft bietet jedoch zur gleichen Zeit erfordert Sorgfalt seitens der Framework-Designer.</span><span class="sxs-lookup"><span data-stu-id="56226-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="56226-107">Dieses Kapitel bietet grundlegende Richtlinien, die beim Entwerfen der Elemente eines beliebigen Typs befolgt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="56226-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56226-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="56226-108">In This Section</span></span>  
 [<span data-ttu-id="56226-109">Überladen von Membern</span><span class="sxs-lookup"><span data-stu-id="56226-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="56226-110">Eigenschaftenentwurf</span><span class="sxs-lookup"><span data-stu-id="56226-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="56226-111">Konstruktorentwurf</span><span class="sxs-lookup"><span data-stu-id="56226-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="56226-112">Ereignisentwurf</span><span class="sxs-lookup"><span data-stu-id="56226-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="56226-113">Feldentwurf</span><span class="sxs-lookup"><span data-stu-id="56226-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="56226-114">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="56226-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="56226-115">Operatorüberladungen</span><span class="sxs-lookup"><span data-stu-id="56226-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="56226-116">Parameterentwurf</span><span class="sxs-lookup"><span data-stu-id="56226-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="56226-117">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="56226-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="56226-118">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="56226-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56226-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56226-119">See also</span></span>

- [<span data-ttu-id="56226-120">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="56226-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
