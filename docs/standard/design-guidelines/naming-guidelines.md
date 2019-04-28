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
author: KrzysztofCwalina
ms.openlocfilehash: 4c7f411bdf538762de18873007c839f66911f96a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757260"
---
# <a name="naming-guidelines"></a><span data-ttu-id="69b13-102">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="69b13-102">Naming Guidelines</span></span>
<span data-ttu-id="69b13-103">Befolgen einen konsistenten Satz von Benennungskonventionen in die Entwicklung eines Frameworks kann einen wichtigen Beitrag zum die Framework benutzerfreundlichkeit sein.</span><span class="sxs-lookup"><span data-stu-id="69b13-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="69b13-104">Sie können das Framework von vielen Entwicklern häufig separate Projekte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69b13-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="69b13-105">Über die Konsistenz des Formulars Namen von Frameworkelementen leicht verstanden werden müssen und müssen die Funktion jedes Elements zu vermitteln.</span><span class="sxs-lookup"><span data-stu-id="69b13-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="69b13-106">Das Ziel dieses Kapitels ist einen konsistenten Satz von Benennungskonventionen angeben, der Namen, die sofortige für Entwickler sinnvoll ergeben.</span><span class="sxs-lookup"><span data-stu-id="69b13-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="69b13-107">Obwohl diese Namenskonventionen übernehmen, da Richtlinien für die Entwicklung von allgemeinen Code führen würde, konsistente Benennung im gesamten Code, Sie sind nur erforderlich, um diese APIs gelten, die öffentlich verfügbar gemacht werden (öffentliche oder geschützte Typen und Member, und explizit implementierte Schnittstellen).</span><span class="sxs-lookup"><span data-stu-id="69b13-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69b13-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="69b13-108">In This Section</span></span>  
 [<span data-ttu-id="69b13-109">Konventionen für die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="69b13-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="69b13-110">Allgemeine Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="69b13-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="69b13-111">Namen von Assemblys und DLLs</span><span class="sxs-lookup"><span data-stu-id="69b13-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="69b13-112">Namen von Namespaces</span><span class="sxs-lookup"><span data-stu-id="69b13-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="69b13-113">Namen von Klassen, Strukturen und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="69b13-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="69b13-114">Namen von Typmembern</span><span class="sxs-lookup"><span data-stu-id="69b13-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="69b13-115">Benennen von Parametern</span><span class="sxs-lookup"><span data-stu-id="69b13-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="69b13-116">Benennen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="69b13-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="69b13-117">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="69b13-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="69b13-118">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="69b13-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b13-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69b13-119">See also</span></span>

- [<span data-ttu-id="69b13-120">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="69b13-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
