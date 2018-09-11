---
title: Attributes1
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51aa91b1acbae9f1a15ac12441090dd4c1c2dcb1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259491"
---
# <a name="attributes"></a><span data-ttu-id="64ec9-102">Attribute</span><span class="sxs-lookup"><span data-stu-id="64ec9-102">Attributes</span></span>
<span data-ttu-id="64ec9-103"><xref:System.Attribute?displayProperty=nameWithType> eine Basisklasse wird zum Definieren von benutzerdefinierter Attributen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64ec9-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="64ec9-104">Attribute sind Anmerkungen, die die Programmierelemente, z. B. Assemblys, Typen, Member und Parameter hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="64ec9-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="64ec9-105">Sie werden in den Metadaten der Assembly gespeichert und zur Laufzeit mithilfe der Reflektions-APIs zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="64ec9-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="64ec9-106">Das Framework definiert z. B. die <xref:System.ObsoleteAttribute>, die angewendet werden können, auf einen Typ oder ein Element aus, um anzugeben, dass der Typ oder Member veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="64ec9-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="64ec9-107">Attribute können eine oder mehrere Eigenschaften verfügen, die zusätzliche Daten, die im Zusammenhang mit der das Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="64ec9-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="64ec9-108">Z. B. `ObsoleteAttribute` könnte natürlich zusätzliche Informationen zu dieser Version in die ein Typ oder Member als veraltet markiert wurde und die Beschreibung der neuen APIs ersetzt die veraltete API.</span><span class="sxs-lookup"><span data-stu-id="64ec9-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="64ec9-109">Einige Eigenschaften eines Attributs müssen angegeben werden, wenn das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="64ec9-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="64ec9-110">Diese sind als die erforderlichen Eigenschaften oder die erforderlichen Argumente bezeichnet, da sie als Konstruktorparameter mit Feldern fester Breite dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="64ec9-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="64ec9-111">Z. B. die <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> Eigenschaft der <xref:System.Diagnostics.ConditionalAttribute> ist eine erforderliche Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="64ec9-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="64ec9-112">Eigenschaften, die nicht unbedingt angegeben werden, wenn das Attribut angewendet wird, werden optionale Eigenschaften (oder optionalen Argumenten) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="64ec9-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="64ec9-113">Sie werden durch festlegbaren Eigenschaften dargestellt.</span><span class="sxs-lookup"><span data-stu-id="64ec9-113">They are represented by settable properties.</span></span> <span data-ttu-id="64ec9-114">Compiler bieten speziellen Syntax zum Festlegen dieser Eigenschaften, wenn ein Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="64ec9-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="64ec9-115">Z. B. die <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> Eigenschaft darstellt, ein optionales Argument.</span><span class="sxs-lookup"><span data-stu-id="64ec9-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="64ec9-116">**✓ DO** benennen Sie benutzerdefinierte Attributklassen mit dem Suffix "-Attribut" an.</span><span class="sxs-lookup"><span data-stu-id="64ec9-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="64ec9-117">**✓ DO** gelten die <xref:System.AttributeUsageAttribute> zu benutzerdefinierten Attributen.</span><span class="sxs-lookup"><span data-stu-id="64ec9-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="64ec9-118">**✓ DO** festlegbare Eigenschaften bereitstellen, für die optionalen Argumente.</span><span class="sxs-lookup"><span data-stu-id="64ec9-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="64ec9-119">**✓ DO** nur Get-Eigenschaften für die erforderlichen Argumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="64ec9-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="64ec9-120">**✓ DO** Konstruktorparameter zum Initialisieren der Eigenschaften, die erforderlichen Argumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="64ec9-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="64ec9-121">Jeder Parameter muss den gleichen Namen (auch mit unterschiedlicher Groß-/Kleinschreibung) als die entsprechende Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="64ec9-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="64ec9-122">**X AVOID** Konstruktorparameter zum Initialisieren der Eigenschaften, die die optionalen Argumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="64ec9-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="64ec9-123">Das heißt, keine Eigenschaften, die mit einem Setter und einen Konstruktor festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="64ec9-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="64ec9-124">Diese Richtlinie ist sehr deutlich, welche Argumente optional sind und die erforderlich sind, und vermeidet zwei Möglichkeiten zum erledigen des gleiche.</span><span class="sxs-lookup"><span data-stu-id="64ec9-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="64ec9-125">**X AVOID** Überladen von Konstruktoren des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="64ec9-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="64ec9-126">Müssen nur über einen Konstruktor kommuniziert eindeutig für den Benutzer der Argumente erforderlich sind und welche optional sind.</span><span class="sxs-lookup"><span data-stu-id="64ec9-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="64ec9-127">**✓ DO** versiegeln Sie benutzerdefinierte Attributklassen, falls möglich.</span><span class="sxs-lookup"><span data-stu-id="64ec9-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="64ec9-128">Dies beschleunigt die Suche für das Attribut.</span><span class="sxs-lookup"><span data-stu-id="64ec9-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="64ec9-129">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="64ec9-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="64ec9-130">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="64ec9-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ec9-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64ec9-131">See also</span></span>

- [<span data-ttu-id="64ec9-132">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="64ec9-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="64ec9-133">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="64ec9-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
