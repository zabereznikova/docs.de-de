---
title: Richtlinien für die Benennung
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
ms.openlocfilehash: 1b137be60f4c8c1c7cf1fa1f807841d4bc209089
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290174"
---
# <a name="naming-guidelines"></a><span data-ttu-id="c7776-102">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="c7776-102">Naming Guidelines</span></span>
<span data-ttu-id="c7776-103">Das befolgen eines konsistenten Satzes von Benennungs Konventionen in der Entwicklung eines Frameworks kann ein wesentlicher Beitrag zur Benutzerfreundlichkeit des Frameworks sein.</span><span class="sxs-lookup"><span data-stu-id="c7776-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="c7776-104">Sie ermöglicht es, dass das Framework von vielen Entwicklern für umfassend getrennte Projekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7776-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="c7776-105">Neben der Konsistenz der Form müssen die Namen von Frameworkelementen leicht verständlich sein und die Funktion der einzelnen Elemente vermitteln.</span><span class="sxs-lookup"><span data-stu-id="c7776-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="c7776-106">Das Ziel dieses Kapitels besteht darin, einen konsistenten Satz von Benennungs Konventionen bereitzustellen, die zu Namen führen, die für die Entwickler von unmittelbarem Sinn machen.</span><span class="sxs-lookup"><span data-stu-id="c7776-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="c7776-107">Obwohl die Übernahme dieser Benennungs Konventionen als allgemeine Richtlinien für die Code Entwicklung zu einer konsistenten Benennung im gesamten Code führen würde, müssen Sie Sie nur auf APIs anwenden, die öffentlich verfügbar gemacht werden (öffentliche oder geschützte Typen und Member sowie explizit implementierte Schnittstellen).</span><span class="sxs-lookup"><span data-stu-id="c7776-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7776-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c7776-108">In This Section</span></span>  
 [<span data-ttu-id="c7776-109">Konventionen für groß Schreibung</span><span class="sxs-lookup"><span data-stu-id="c7776-109">Capitalization Conventions</span></span>](capitalization-conventions.md)  
 [<span data-ttu-id="c7776-110">Allgemeine Benennungs Konventionen</span><span class="sxs-lookup"><span data-stu-id="c7776-110">General Naming Conventions</span></span>](general-naming-conventions.md)  
 [<span data-ttu-id="c7776-111">Namen von Assemblys und DLLs</span><span class="sxs-lookup"><span data-stu-id="c7776-111">Names of Assemblies and DLLs</span></span>](names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="c7776-112">Namen von Namespaces</span><span class="sxs-lookup"><span data-stu-id="c7776-112">Names of Namespaces</span></span>](names-of-namespaces.md)  
 [<span data-ttu-id="c7776-113">Namen von Klassen, Strukturen und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c7776-113">Names of Classes, Structs, and Interfaces</span></span>](names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="c7776-114">Namen von Typmembern</span><span class="sxs-lookup"><span data-stu-id="c7776-114">Names of Type Members</span></span>](names-of-type-members.md)  
 [<span data-ttu-id="c7776-115">Benennungs Parameter</span><span class="sxs-lookup"><span data-stu-id="c7776-115">Naming Parameters</span></span>](naming-parameters.md)  
 [<span data-ttu-id="c7776-116">Benennen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c7776-116">Naming Resources</span></span>](naming-resources.md)  
 <span data-ttu-id="c7776-117">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="c7776-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c7776-118">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="c7776-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7776-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7776-119">See also</span></span>

- [<span data-ttu-id="c7776-120">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="c7776-120">Framework Design Guidelines</span></span>](index.md)
