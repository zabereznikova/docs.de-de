---
title: Attributes1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86fa2556e6b8fb82e31a7d4753354aa2dff627ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="attributes"></a><span data-ttu-id="2cb55-102">Attribute</span><span class="sxs-lookup"><span data-stu-id="2cb55-102">Attributes</span></span>
<span data-ttu-id="2cb55-103"><xref:System.Attribute?displayProperty=nameWithType>eine Basisklasse wird zum Definieren von benutzerdefinierter Attributen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2cb55-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="2cb55-104">Attribute sind Anmerkungen, die um Programmierelemente wie Assemblys, Typen, Member und Parameter hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="2cb55-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="2cb55-105">Sie werden in den Metadaten der Assembly gespeichert und zur Laufzeit mit der Reflektions-APIs zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="2cb55-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="2cb55-106">Das Framework definiert z. B. die <xref:System.ObsoleteAttribute>, die auf einen Typ oder ein Element aus, um anzugeben, dass der Typ oder Member veraltet ist angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2cb55-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="2cb55-107">Attribute können eine oder mehrere Eigenschaften aufweisen, die zusätzliche Daten, die im Zusammenhang mit dem Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="2cb55-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="2cb55-108">Beispielsweise `ObsoleteAttribute` konnte enthalten zusätzliche Informationen über die Freigabe in der ein Typ oder Member veraltet erhalten haben und die Beschreibung der neuen APIs ersetzt die veraltete API.</span><span class="sxs-lookup"><span data-stu-id="2cb55-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="2cb55-109">Einige Eigenschaften eines Attributs müssen angegeben werden, wenn das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cb55-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="2cb55-110">Diese sind als die erforderlichen Eigenschaften oder die erforderlichen Argumente bezeichnet, da sie als Konstruktorparameter mit Feldern fester Breite dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2cb55-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="2cb55-111">Z. B. die <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> Eigenschaft von der <xref:System.Diagnostics.ConditionalAttribute> ist eine erforderliche Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2cb55-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="2cb55-112">Eigenschaften, die nicht unbedingt angegeben werden, wenn das Attribut angewendet wird, werden optionale Eigenschaften (oder optionale Argumente) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2cb55-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="2cb55-113">Sie werden durch festlegbaren Eigenschaften dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2cb55-113">They are represented by settable properties.</span></span> <span data-ttu-id="2cb55-114">Compiler bieten spezielle Syntax, um diese Eigenschaften festzulegen, wenn ein Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cb55-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="2cb55-115">Z. B. die <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> Eigenschaft darstellt, ein optionales Argument.</span><span class="sxs-lookup"><span data-stu-id="2cb55-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="2cb55-116">**Führen Sie ✓** benennen Sie benutzerdefinierte Attributklassen mit dem Suffix "-Attribut" an.</span><span class="sxs-lookup"><span data-stu-id="2cb55-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="2cb55-117">**Führen Sie ✓** gelten die <xref:System.AttributeUsageAttribute> zu benutzerdefinierten Attributen.</span><span class="sxs-lookup"><span data-stu-id="2cb55-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="2cb55-118">**Führen Sie ✓** festlegbare Eigenschaften bereitstellen, für die optionalen Argumente.</span><span class="sxs-lookup"><span data-stu-id="2cb55-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="2cb55-119">**Führen Sie ✓** nur Get-Eigenschaften für die erforderlichen Argumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2cb55-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="2cb55-120">**Führen Sie ✓** Konstruktorparameter zum Initialisieren der Eigenschaften, die erforderlichen Argumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2cb55-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="2cb55-121">Jeder Parameter muss den gleichen Namen (obwohl mit abweichender Groß-/Kleinschreibung) als die entsprechende Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="2cb55-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="2cb55-122">**X vermeiden** Konstruktorparameter zum Initialisieren der Eigenschaften, die die optionalen Argumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2cb55-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="2cb55-123">Das heißt, keine Eigenschaften, die mit einem Konstruktor und einen Setter festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="2cb55-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="2cb55-124">Diese Richtlinie stellt sehr explizite, welche Argumente optional sind und die erforderlich sind, und vermeidet zwei Möglichkeiten, auf diese Weise dieselbe Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="2cb55-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="2cb55-125">**X vermeiden** Überladen von Konstruktoren des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="2cb55-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="2cb55-126">Nur über einen Konstruktor mit kommuniziert eindeutig für den Benutzer die Argumente erforderlich sind und welche optional sind.</span><span class="sxs-lookup"><span data-stu-id="2cb55-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="2cb55-127">**Führen Sie ✓** versiegeln Sie benutzerdefinierte Attributklassen, falls möglich.</span><span class="sxs-lookup"><span data-stu-id="2cb55-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="2cb55-128">Dies beschleunigt die Suchregeln für das Attribut.</span><span class="sxs-lookup"><span data-stu-id="2cb55-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="2cb55-129">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="2cb55-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2cb55-130">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="2cb55-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb55-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cb55-131">See Also</span></span>  
 [<span data-ttu-id="2cb55-132">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2cb55-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="2cb55-133">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2cb55-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
