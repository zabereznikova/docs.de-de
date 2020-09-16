---
title: Sicherheitstransparenter Code, Ebene 2
description: Verstehen Sie den transparenten Code der Ebene 2. Weitere Informationen finden Sie unter Verwendungs Beispiele und Verhalten, außer Kraft setzen von Mustern, Vererbungs Regeln und mehr.
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
ms.openlocfilehash: bbff7b53bacd50746de56c8dba85cdc9e4b1ad9b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556407"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="d4c19-104">Sicherheitstransparenter Code, Ebene 2</span><span class="sxs-lookup"><span data-stu-id="d4c19-104">Security-Transparent Code, Level 2</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="d4c19-105">Transparenz der Ebene 2 wurde in der .NET Framework 4 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-105">Level 2 transparency was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="d4c19-106">Die drei Grundsätze dieses Modells sind transparenter Code, sicherheitsgeschützter Code und sicherheitskritischer Code.</span><span class="sxs-lookup"><span data-stu-id="d4c19-106">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="d4c19-107">Transparenter Code, einschließlich Code, der mit voller Vertrauenswürdigkeit ausgeführt wird, kann anderen transparenten Code oder sicherheitsgeschützten Code nur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d4c19-107">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="d4c19-108">Er kann nur Aktionen durchführen, die von der domänenspezifischen Berechtigungseinstellung für teilweise Vertrauenswürdigkeit zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="d4c19-108">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="d4c19-109">Transparenter Code ist nicht für die folgenden Vorgänge vorgesehen:</span><span class="sxs-lookup"><span data-stu-id="d4c19-109">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="d4c19-110">Ausführen eines <xref:System.Security.CodeAccessPermission.Assert%2A>-Vorgangs oder einer Berechtigungserweiterung.</span><span class="sxs-lookup"><span data-stu-id="d4c19-110">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="d4c19-111">Der Code darf keinen unsicheren oder nicht überprüfbaren Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4c19-111">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="d4c19-112">Direktes Aufrufen von wichtigem Code.</span><span class="sxs-lookup"><span data-stu-id="d4c19-112">Directly call critical code.</span></span>

  - <span data-ttu-id="d4c19-113">Aufrufen von systemeigenen Code oder von Code mit dem <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="d4c19-113">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="d4c19-114">Aufrufen eines Members, der von einem <xref:System.Security.Permissions.SecurityAction.LinkDemand>-Feld geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="d4c19-114">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="d4c19-115">Erben von wichtigen Typen.</span><span class="sxs-lookup"><span data-stu-id="d4c19-115">Inherit from critical types.</span></span>

  <span data-ttu-id="d4c19-116">Außerdem können transparente Methoden keine wichtigen virtuellen Methoden überschreiben oder wichtige Schnittstellenmethoden implementieren.</span><span class="sxs-lookup"><span data-stu-id="d4c19-116">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="d4c19-117">Sicherheitsgeschützter Code ist vollständig vertrauenswürdig, kann aber durch transparenten Code aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d4c19-117">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="d4c19-118">Er macht einen beschränkten Oberflächenbereich mit vollständig vertrauenswürdigem Code verfügbar. Korrektheits- und Sicherheitsüberprüfungen werden in sicherheitsgeschütztem Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-118">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="d4c19-119">Mit sicherheitskritischem Code kann jeder Code aufgerufen werden, und er ist vollständig vertrauenswürdig, kann jedoch nicht von transparentem Code aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d4c19-119">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="d4c19-120">Verwendungsbeispiele und Verhalten</span><span class="sxs-lookup"><span data-stu-id="d4c19-120">Usage Examples and Behaviors</span></span>

<span data-ttu-id="d4c19-121">Verwenden Sie zum Angeben von .NET Framework 4-Regeln (Transparenz der Ebene 2) die folgende Anmerkung für eine Assembly:</span><span class="sxs-lookup"><span data-stu-id="d4c19-121">To specify .NET Framework 4 rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="d4c19-122">Um die .NET Framework 2.0-Regeln (Transparenz der Ebene 1) festzulegen, verwenden Sie die folgende Anmerkung:</span><span class="sxs-lookup"><span data-stu-id="d4c19-122">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="d4c19-123">Wenn Sie keine Assembly mit Anmerkungen versehen, werden standardmäßig die .NET Framework 4-Regeln verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4c19-123">If you do not annotate an assembly, the .NET Framework 4 rules are used by default.</span></span> <span data-ttu-id="d4c19-124">Es wird jedoch empfohlen, das- <xref:System.Security.SecurityRulesAttribute> Attribut anstelle der Standardeinstellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4c19-124">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="d4c19-125">Assemblyweite Anmerkung</span><span class="sxs-lookup"><span data-stu-id="d4c19-125">Assembly-wide Annotation</span></span>

<span data-ttu-id="d4c19-126">Die folgenden Regeln gelten für die Verwendung von Attributen auf Assemblyebene:</span><span class="sxs-lookup"><span data-stu-id="d4c19-126">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="d4c19-127">Keine Attribute: Wenn Sie keine Attribute angeben, interpretiert die Laufzeit den gesamten Code als sicherheitskritisch, es sei denn, die Einstufung als sicherheitskritisch verletzt eine Vererbungsregel (z. B. beim Überschreiben oder Implementieren einer transparenten virtuellen oder Schnittstellenmethode).</span><span class="sxs-lookup"><span data-stu-id="d4c19-127">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="d4c19-128">In diesen Fällen sind die Methoden sicherheitsgeschützt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-128">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="d4c19-129">Wenn kein Attribut angegeben wird, bestimmt die Common Language Runtime die Transparenzregeln.</span><span class="sxs-lookup"><span data-stu-id="d4c19-129">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="d4c19-130">`SecurityTransparent`: Der gesamte Code ist transparent, und die gesamte Assembly führt keine privilegierten oder unsicheren Aktionen durch.</span><span class="sxs-lookup"><span data-stu-id="d4c19-130">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="d4c19-131">`SecurityCritical`: Der gesamte Code, der von Typen in dieser Assembly eingeführt wird, ist wichtig, und der gesamte andere Code ist transparent.</span><span class="sxs-lookup"><span data-stu-id="d4c19-131">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="d4c19-132">Dieses Szenario ähnelt dem Fall, dass keine Attribute angegeben werden, allerdings werden die Transparenzregeln nicht automatisch von der Common Language Runtime bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-132">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="d4c19-133">Wenn Sie beispielsweise eine virtuelle oder abstrakte Methode überschreiben oder eine Schnittstellenmethode implementieren, ist diese Methode standardmäßig transparent.</span><span class="sxs-lookup"><span data-stu-id="d4c19-133">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="d4c19-134">Sie müssen die Methode explizit als `SecurityCritical` oder `SecuritySafeCritical` kommentieren, andernfalls wird zur Ladezeit eine <xref:System.TypeLoadException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d4c19-134">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="d4c19-135">Diese Regel gilt auch, wenn die Basisklasse und die abgeleitete Klasse sich in der gleichen Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="d4c19-135">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="d4c19-136">`AllowPartiallyTrustedCallers` (nur Ebene 2): Der gesamte Code ist standardmäßig transparent.</span><span class="sxs-lookup"><span data-stu-id="d4c19-136">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="d4c19-137">Einzelne Typen und Member können jedoch andere Attribute haben.</span><span class="sxs-lookup"><span data-stu-id="d4c19-137">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="d4c19-138">In der folgenden Tabelle wird das Verhalten auf Assemblyebene für Ebene 2 mit Ebene 1 verglichen.</span><span class="sxs-lookup"><span data-stu-id="d4c19-138">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="d4c19-139">Assembly-Attribut</span><span class="sxs-lookup"><span data-stu-id="d4c19-139">Assembly attribute</span></span>|<span data-ttu-id="d4c19-140">Ebene 2</span><span class="sxs-lookup"><span data-stu-id="d4c19-140">Level 2</span></span>|<span data-ttu-id="d4c19-141">Ebene 1</span><span class="sxs-lookup"><span data-stu-id="d4c19-141">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="d4c19-142">Kein Attribut in einer teilweise vertrauenswürdigen Assembly</span><span class="sxs-lookup"><span data-stu-id="d4c19-142">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="d4c19-143">Typen und Member sind standardmäßig transparent, aber können sicherheitskritisch oder sicherheitsgeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="d4c19-143">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="d4c19-144">Alle Typen und Member sind transparent.</span><span class="sxs-lookup"><span data-stu-id="d4c19-144">All types and members are transparent.</span></span>|
|<span data-ttu-id="d4c19-145">Kein Attribut</span><span class="sxs-lookup"><span data-stu-id="d4c19-145">No attribute</span></span>|<span data-ttu-id="d4c19-146">Wenn kein Attribut angegeben wird, bestimmt die Common Language Runtime die Transparenzregeln.</span><span class="sxs-lookup"><span data-stu-id="d4c19-146">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="d4c19-147">Alle Typen und Member sind sicherheitskritisch, es sei denn, die Einstufung als sicherheitskritisch verletzt eine Vererbungsregel.</span><span class="sxs-lookup"><span data-stu-id="d4c19-147">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="d4c19-148">In einer voll vertrauenswürdigen Assembly (im globalen Assemblycache oder als voll vertrauenswürdig in der `AppDomain` identifiziert) sind alle Typen transparent, und alle Member sind sicherheitsgeschützt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-148">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="d4c19-149">Alle Typen und Member sind transparent.</span><span class="sxs-lookup"><span data-stu-id="d4c19-149">All types and members are transparent.</span></span>|<span data-ttu-id="d4c19-150">Alle Typen und Member sind transparent.</span><span class="sxs-lookup"><span data-stu-id="d4c19-150">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="d4c19-151">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4c19-151">Not applicable.</span></span>|<span data-ttu-id="d4c19-152"> Alle Typen und Member sind sicherheitskritisch.</span><span class="sxs-lookup"><span data-stu-id="d4c19-152">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="d4c19-153">Der gesamte Code, der von Typen in dieser Assembly eingeführt wird, ist wichtig, und der gesamte andere Code ist transparent.</span><span class="sxs-lookup"><span data-stu-id="d4c19-153">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="d4c19-154">Wenn Sie eine virtuelle oder abstrakte Methode überschreiben oder eine Schnittstellenmethode implementieren, müssen Sie diese Methode explizit per Anmerkung als `SecurityCritical` oder `SecuritySafeCritical` kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="d4c19-154">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="d4c19-155">Der gesamte Code ist standardmäßig transparent.</span><span class="sxs-lookup"><span data-stu-id="d4c19-155">All code defaults to transparent.</span></span> <span data-ttu-id="d4c19-156">Einzelne Typen und Member können jedoch andere Attribute haben.</span><span class="sxs-lookup"><span data-stu-id="d4c19-156">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="d4c19-157">Typ- und Memberanmerkung</span><span class="sxs-lookup"><span data-stu-id="d4c19-157">Type and Member Annotation</span></span>

<span data-ttu-id="d4c19-158">Die Sicherheitsattribute, die auf einen Typ angewendet werden, gelten auch für die Elemente, die vom Typ eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d4c19-158">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="d4c19-159">Allerdings gelten sie nicht für virtuelle oder abstrakte Überschreibungen der Basisklassen- oder  Schnittstellenimplementierungen.</span><span class="sxs-lookup"><span data-stu-id="d4c19-159">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="d4c19-160">Die folgenden Regeln gelten für die Verwendung von Attributen auf Typ- und Memberebene:</span><span class="sxs-lookup"><span data-stu-id="d4c19-160">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="d4c19-161">`SecurityCritical`: Der Typ oder Member ist wichtig und kann nur von voll vertrauenswürdigem Code aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d4c19-161">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="d4c19-162">Methoden, die in einem sicherheitsrelevanten Typ eingeführt werden, sind wichtig.</span><span class="sxs-lookup"><span data-stu-id="d4c19-162">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d4c19-163">Virtuelle und abstrakte Methoden, die in Basisklassen oder Schnittstellen eingeführt und überschrieben oder in einer sicherheitskritischen Klasse implementiert werden, sind standardmäßig transparent.</span><span class="sxs-lookup"><span data-stu-id="d4c19-163">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="d4c19-164">Sie müssen als `SecuritySafeCritical` oder `SecurityCritical` identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="d4c19-164">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="d4c19-165">`SecuritySafeCritical`: Der Typ oder Member ist sicherheitsgeschützt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-165">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="d4c19-166">Allerdings kann der Typ oder Member von transparentem (teilweise vertrauenswürdigem) Code aufgerufen werden und ist so leistungsfähig wie jeder andere wichtige Code.</span><span class="sxs-lookup"><span data-stu-id="d4c19-166">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="d4c19-167">Der Code muss hinsichtlich der Sicherheit überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="d4c19-167">The code must be audited for security.</span></span>

## <a name="override-patterns"></a><span data-ttu-id="d4c19-168">Überschreibungsmuster</span><span class="sxs-lookup"><span data-stu-id="d4c19-168">Override Patterns</span></span>

<span data-ttu-id="d4c19-169">In der folgenden Tabelle werden die für die Transparenz der Ebene 2 zulässigen Methodenüberschreibungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-169">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="d4c19-170">Basis virtuell/Schnittstellenmember</span><span class="sxs-lookup"><span data-stu-id="d4c19-170">Base virtual/interface member</span></span>|<span data-ttu-id="d4c19-171">Überschreiben/Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4c19-171">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a><span data-ttu-id="d4c19-172">Vererbungsregeln</span><span class="sxs-lookup"><span data-stu-id="d4c19-172">Inheritance Rules</span></span>

<span data-ttu-id="d4c19-173">In diesem Abschnitt wird `Transparent`, `Critical` und `SafeCritical` Code basierend auf Zugriff und Funktionalität folgende Reihenfolge zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="d4c19-173">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="d4c19-174">Regeln für Typen: Von links nach rechts wird der Zugriff immer stärker eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-174">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="d4c19-175">Abgeleitete Typen müssen mindestens so restriktiv wie der Basistyp sein.</span><span class="sxs-lookup"><span data-stu-id="d4c19-175">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="d4c19-176">Regeln für Methoden: Der Zugriff abgeleiteter Methoden kann nicht vom Zugriff der Basismethode abweichen.</span><span class="sxs-lookup"><span data-stu-id="d4c19-176">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="d4c19-177">Standardmäßig sind alle abgeleiteten Methoden, die nicht mit einer Anmerkung versehen sind, `Transparent`.</span><span class="sxs-lookup"><span data-stu-id="d4c19-177">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="d4c19-178">Ableitungen wichtiger Typen bewirken, dass eine Ausnahme ausgelöst wird, wenn die überschriebene Methode nicht explizit als `SecurityCritical` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="d4c19-178">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="d4c19-179">In der folgenden Tabelle werden die zulässigen Muster der Typenvererbung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-179">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="d4c19-180">Basisklasse</span><span class="sxs-lookup"><span data-stu-id="d4c19-180">Base class</span></span>|<span data-ttu-id="d4c19-181">Abgeleitete Klasse kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="d4c19-181">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="d4c19-182">In der folgenden Tabelle werden die unzulässigen Muster der Typenvererbung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-182">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="d4c19-183">Basisklasse</span><span class="sxs-lookup"><span data-stu-id="d4c19-183">Base class</span></span>|<span data-ttu-id="d4c19-184">Abgeleitete Klasse kann Folgendes nicht sein:</span><span class="sxs-lookup"><span data-stu-id="d4c19-184">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="d4c19-185">In der folgenden Tabelle werden die zulässigen Muster der Methodenvererbung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-185">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="d4c19-186">Basismethode</span><span class="sxs-lookup"><span data-stu-id="d4c19-186">Base method</span></span>|<span data-ttu-id="d4c19-187">Abgeleitete Methode kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="d4c19-187">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="d4c19-188">In der folgenden Tabelle werden die unzulässigen Muster der Methodenvererbung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-188">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="d4c19-189">Basismethode</span><span class="sxs-lookup"><span data-stu-id="d4c19-189">Base method</span></span>|<span data-ttu-id="d4c19-190">Abgeleitete Methode kann Folgendes nicht sein:</span><span class="sxs-lookup"><span data-stu-id="d4c19-190">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="d4c19-191">Diese Vererbungsregeln gelten für Typen und Member der Ebene 2.</span><span class="sxs-lookup"><span data-stu-id="d4c19-191">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="d4c19-192">Typen in Assemblys der Ebene 1 können von sicherheitskritischen Typen und Membern der Ebene 2 erben.</span><span class="sxs-lookup"><span data-stu-id="d4c19-192">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="d4c19-193">Daher müssen Typen und Member der Ebene 2 separate  Vererbungsanforderungen für Erben der Ebene 1 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d4c19-193">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

## <a name="additional-information-and-rules"></a><span data-ttu-id="d4c19-194">Zusätzliche Informationen und Regeln</span><span class="sxs-lookup"><span data-stu-id="d4c19-194">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="d4c19-195">LinkDemand-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="d4c19-195">LinkDemand Support</span></span>

<span data-ttu-id="d4c19-196">Das Transparenzmodell der Ebene 2 ersetzt <xref:System.Security.Permissions.SecurityAction.LinkDemand> durch das <xref:System.Security.SecurityCriticalAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="d4c19-196">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="d4c19-197">In Legacycode (Stufe 1) wird ein <xref:System.Security.Permissions.SecurityAction.LinkDemand> automatisch als ein <xref:System.Security.Permissions.SecurityAction.Demand> behandelt.</span><span class="sxs-lookup"><span data-stu-id="d4c19-197">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="d4c19-198">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="d4c19-198">Reflection</span></span>

<span data-ttu-id="d4c19-199">Das Aufrufen einer wichtigen Methode oder das Lesen eines wichtigen Felds löst eine Anforderung vollständiger Vertrauenswürdigkeit aus (wie beim Aufrufen einer privaten Methode oder eines privaten Felds).</span><span class="sxs-lookup"><span data-stu-id="d4c19-199">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="d4c19-200">Aus diesem Grund kann voll vertrauenswürdiger Code eine wichtige Methode aufrufen, teilweise vertrauenswürdiger Code hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="d4c19-200">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="d4c19-201">Die folgenden Eigenschaften wurden dem Namespace "<xref:System.Reflection>" hinzugefügt, um zu bestimmen, ob der Typ, die Methode oder das Feld `SecurityCritical`, `SecuritySafeCritical` oder `SecurityTransparent` ist:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> und <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4c19-201">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="d4c19-202">Verwenden Sie diese Eigenschaften zur Bestimmung der Transparenz durch Reflektion statt durch Prüfen auf das Vorhandensein des Attributs.</span><span class="sxs-lookup"><span data-stu-id="d4c19-202">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="d4c19-203">Die Transparenzregeln sind komplex, und das Prüfen auf das Attribut ist möglicherweise nicht ausreichend.</span><span class="sxs-lookup"><span data-stu-id="d4c19-203">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c19-204">Eine `SafeCritical` Methode gibt `true` sowohl für <xref:System.Type.IsSecurityCritical%2A> als auch zurück <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> , da `SafeCritical` tatsächlich kritisch ist (Sie hat die gleichen Funktionen wie kritischer Code, aber Sie kann aus transparentem Code aufgerufen werden).</span><span class="sxs-lookup"><span data-stu-id="d4c19-204">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="d4c19-205">Dynamische Methoden erben die Transparenz der Module, denen sie zugeordnet sind. Sie erben nicht die Transparenz des Typs (sofern sie einem Typ zugeordnet sind).</span><span class="sxs-lookup"><span data-stu-id="d4c19-205">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="d4c19-206">Überspringen der Überprüfung bei vollständiger Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="d4c19-206">Skip Verification in Full Trust</span></span>

<span data-ttu-id="d4c19-207">Sie können die Überprüfung für vollständig vertrauenswürdige transparente Assemblys überspringen, indem Sie die Eigenschaft "<xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A>" im Attribut "<xref:System.Security.SecurityRulesAttribute>" auf "`true`" festlegen:</span><span class="sxs-lookup"><span data-stu-id="d4c19-207">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="d4c19-208">Die Eigenschaft "<xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A>" ist standardmäßig "`false`" und muss daher auf "`true`" festgelegt werden, um die Überprüfung zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="d4c19-208">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="d4c19-209">Dies sollte nur zu Optimierungszwecken erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d4c19-209">This should be done for optimization purposes only.</span></span> <span data-ttu-id="d4c19-210">Stellen Sie sicher, dass der transparente Code in der Assembly überprüfbar ist. verwenden Sie dazu die `transparent` Option im [Tool "Peer Verify](../tools/peverify-exe-peverify-tool.md)".</span><span class="sxs-lookup"><span data-stu-id="d4c19-210">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4c19-211">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4c19-211">See also</span></span>

- [<span data-ttu-id="d4c19-212">Sicherheitstransparenter Code, Ebene 1</span><span class="sxs-lookup"><span data-stu-id="d4c19-212">Security-Transparent Code, Level 1</span></span>](security-transparent-code-level-1.md)
- [<span data-ttu-id="d4c19-213">Sicherheitsänderungen</span><span class="sxs-lookup"><span data-stu-id="d4c19-213">Security Changes</span></span>](/previous-versions/dotnet/framework/security/security-changes)
