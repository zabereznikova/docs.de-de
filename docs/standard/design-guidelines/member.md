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
ms.openlocfilehash: 1c04b431224a1d4f03e85397b854a52856e114e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571396"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="b40d4-102">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="b40d4-102">Member Design Guidelines</span></span>
<span data-ttu-id="b40d4-103">Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder werden zusammenfassend als Mitglieder bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b40d4-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="b40d4-104">Mitglieder werden letztlich von der Framework-Funktionalitäten an die Endbenutzer von einem Framework verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="b40d4-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="b40d4-105">Mitglieder möglich, virtuellen oder nicht virtuelle, konkrete oder abstrakten, statischen oder und können mehrere unterschiedliche Bereiche der Barrierefreiheit haben.</span><span class="sxs-lookup"><span data-stu-id="b40d4-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="b40d4-106">Alle Vielfalt unglaubliche Ausdruckskraft bietet jedoch zur selben Zeit erfordert Sorgfalt seitens der Framework-Designer.</span><span class="sxs-lookup"><span data-stu-id="b40d4-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="b40d4-107">Dieses Kapitel bietet die grundlegende Richtlinien, die beim Entwerfen der Elemente eines beliebigen Typs ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b40d4-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b40d4-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b40d4-108">In This Section</span></span>  
 [<span data-ttu-id="b40d4-109">Überladen von Membern</span><span class="sxs-lookup"><span data-stu-id="b40d4-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="b40d4-110">Eigenschaftenentwurf</span><span class="sxs-lookup"><span data-stu-id="b40d4-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="b40d4-111">Konstruktorentwurf</span><span class="sxs-lookup"><span data-stu-id="b40d4-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="b40d4-112">Ereignisentwurf</span><span class="sxs-lookup"><span data-stu-id="b40d4-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="b40d4-113">Feldentwurf</span><span class="sxs-lookup"><span data-stu-id="b40d4-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="b40d4-114">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="b40d4-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="b40d4-115">Operatorüberladungen</span><span class="sxs-lookup"><span data-stu-id="b40d4-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="b40d4-116">Parameterentwurf</span><span class="sxs-lookup"><span data-stu-id="b40d4-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="b40d4-117">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="b40d4-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b40d4-118">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="b40d4-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b40d4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b40d4-119">See Also</span></span>  
 [<span data-ttu-id="b40d4-120">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="b40d4-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
