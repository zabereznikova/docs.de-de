---
title: Namen von Namespaces
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bc298ad41884bfda84771a729990ebb4e6f776b7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="names-of-namespaces"></a><span data-ttu-id="1b538-102">Namen von Namespaces</span><span class="sxs-lookup"><span data-stu-id="1b538-102">Names of Namespaces</span></span>
<span data-ttu-id="1b538-103">Als ist mit anderen Benennungsrichtlinien das Ziel beim Benennen von Namespaces erstellen ausreichend Klarheit für Programmierer, die mithilfe des Frameworks sofort zu wissen, was der Inhalt des Namespaces wahrscheinlich ist.</span><span class="sxs-lookup"><span data-stu-id="1b538-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="1b538-104">Die folgende Vorlage gibt an, die in der Regel für die Benennung von Namespaces:</span><span class="sxs-lookup"><span data-stu-id="1b538-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="1b538-105">Es folgen Beispiele für:</span><span class="sxs-lookup"><span data-stu-id="1b538-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="1b538-106">**Führen Sie ✓** Präfix Namespacenamen mit einem Firmennamen, um zu verhindern, dass Namespaces aus verschiedenen Unternehmen über den gleichen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="1b538-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="1b538-107">**Führen Sie ✓** ein stabiler, versionsunabhängige Produktname auf der zweiten Ebene eine Namespace-Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b538-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="1b538-108">**X nicht** Organisationseinheit Hierarchien für Namen in Namespacehierarchien, als Grundlage verwenden, da Gruppennamen in Unternehmen häufig kurzlebig sind.</span><span class="sxs-lookup"><span data-stu-id="1b538-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="1b538-109">Organisieren Sie die Hierarchie von Namespaces, um Gruppen von verwandten Technologien.</span><span class="sxs-lookup"><span data-stu-id="1b538-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="1b538-110">**Führen Sie ✓** PascalCasing und abgetrennten Namespacekomponenten mit Zeiträumen verwenden (z. B. `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="1b538-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="1b538-111">Wenn Ihre Marke traditionelle Groß-/Kleinschreibung verwendet, sollten Sie die Groß-/Kleinschreibung definiert Ihre Marke folgen, selbst wenn er von der normalen Namespace Groß-/Kleinschreibung abweicht.</span><span class="sxs-lookup"><span data-stu-id="1b538-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="1b538-112">**✓ GGF.** plural Namespacenamen verwenden, falls zutreffend.</span><span class="sxs-lookup"><span data-stu-id="1b538-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="1b538-113">Verwenden Sie z. B. `System.Collections` anstelle von `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="1b538-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="1b538-114">Markennamen und Akronyme sind jedoch Ausnahmen von dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="1b538-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="1b538-115">Verwenden Sie z. B. `System.IO` anstelle von `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="1b538-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="1b538-116">**X nicht** denselben Namen für einen Namespace und einen Typ in diesem Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b538-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="1b538-117">Verwenden Sie z. B. nicht `Debug` wie ein Namespace benennen, und geben Sie dann auch eine Klasse namens `Debug` im selben Namespace.</span><span class="sxs-lookup"><span data-stu-id="1b538-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="1b538-118">Einige Compiler erfordern, dass solche Typen vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="1b538-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="1b538-119">Namespaces und Typnamenskonflikte</span><span class="sxs-lookup"><span data-stu-id="1b538-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="1b538-120">**X nicht** führen Sie die generischen Namen wie z. B. `Element`, `Node`, `Log`, und `Message`.</span><span class="sxs-lookup"><span data-stu-id="1b538-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="1b538-121">Es ist ein sehr hoher Wahrscheinlichkeit, dass dies hätte, führen um zu eingeben gemeinsame Szenarien steht in Konflikt.</span><span class="sxs-lookup"><span data-stu-id="1b538-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="1b538-122">Sie sollten die generischen Namen qualifizieren (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="1b538-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="1b538-123">Es gibt spezielle Richtlinien für die Typ-Namenskonflikte für verschiedene Kategorien von Namespaces zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="1b538-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
-   <span data-ttu-id="1b538-124">**Application-Modell-namespaces**</span><span class="sxs-lookup"><span data-stu-id="1b538-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="1b538-125">Namespaces, gehören zu einem einzelnen Anwendungsmodell werden häufig zusammen verwendet werden, aber sie fast nie mit Namespaces anderer Modelle der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b538-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="1b538-126">Z. B. die <xref:System.Windows.Forms?displayProperty=nameWithType> Namespace wird sehr selten verwendet werden, zusammen mit den <xref:System.Web.UI?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="1b538-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="1b538-127">Im folgenden finden eine Liste der bekannten Anwendung Namespace Modellgruppen:</span><span class="sxs-lookup"><span data-stu-id="1b538-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="1b538-128">**X nicht** weisen den gleichen Namen auf Typen in Namespaces in einem einzigen Anwendungsmodell.</span><span class="sxs-lookup"><span data-stu-id="1b538-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="1b538-129">Z. B. einen Typ mit dem Namen nicht hinzufügen `Page` auf die <xref:System.Web.UI.Adapters?displayProperty=nameWithType> Namespace, da die <xref:System.Web.UI?displayProperty=nameWithType> -Namespace enthält bereits einen Typ mit dem Namen `Page`.</span><span class="sxs-lookup"><span data-stu-id="1b538-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
-   <span data-ttu-id="1b538-130">**Infrastrukturnamespaces**</span><span class="sxs-lookup"><span data-stu-id="1b538-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="1b538-131">Diese Gruppe enthält die Namespaces, die nur selten während der Entwicklung der Anwendung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="1b538-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="1b538-132">Beispielsweise `.Design` Namespaces werden hauptsächlich verwendet, bei der Entwicklung, Programmierung tools.</span><span class="sxs-lookup"><span data-stu-id="1b538-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="1b538-133">Vermeiden von Konflikten mit Typen aus den Namespaces ist unerheblich.</span><span class="sxs-lookup"><span data-stu-id="1b538-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
-   <span data-ttu-id="1b538-134">**Core-namespaces**</span><span class="sxs-lookup"><span data-stu-id="1b538-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="1b538-135">Core-Namespaces enthalten alle `System` Namespaces, die ausschließlich Namespaces und die Anwendungsmodelle und der Infrastruktur-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="1b538-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="1b538-136">Core-Namespaces enthalten, u. a. `System`, `System.IO`, `System.Xml`, und `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="1b538-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="1b538-137">**X nicht** erteilen, die in Konflikt stehenden Namen mit einem beliebigen Typ in den Core-Namespaces Typen.</span><span class="sxs-lookup"><span data-stu-id="1b538-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="1b538-138">Verwenden Sie z. B. niemals `Stream` als Typname.</span><span class="sxs-lookup"><span data-stu-id="1b538-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="1b538-139">Es steht in Konflikt mit <xref:System.IO.Stream?displayProperty=nameWithType>, eine sehr häufig verwendete Typ.</span><span class="sxs-lookup"><span data-stu-id="1b538-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
-   <span data-ttu-id="1b538-140">**Technologie Namespace Gruppen**</span><span class="sxs-lookup"><span data-stu-id="1b538-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="1b538-141">Diese Kategorie umfasst alle Namespaces mit den gleichen ersten beiden Namespaceknoten `(<Company>.<Technology>*`), wie z. B. `Microsoft.Build.Utilities` und `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="1b538-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="1b538-142">Es ist wichtig, dass Typen, die auf eine einzelne Technologie gehören nicht miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="1b538-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="1b538-143">**X nicht** Typnamen, die in Konflikt stehen würde mit anderen Typen in einer einzelnen Technologie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1b538-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="1b538-144">**X nicht** einführen Typnamenskonflikte zwischen Typen in Technologienamespaces und eine Anwendungsmodellnamespace (es sei denn, die Technologie nicht mit dem Anwendungsmodell verwendet werden sollen).</span><span class="sxs-lookup"><span data-stu-id="1b538-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="1b538-145">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="1b538-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1b538-146">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="1b538-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b538-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b538-147">See Also</span></span>  
 [<span data-ttu-id="1b538-148">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1b538-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="1b538-149">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="1b538-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
