---
title: Unversiegelte Klassen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: KrzysztofCwalina
ms.openlocfilehash: 8d7b1500506ec73a0d33d5352756cb85039358e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153227"
---
# <a name="unsealed-classes"></a><span data-ttu-id="da3c5-102">Unversiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="da3c5-102">Unsealed Classes</span></span>
<span data-ttu-id="da3c5-103">Versiegelte Klassen können nicht geerbt werden, aus, und sie verhindern, dass Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="da3c5-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="da3c5-104">Im Gegensatz dazu sind Klassen, die von geerbt werden können, nicht versiegelte Klassen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="da3c5-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="da3c5-105">**✓ CONSIDER** virtuelle oder geschützten Member mit nicht versiegelten Klassen ohne hinzugefügt werden, da eine hervorragende Möglichkeit zum kostengünstigen bereitstellen noch viel Erweiterbarkeit für ein Framework freuen.</span><span class="sxs-lookup"><span data-stu-id="da3c5-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="da3c5-106">Entwickler möchten häufig das nicht versiegelte Klassen, um das Hinzufügen von Mitgliedern der Einfachheit halber, z. B. benutzerdefinierten Konstruktoren, neue Methoden und methodenüberladungen erben.</span><span class="sxs-lookup"><span data-stu-id="da3c5-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="da3c5-107">Z. B. `System.Messaging.MessageQueue` ist unversiegelt, und daher können Benutzer, die zum Erstellen von benutzerdefinierter Warteschlangen, die standardmäßig der Pfad einer bestimmten Warteschlange oder zum Hinzufügen von benutzerdefinierter Methoden, die die API für bestimmte Szenarien zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="da3c5-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="da3c5-108">Klassen sind in den meisten Programmiersprachen standardmäßig nicht versiegelt, und dies ist auch die empfohlene Standardvorgehensweise für die meisten Klassen in Frameworks.</span><span class="sxs-lookup"><span data-stu-id="da3c5-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="da3c5-109">Die Erweiterbarkeit verfügbaren unversiegelte Typen ist viel geschätzt, Framework-Benutzer und recht wenig Aufwand aufgrund von mit relativ niedrigen Testkosten im Zusammenhang mit unversiegelte Typen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="da3c5-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="da3c5-110">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="da3c5-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="da3c5-111">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="da3c5-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3c5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da3c5-112">See also</span></span>

- [<span data-ttu-id="da3c5-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="da3c5-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="da3c5-114">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="da3c5-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="da3c5-115">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="da3c5-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
