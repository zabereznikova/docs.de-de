---
title: Geschützte Member
ms.date: 10/22/2008
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: 3cc2ab3e605cfb5382f107dead0c95495858fc6b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828724"
---
# <a name="protected-members"></a><span data-ttu-id="51b4a-102">Geschützte Member</span><span class="sxs-lookup"><span data-stu-id="51b4a-102">Protected Members</span></span>
<span data-ttu-id="51b4a-103">Geschützte Member selbst bieten keine Erweiterbarkeit, Sie können jedoch die Erweiterbarkeit durch Unterklassen erhöhen.</span><span class="sxs-lookup"><span data-stu-id="51b4a-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="51b4a-104">Sie können verwendet werden, um erweiterte Anpassungsoptionen verfügbar zu machen, ohne die öffentliche Hauptschnittstelle unnötig zu verkomplizieren.</span><span class="sxs-lookup"><span data-stu-id="51b4a-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>

 <span data-ttu-id="51b4a-105">Frameworkdesigner müssen mit geschützten Membern vorsichtig sein, da der Name "Protected" eine falsche Sicherheit bietet.</span><span class="sxs-lookup"><span data-stu-id="51b4a-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="51b4a-106">Jeder ist in der Lage, eine nicht versiegelte Klasse zu unterteilen und auf geschützte Member zuzugreifen. Daher gelten dieselben Verteidigungsmethoden, die für öffentliche Member verwendet werden, für geschützte Member.</span><span class="sxs-lookup"><span data-stu-id="51b4a-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>

 <span data-ttu-id="51b4a-107">✔️ sollten Sie die Verwendung geschützter Member für erweiterte Anpassungen in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="51b4a-107">✔️ CONSIDER using protected members for advanced customization.</span></span>

 <span data-ttu-id="51b4a-108">✔️ werden geschützte Member in nicht versiegelten Klassen als öffentlich für den Zweck der Sicherheits-, Dokumentations-und Kompatibilitäts Analyse behandelt.</span><span class="sxs-lookup"><span data-stu-id="51b4a-108">✔️ DO treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>

 <span data-ttu-id="51b4a-109">Jeder kann von einer Klasse erben und auf die geschützten Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="51b4a-109">Anyone can inherit from a class and access the protected members.</span></span>

 <span data-ttu-id="51b4a-110">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="51b4a-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="51b4a-111">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="51b4a-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="51b4a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51b4a-112">See also</span></span>

- [<span data-ttu-id="51b4a-113">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="51b4a-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="51b4a-114">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="51b4a-114">Designing for Extensibility</span></span>](designing-for-extensibility.md)
