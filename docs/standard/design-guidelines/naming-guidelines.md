---
title: Richtlinien für die Benennung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 91b392c2fe895499b9da83cfd773edb1128a429b
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="naming-guidelines"></a><span data-ttu-id="84776-102">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="84776-102">Naming Guidelines</span></span>
<span data-ttu-id="84776-103">Befolgen konsistente Benennungskonventionen in die Entwicklung von einem Framework kann einen wesentlichen Beitrag das Framework verwendbarkeits-sein.</span><span class="sxs-lookup"><span data-stu-id="84776-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="84776-104">Es kann das Framework weit getrennte Projekte für viele Entwickler verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84776-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="84776-105">Über die Konsistenz des Formulars Namen von Frameworkelemente leicht verstanden werden müssen und müssen die Funktion der einzelnen Elemente zu vermitteln.</span><span class="sxs-lookup"><span data-stu-id="84776-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="84776-106">Das Ziel dieses Kapitels ist konsistente Benennungskonventionen angeben, die sich im Namen ergibt, die sofortige für Entwickler sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="84776-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="84776-107">Obwohl diese Benennungskonventionen einführen, da mit Richtlinien für die allgemeine Entwicklung konsistenter Benennung im gesamten Code führen würde, Sie sind nur erforderlich, um deren Anwendung auf APIs an, die öffentlich verfügbar gemacht werden (öffentliche oder geschützte Typen und Member, und explizit implementierte Schnittstellen).</span><span class="sxs-lookup"><span data-stu-id="84776-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84776-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="84776-108">In This Section</span></span>  
 [<span data-ttu-id="84776-109">Konventionen für die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="84776-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="84776-110">Allgemeine Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="84776-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="84776-111">Namen von Assemblys und DLLs</span><span class="sxs-lookup"><span data-stu-id="84776-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="84776-112">Namen von Namespaces</span><span class="sxs-lookup"><span data-stu-id="84776-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="84776-113">Namen von Klassen, Strukturen und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="84776-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="84776-114">Namen von Typmembern</span><span class="sxs-lookup"><span data-stu-id="84776-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="84776-115">Benennen von Parametern</span><span class="sxs-lookup"><span data-stu-id="84776-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="84776-116">Benennen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="84776-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="84776-117">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="84776-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="84776-118">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="84776-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84776-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84776-119">See Also</span></span>  
 [<span data-ttu-id="84776-120">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="84776-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
