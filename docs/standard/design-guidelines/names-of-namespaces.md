---
title: Namen von Namespaces
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 52fee0dfaff284c2c1a6afcb8aa7530c28a60d65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744143"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="2944c-102">Namen von Namespaces</span><span class="sxs-lookup"><span data-stu-id="2944c-102">Names of Namespaces</span></span>
<span data-ttu-id="2944c-103">Wie bei anderen Benennungs Richtlinien ist das Ziel bei der Benennung von Namespaces, dass der Programmierer, der das Framework verwendet, ausreichend Klarheit schafft, um sofort zu wissen, welcher Inhalt des Namespace wahrscheinlich ist.</span><span class="sxs-lookup"><span data-stu-id="2944c-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="2944c-104">Die folgende Vorlage gibt die allgemeine Regel für das Benennen von Namespaces an:</span><span class="sxs-lookup"><span data-stu-id="2944c-104">The following template specifies the general rule for naming namespaces:</span></span>

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 <span data-ttu-id="2944c-105">Im folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2944c-105">The following are examples:</span></span>

 <span data-ttu-id="2944c-106">`Fabrikam.Math` `Litware.Security`</span><span class="sxs-lookup"><span data-stu-id="2944c-106">`Fabrikam.Math` `Litware.Security`</span></span>

 <span data-ttu-id="2944c-107">✔️ Namen von Namespace Namen mit einem Firmennamen zu versehen, um zu verhindern, dass Namespaces von unterschiedlichen Unternehmen denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="2944c-107">✔️ DO prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>

 <span data-ttu-id="2944c-108">✔️ verwenden einen stabilen, Versions unabhängigen Produktnamen auf der zweiten Ebene eines Namespace namens.</span><span class="sxs-lookup"><span data-stu-id="2944c-108">✔️ DO use a stable, version-independent product name at the second level of a namespace name.</span></span>

 <span data-ttu-id="2944c-109">❌ verwenden keine Organisations Hierarchien als Grundlage für Namen in Namespace Hierarchien, da Gruppennamen in Unternehmen tendenziell kurzlebig sind.</span><span class="sxs-lookup"><span data-stu-id="2944c-109">❌ DO NOT use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="2944c-110">Organisieren Sie die Hierarchie von Namespaces um Gruppen verwandter Technologien.</span><span class="sxs-lookup"><span data-stu-id="2944c-110">Organize the hierarchy of namespaces around groups of related technologies.</span></span>

 <span data-ttu-id="2944c-111">✔️ eine Pass-/Schreibweise verwenden, und trennen Sie Namespace Komponenten mit Zeiträumen (z. b. `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="2944c-111">✔️ DO use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="2944c-112">Wenn Ihre Marke nicht herkömmliche Schreibweise verwendet, sollten Sie die von Ihrer Marke definierte Groß-/Kleinschreibung befolgen, auch wenn Sie von der normalen Namespace-Schreibweise abweicht.</span><span class="sxs-lookup"><span data-stu-id="2944c-112">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>

 <span data-ttu-id="2944c-113">✔️ sollten Sie ggf. Plural Namespace Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2944c-113">✔️ CONSIDER using plural namespace names where appropriate.</span></span>

 <span data-ttu-id="2944c-114">Verwenden Sie z. B. `System.Collections` statt `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="2944c-114">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="2944c-115">Markennamen und Akronyme sind jedoch Ausnahmen für diese Regel.</span><span class="sxs-lookup"><span data-stu-id="2944c-115">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="2944c-116">Verwenden Sie z. B. `System.IO` statt `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="2944c-116">For example, use `System.IO` instead of `System.IOs`.</span></span>

 <span data-ttu-id="2944c-117">❌ nicht denselben Namen für einen Namespace und einen Typ in diesem Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="2944c-117">❌ DO NOT use the same name for a namespace and a type in that namespace.</span></span>

 <span data-ttu-id="2944c-118">Verwenden Sie z. b. `Debug` nicht als Namespace Namen, und stellen Sie dann auch eine Klasse mit dem Namen `Debug` im gleichen Namespace bereit.</span><span class="sxs-lookup"><span data-stu-id="2944c-118">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="2944c-119">Mehrere Compiler erfordern, dass solche Typen voll qualifiziert sind.</span><span class="sxs-lookup"><span data-stu-id="2944c-119">Several compilers require such types to be fully qualified.</span></span>

### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="2944c-120">Namespaces und Typnamen Konflikte</span><span class="sxs-lookup"><span data-stu-id="2944c-120">Namespaces and Type Name Conflicts</span></span>
 <span data-ttu-id="2944c-121">❌ führen keine generischen Typnamen wie `Element`, `Node`, `Log`und `Message`ein.</span><span class="sxs-lookup"><span data-stu-id="2944c-121">❌ DO NOT introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>

 <span data-ttu-id="2944c-122">Es gibt eine sehr hohe Wahrscheinlichkeit, dass dies zu Typnamens Konflikten in gängigen Szenarien führt.</span><span class="sxs-lookup"><span data-stu-id="2944c-122">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="2944c-123">Sie sollten die generischen Typnamen (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`) qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="2944c-123">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>

 <span data-ttu-id="2944c-124">Es gibt spezielle Richtlinien zum Vermeiden von Typnamens Konflikten für verschiedene Namespaces-Kategorien.</span><span class="sxs-lookup"><span data-stu-id="2944c-124">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>

- <span data-ttu-id="2944c-125">**Namespaces des Anwendungs Modells**</span><span class="sxs-lookup"><span data-stu-id="2944c-125">**Application model namespaces**</span></span>

     <span data-ttu-id="2944c-126">Namespaces, die zu einem einzelnen Anwendungsmodell gehören, werden häufig zusammen verwendet, aber Sie werden fast nie mit Namespaces anderer Anwendungsmodelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="2944c-126">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="2944c-127">Beispielsweise wird der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace sehr selten in Verbindung mit dem <xref:System.Web.UI?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="2944c-127">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="2944c-128">Im folgenden finden Sie eine Liste bekannter Anwendungsmodell-Namespace Gruppen:</span><span class="sxs-lookup"><span data-stu-id="2944c-128">The following is a list of well-known application model namespace groups:</span></span>

     <span data-ttu-id="2944c-129">`System.Windows*` `System.Web.UI*`</span><span class="sxs-lookup"><span data-stu-id="2944c-129">`System.Windows*` `System.Web.UI*`</span></span>

     <span data-ttu-id="2944c-130">❌ nicht denselben Namen für Typen in Namespaces innerhalb eines einzelnen Anwendungs Modells.</span><span class="sxs-lookup"><span data-stu-id="2944c-130">❌ DO NOT give the same name to types in namespaces within a single application model.</span></span>

     <span data-ttu-id="2944c-131">Fügen Sie z. b. dem <xref:System.Web.UI.Adapters?displayProperty=nameWithType>-Namespace keinen Typ mit dem Namen `Page` hinzu, da der <xref:System.Web.UI?displayProperty=nameWithType>-Namespace bereits einen Typ mit dem Namen `Page`enthält.</span><span class="sxs-lookup"><span data-stu-id="2944c-131">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>

- <span data-ttu-id="2944c-132">**Infrastructure-Namespaces**</span><span class="sxs-lookup"><span data-stu-id="2944c-132">**Infrastructure namespaces**</span></span>

     <span data-ttu-id="2944c-133">Diese Gruppe enthält Namespaces, die nur selten während der Entwicklung allgemeiner Anwendungen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="2944c-133">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="2944c-134">`.Design`-Namespaces werden z. b. hauptsächlich zum Entwickeln von Programmier Tools verwendet.</span><span class="sxs-lookup"><span data-stu-id="2944c-134">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="2944c-135">Es ist nicht wichtig, Konflikte mit Typen in diesen Namespaces zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2944c-135">Avoiding conflicts with types in these namespaces is not critical.</span></span>

- <span data-ttu-id="2944c-136">**Kernnamespaces**</span><span class="sxs-lookup"><span data-stu-id="2944c-136">**Core namespaces**</span></span>

     <span data-ttu-id="2944c-137">Kernnamespaces enthalten alle `System` Namespaces, ausgenommen Namespaces der Anwendungsmodelle und der Infrastructure-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="2944c-137">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="2944c-138">Zu den Kernnamespaces zählen unter anderem `System`, `System.IO`, `System.Xml`und `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="2944c-138">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>

     <span data-ttu-id="2944c-139">❌ geben keine Namen für Typen an, die mit einem beliebigen Typ in den Kernnamespaces in Konflikt stehen würden.</span><span class="sxs-lookup"><span data-stu-id="2944c-139">❌ DO NOT give types names that would conflict with any type in the Core namespaces.</span></span>

     <span data-ttu-id="2944c-140">Verwenden Sie z. b. niemals `Stream` als Typnamen.</span><span class="sxs-lookup"><span data-stu-id="2944c-140">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="2944c-141">Es würde zu einem Konflikt mit <xref:System.IO.Stream?displayProperty=nameWithType>, einem sehr häufig verwendeten Typ, kommen.</span><span class="sxs-lookup"><span data-stu-id="2944c-141">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>

- <span data-ttu-id="2944c-142">**Technologie-Namespace Gruppen**</span><span class="sxs-lookup"><span data-stu-id="2944c-142">**Technology namespace groups**</span></span>

     <span data-ttu-id="2944c-143">Diese Kategorie enthält alle Namespaces mit denselben ersten zwei Namespace Knoten `(<Company>.<Technology>*`), z. b. `Microsoft.Build.Utilities` und `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="2944c-143">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="2944c-144">Es ist wichtig, dass Typen, die zu einer einzelnen Technologie gehören, nicht miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="2944c-144">It is important that types belonging to a single technology do not conflict with each other.</span></span>

     <span data-ttu-id="2944c-145">❌ weisen keine Typnamen zu, die mit anderen Typen in einer einzelnen Technologie in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="2944c-145">❌ DO NOT assign type names that would conflict with other types within a single technology.</span></span>

     <span data-ttu-id="2944c-146">in ❌ werden keine Typnamen Konflikte zwischen Typen in Technologie Namespaces und einem Anwendungsmodell-Namespace eingeführt (es sei denn, die Technologie ist nicht für die Verwendung mit dem Anwendungsmodell vorgesehen).</span><span class="sxs-lookup"><span data-stu-id="2944c-146">❌ DO NOT introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>

 <span data-ttu-id="2944c-147">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="2944c-147">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2944c-148">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="2944c-148">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2944c-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2944c-149">See also</span></span>

- [<span data-ttu-id="2944c-150">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2944c-150">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="2944c-151">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="2944c-151">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
