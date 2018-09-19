---
title: Namen von Namespaces
ms.date: 03/30/2017
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d68966f60c5039fd67195a03facc1586b9ed154
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "45991271"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="350a7-102">Namen von Namespaces</span><span class="sxs-lookup"><span data-stu-id="350a7-102">Names of Namespaces</span></span>
<span data-ttu-id="350a7-103">Wie wird mit anderen Benennungsrichtlinien, das Ziel bei der Benennung von Namespaces erstellt ausreichend Klarheit für den Programmierer mit dem Framework sofort wissen, was der Inhalt des Namespace wahrscheinlich ist.</span><span class="sxs-lookup"><span data-stu-id="350a7-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="350a7-104">Die folgende Vorlage gibt die allgemeine Regel für die Benennung von Namespaces an:</span><span class="sxs-lookup"><span data-stu-id="350a7-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="350a7-105">Es folgen Beispiele für:</span><span class="sxs-lookup"><span data-stu-id="350a7-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="350a7-106">**✓ DO** Präfix Namespacenamen mit einem Firmennamen, um zu verhindern, dass Namespaces aus verschiedenen Unternehmen über den gleichen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="350a7-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="350a7-107">**✓ DO** ein stabiler, versionsunabhängige Produktname auf der zweiten Ebene eine Namespace-Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="350a7-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="350a7-108">**X DO NOT** Organisationseinheit Hierarchien für Namen in Namespacehierarchien, als Grundlage verwenden, da Gruppennamen in Unternehmen häufig kurzlebig sind.</span><span class="sxs-lookup"><span data-stu-id="350a7-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="350a7-109">Organisieren Sie die Hierarchie der Namespaces, um Gruppen von verwandten Technologien.</span><span class="sxs-lookup"><span data-stu-id="350a7-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="350a7-110">**✓ DO** PascalCasing und abgetrennten Namespacekomponenten mit Zeiträumen verwenden (z. B. `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="350a7-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="350a7-111">Wenn Ihre Marke zwar Groß-/Kleinschreibung verwendet, sollten Sie die Groß-/Kleinschreibung, Ihre Marke definiert folgen, selbst wenn es sich von normalen Namespace Groß-/Kleinschreibung abweicht.</span><span class="sxs-lookup"><span data-stu-id="350a7-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="350a7-112">**✓ CONSIDER** plural Namespacenamen verwenden, falls zutreffend.</span><span class="sxs-lookup"><span data-stu-id="350a7-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="350a7-113">Verwenden Sie z. B. `System.Collections` anstelle von `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="350a7-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="350a7-114">Markennamen und Akronyme sind jedoch Ausnahmen von dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="350a7-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="350a7-115">Verwenden Sie z. B. `System.IO` anstelle von `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="350a7-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="350a7-116">**X DO NOT** denselben Namen für einen Namespace und einen Typ in diesem Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="350a7-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="350a7-117">Verwenden Sie z. B. nicht `Debug` als Namespace benennen, und geben Sie dann auch eine Klasse namens `Debug` im selben Namespace.</span><span class="sxs-lookup"><span data-stu-id="350a7-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="350a7-118">Einige Compiler erfordern, dass solche Typen vollständig qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="350a7-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="350a7-119">Namespaces und Namenstypkonflikten</span><span class="sxs-lookup"><span data-stu-id="350a7-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="350a7-120">**X DO NOT** führen Sie die generischen Namen wie z. B. `Element`, `Node`, `Log`, und `Message`.</span><span class="sxs-lookup"><span data-stu-id="350a7-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="350a7-121">Es ist eine sehr hohe Wahrscheinlichkeit, dass dies zur Folge hat, geben Sie den Namen in gängigen Szenarien steht in Konflikt.</span><span class="sxs-lookup"><span data-stu-id="350a7-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="350a7-122">Sie sollten den Namen des generischen Typs zu qualifizieren (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="350a7-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="350a7-123">Es gibt bestimmte Richtlinien zum Vermeiden von namenstypkonflikten für verschiedene Kategorien von Namespaces.</span><span class="sxs-lookup"><span data-stu-id="350a7-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
-   <span data-ttu-id="350a7-124">**Application-Modell-namespaces**</span><span class="sxs-lookup"><span data-stu-id="350a7-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="350a7-125">Namespaces für ein einziges Anwendungsmodell werden sehr häufig zusammen verwendet werden, aber sie werden fast nie mit Namespaces anderer Modelle für die Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="350a7-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="350a7-126">Z. B. die <xref:System.Windows.Forms?displayProperty=nameWithType> -Namespace werden nur sehr selten zusammen mit den <xref:System.Web.UI?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="350a7-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="350a7-127">Im folgenden finden eine Liste der bekannten Modell Namespace Anwendungsgruppen:</span><span class="sxs-lookup"><span data-stu-id="350a7-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="350a7-128">**X DO NOT** weisen den gleichen Namen auf Typen in Namespaces in einem einzigen Anwendungsmodell.</span><span class="sxs-lookup"><span data-stu-id="350a7-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="350a7-129">Z. B. nicht auf einen Typ mit dem Namen hinzufügen `Page` auf die <xref:System.Web.UI.Adapters?displayProperty=nameWithType> -Namespace, da die <xref:System.Web.UI?displayProperty=nameWithType> -Namespace enthält bereits einen Typ namens `Page`.</span><span class="sxs-lookup"><span data-stu-id="350a7-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
-   <span data-ttu-id="350a7-130">**Infrastrukturnamespaces**</span><span class="sxs-lookup"><span data-stu-id="350a7-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="350a7-131">Diese Gruppe enthält die Namespaces, die nur selten während der Entwicklung häufig genutzte Anwendungen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="350a7-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="350a7-132">Z. B. `.Design` Namespaces werden hauptsächlich verwendet, wenn das tools entwickeln, Programmieren.</span><span class="sxs-lookup"><span data-stu-id="350a7-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="350a7-133">Vermeiden von Konflikten mit Typen aus den Namespaces ist unerheblich.</span><span class="sxs-lookup"><span data-stu-id="350a7-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
-   <span data-ttu-id="350a7-134">**Core-namespaces**</span><span class="sxs-lookup"><span data-stu-id="350a7-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="350a7-135">Core-Namespaces enthalten alle `System` Namespaces, mit Ausnahme von Namespaces der Anwendungsmodelle und die Infrastruktur-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="350a7-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="350a7-136">Core-Namespaces einschließen, u. a. `System`, `System.IO`, `System.Xml`, und `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="350a7-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="350a7-137">**X DO NOT** erteilen, die in Konflikt stehenden Namen mit einem beliebigen Typ in den Core-Namespaces Typen.</span><span class="sxs-lookup"><span data-stu-id="350a7-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="350a7-138">Verwenden Sie z. B. niemals `Stream` als Typname.</span><span class="sxs-lookup"><span data-stu-id="350a7-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="350a7-139">Es steht in Konflikt mit <xref:System.IO.Stream?displayProperty=nameWithType>, ein sehr häufig verwendete Typ.</span><span class="sxs-lookup"><span data-stu-id="350a7-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
-   <span data-ttu-id="350a7-140">**Technologie-Namespace-Gruppen**</span><span class="sxs-lookup"><span data-stu-id="350a7-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="350a7-141">Diese Kategorie enthält alle Namespaces mit den gleichen Namespaceknoten der ersten beiden `(<Company>.<Technology>*`), wie z. B. `Microsoft.Build.Utilities` und `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="350a7-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="350a7-142">Es ist wichtig, dass Typen, die auf eine einzelne Technologie gehören nicht miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="350a7-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="350a7-143">**X DO NOT** Typnamen, die in Konflikt stehen würde mit anderen Typen in einer einzelnen Technologie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="350a7-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="350a7-144">**X DO NOT** einführen Typnamenskonflikte zwischen Typen in Technologienamespaces und eine Anwendungsmodellnamespace (es sei denn, die Technologie nicht mit dem Anwendungsmodell verwendet werden sollen).</span><span class="sxs-lookup"><span data-stu-id="350a7-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="350a7-145">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="350a7-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="350a7-146">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="350a7-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350a7-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="350a7-147">See also</span></span>

- [<span data-ttu-id="350a7-148">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="350a7-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="350a7-149">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="350a7-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
