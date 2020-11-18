---
title: Unversiegelte Klassen
ms.date: 10/22/2008
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: b2e14b435aa567f231230da34307014210d46ccb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828516"
---
# <a name="unsealed-classes"></a><span data-ttu-id="2cfd9-102">Unversiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="2cfd9-102">Unsealed Classes</span></span>
<span data-ttu-id="2cfd9-103">Versiegelte Klassen können nicht von geerbt werden und verhindern die Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="2cfd9-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="2cfd9-104">Im Gegensatz dazu werden Klassen, die von geerbt werden können, als nicht versiegelte Klassen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2cfd9-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>

 <span data-ttu-id="2cfd9-105">✔️ sollten Sie in Erwägung gezogen werden, nicht versiegelte Klassen ohne hinzugefügte virtuelle oder geschützte Member als hervorragend zu verwenden, um eine kostengünstige Erweiterbarkeit für ein Framework zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="2cfd9-105">✔️ CONSIDER using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>

 <span data-ttu-id="2cfd9-106">Entwickler möchten häufig von nicht versiegelten Klassen erben, um bequeme Member wie benutzerdefinierte Konstruktoren, neue Methoden oder Methoden Überladungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2cfd9-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="2cfd9-107">Beispielsweise  `System.Messaging.MessageQueue` ist nicht versiegelt und ermöglicht Benutzern das Erstellen benutzerdefinierter Warteschlangen, die standardmäßig einen bestimmten Warteschlangen Pfad haben, oder das Hinzufügen von benutzerdefinierten Methoden, die die API für bestimmte Szenarien vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="2cfd9-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>

 <span data-ttu-id="2cfd9-108">Klassen sind in den meisten Programmiersprachen standardmäßig nicht versiegelt. Dies ist auch der empfohlene Standard für die meisten Klassen in Frameworks.</span><span class="sxs-lookup"><span data-stu-id="2cfd9-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="2cfd9-109">Die Erweiterbarkeit, die von nicht versiegelten Typen geboten wird, wird von frameworkbenutzern erheblich geschätzt und ist aufgrund relativ niedriger Testkosten, die mit nicht versiegelten Typen verbunden sind, sehr kostengünstig.</span><span class="sxs-lookup"><span data-stu-id="2cfd9-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>

 <span data-ttu-id="2cfd9-110">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="2cfd9-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2cfd9-111">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="2cfd9-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2cfd9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cfd9-112">See also</span></span>

- [<span data-ttu-id="2cfd9-113">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="2cfd9-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="2cfd9-114">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="2cfd9-114">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="2cfd9-115">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="2cfd9-115">Sealing</span></span>](sealing.md)
