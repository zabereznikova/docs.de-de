---
title: "Entwurfsrichtlinien für Member"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae69b77098c7f2e1de83eedd40cf0f0da9473326
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="member-design-guidelines"></a><span data-ttu-id="ee0d0-102">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="ee0d0-102">Member Design Guidelines</span></span>
<span data-ttu-id="ee0d0-103">Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder werden zusammenfassend als Mitglieder bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ee0d0-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="ee0d0-104">Mitglieder werden letztlich von der Framework-Funktionalitäten an die Endbenutzer von einem Framework verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="ee0d0-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="ee0d0-105">Mitglieder möglich, virtuellen oder nicht virtuelle, konkrete oder abstrakten, statischen oder und können mehrere unterschiedliche Bereiche der Barrierefreiheit haben.</span><span class="sxs-lookup"><span data-stu-id="ee0d0-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="ee0d0-106">Alle Vielfalt unglaubliche Ausdruckskraft bietet jedoch zur selben Zeit erfordert Sorgfalt seitens der Framework-Designer.</span><span class="sxs-lookup"><span data-stu-id="ee0d0-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="ee0d0-107">Dieses Kapitel bietet die grundlegende Richtlinien, die beim Entwerfen der Elemente eines beliebigen Typs ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ee0d0-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee0d0-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ee0d0-108">In This Section</span></span>  
 [<span data-ttu-id="ee0d0-109">Überladen von Membern</span><span class="sxs-lookup"><span data-stu-id="ee0d0-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="ee0d0-110">Eigenschaftenentwurf</span><span class="sxs-lookup"><span data-stu-id="ee0d0-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="ee0d0-111">Konstruktorentwurf</span><span class="sxs-lookup"><span data-stu-id="ee0d0-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="ee0d0-112">Ereignisentwurf</span><span class="sxs-lookup"><span data-stu-id="ee0d0-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="ee0d0-113">Feldentwurf</span><span class="sxs-lookup"><span data-stu-id="ee0d0-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="ee0d0-114">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="ee0d0-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="ee0d0-115">Operatorüberladungen</span><span class="sxs-lookup"><span data-stu-id="ee0d0-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="ee0d0-116">Parameterentwurf</span><span class="sxs-lookup"><span data-stu-id="ee0d0-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="ee0d0-117">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="ee0d0-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ee0d0-118">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="ee0d0-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0d0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee0d0-119">See Also</span></span>  
 [<span data-ttu-id="ee0d0-120">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ee0d0-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
