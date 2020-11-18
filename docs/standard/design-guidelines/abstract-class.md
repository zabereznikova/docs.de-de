---
title: Entwurf abstrakter Klassen
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 6903e10c8695376d8ac5961461796c5413307f90
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821644"
---
# <a name="abstract-class-design"></a><span data-ttu-id="02eea-102">Entwurf abstrakter Klassen</span><span class="sxs-lookup"><span data-stu-id="02eea-102">Abstract Class Design</span></span>

<span data-ttu-id="02eea-103">❌ Definieren Sie keine öffentlichen oder geschützten internen Konstruktoren in abstrakten Typen.</span><span class="sxs-lookup"><span data-stu-id="02eea-103">❌ DO NOT define public or protected internal constructors in abstract types.</span></span>

 <span data-ttu-id="02eea-104">Konstruktoren sollten nur dann öffentlich sein, wenn Benutzer Instanzen des Typs erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="02eea-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="02eea-105">Da es nicht möglich ist, Instanzen eines abstrakten Typs zu erstellen, wurde ein abstrakter Typ mit einem öffentlichen Konstruktor falsch entworfen und ist für die Benutzer irreführend.</span><span class="sxs-lookup"><span data-stu-id="02eea-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>

 <span data-ttu-id="02eea-106">✔️ einen geschützten oder einen internen Konstruktor in abstrakten Klassen definieren.</span><span class="sxs-lookup"><span data-stu-id="02eea-106">✔️ DO define a protected or an internal constructor in abstract classes.</span></span>

 <span data-ttu-id="02eea-107">Ein geschützter Konstruktor ist häufiger und ermöglicht es der Basisklasse, eine eigene Initialisierung durchzuführen, wenn Untertypen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="02eea-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>

 <span data-ttu-id="02eea-108">Ein interner Konstruktor kann verwendet werden, um konkrete Implementierungen der abstrakten Klasse auf die Assembly zu beschränken, die die Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="02eea-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>

 <span data-ttu-id="02eea-109">✔️ Geben Sie mindestens einen konkreten Typ an, der von jeder von Ihnen gelieferten abstrakten Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="02eea-109">✔️ DO provide at least one concrete type that inherits from each abstract class that you ship.</span></span>

 <span data-ttu-id="02eea-110">Dies erleichtert das Überprüfen des Entwurfs der abstrakten Klasse.</span><span class="sxs-lookup"><span data-stu-id="02eea-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="02eea-111">Beispielsweise  <xref:System.IO.FileStream?displayProperty=nameWithType> ist eine Implementierung der abstrakten- <xref:System.IO.Stream?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="02eea-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>

 <span data-ttu-id="02eea-112">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="02eea-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="02eea-113">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="02eea-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="02eea-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02eea-114">See also</span></span>

- [<span data-ttu-id="02eea-115">Typentwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="02eea-115">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="02eea-116">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="02eea-116">Framework Design Guidelines</span></span>](index.md)
