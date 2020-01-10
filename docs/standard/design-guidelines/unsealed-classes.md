---
title: Unversiegelte Klassen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: 8a5f1142674f83b5ef77f9f7e7e3518afd475e7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709009"
---
# <a name="unsealed-classes"></a><span data-ttu-id="785ea-102">Unversiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="785ea-102">Unsealed Classes</span></span>
<span data-ttu-id="785ea-103">Versiegelte Klassen können nicht von geerbt werden und verhindern die Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="785ea-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="785ea-104">Im Gegensatz dazu werden Klassen, die von geerbt werden können, als nicht versiegelte Klassen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="785ea-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="785ea-105">**✓ CONSIDER** virtuelle oder geschützten Member mit nicht versiegelten Klassen ohne hinzugefügt werden, da eine hervorragende Möglichkeit zum kostengünstigen bereitstellen noch viel Erweiterbarkeit für ein Framework freuen.</span><span class="sxs-lookup"><span data-stu-id="785ea-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="785ea-106">Entwickler möchten häufig von nicht versiegelten Klassen erben, um bequeme Member wie benutzerdefinierte Konstruktoren, neue Methoden oder Methoden Überladungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="785ea-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="785ea-107">Beispielsweise ist `System.Messaging.MessageQueue` nicht versiegelt und ermöglicht es Benutzern, benutzerdefinierte Warteschlangen zu erstellen, die standardmäßig einen bestimmten Warteschlangen Pfad haben, oder benutzerdefinierte Methoden hinzuzufügen, die die API für bestimmte Szenarien vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="785ea-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="785ea-108">Klassen sind in den meisten Programmiersprachen standardmäßig nicht versiegelt. Dies ist auch der empfohlene Standard für die meisten Klassen in Frameworks.</span><span class="sxs-lookup"><span data-stu-id="785ea-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="785ea-109">Die Erweiterbarkeit, die von nicht versiegelten Typen geboten wird, wird von frameworkbenutzern erheblich geschätzt und ist aufgrund relativ niedriger Testkosten, die mit nicht versiegelten Typen verbunden sind, sehr kostengünstig.</span><span class="sxs-lookup"><span data-stu-id="785ea-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="785ea-110">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="785ea-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="785ea-111">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="785ea-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785ea-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="785ea-112">See also</span></span>

- [<span data-ttu-id="785ea-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="785ea-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="785ea-114">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="785ea-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="785ea-115">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="785ea-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
