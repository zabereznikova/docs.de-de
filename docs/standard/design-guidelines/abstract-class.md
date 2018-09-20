---
title: Entwurf abstrakter Klassen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b9dacc4995a126e1ee3f6062dca796194d4882
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46493489"
---
# <a name="abstract-class-design"></a><span data-ttu-id="19331-102">Entwurf abstrakter Klassen</span><span class="sxs-lookup"><span data-stu-id="19331-102">Abstract Class Design</span></span>
<span data-ttu-id="19331-103">**X DO NOT** öffentliche oder geschützte interne Konstruktoren in abstrakten Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="19331-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="19331-104">Konstruktoren sollten nur, wenn Benutzer zum Erstellen von Instanzen des Typs müssen öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="19331-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="19331-105">Da Instanzen eines abstrakten Typs kann nicht erstellt werden, ist ein abstrakter Typ mit einem öffentlichen Konstruktor fehlerhaft entworfene und irreführend, die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="19331-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="19331-106">**✓ DO** einer geschützten oder internen-Konstruktor in abstrakten Klassen definieren.</span><span class="sxs-lookup"><span data-stu-id="19331-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="19331-107">Ein geschützter Konstruktor wird häufiger verwendet und ermöglicht es einfach die Basisklasse, um seine eigenen Initialisierung auszuführen, wenn Untertypen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="19331-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="19331-108">Ein interner Konstruktor kann verwendet werden, um konkrete Implementierungen der abstrakten Klasse auf die Assembly mit dem Definieren der Klasse zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="19331-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="19331-109">**✓ DO** Geben Sie mindestens einen konkreten Typ, die von jeder abstrakten Klasse erbt, die Sie versenden.</span><span class="sxs-lookup"><span data-stu-id="19331-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="19331-110">Dies erleichtert das Design der abstrakten Klasse zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="19331-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="19331-111">Z. B. <xref:System.IO.FileStream?displayProperty=nameWithType> ist eine Implementierung der <xref:System.IO.Stream?displayProperty=nameWithType> abstrakte Klasse.</span><span class="sxs-lookup"><span data-stu-id="19331-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="19331-112">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="19331-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="19331-113">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="19331-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19331-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19331-114">See also</span></span>

- [<span data-ttu-id="19331-115">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="19331-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="19331-116">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="19331-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
