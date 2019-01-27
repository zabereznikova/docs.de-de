---
title: Sicherheitstransparenter Code, Ebene 2
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8425b294328d4fc7546a372b329d8fa834a088d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567021"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="140da-102">Sicherheitstransparenter Code, Ebene 2</span><span class="sxs-lookup"><span data-stu-id="140da-102">Security-Transparent Code, Level 2</span></span>
<a name="top"></a>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="140da-103">Transparenz der Ebene 2 wurde in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] eingeführt.</span><span class="sxs-lookup"><span data-stu-id="140da-103">Level 2 transparency was introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="140da-104">Die drei Grundsätze dieses Modells sind transparenter Code, sicherheitsgeschützter Code und sicherheitskritischer Code.</span><span class="sxs-lookup"><span data-stu-id="140da-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>  
  
-   <span data-ttu-id="140da-105">Transparenter Code, einschließlich Code, der mit voller Vertrauenswürdigkeit ausgeführt wird, kann anderen transparenten Code oder sicherheitsgeschützten Code nur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="140da-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="140da-106">Er kann nur Aktionen durchführen, die von der domänenspezifischen Berechtigungseinstellung für teilweise Vertrauenswürdigkeit zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="140da-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="140da-107">Transparenter Code ist nicht für die folgenden Vorgänge vorgesehen:</span><span class="sxs-lookup"><span data-stu-id="140da-107">Transparent code cannot do the following:</span></span>  
  
    -   <span data-ttu-id="140da-108">Ausführen eines <xref:System.Security.CodeAccessPermission.Assert%2A>-Vorgangs oder einer Berechtigungserweiterung.</span><span class="sxs-lookup"><span data-stu-id="140da-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>  
  
    -   <span data-ttu-id="140da-109">Der Code darf keinen unsicheren oder nicht überprüfbaren Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="140da-109">Contain unsafe or unverifiable code.</span></span>  
  
    -   <span data-ttu-id="140da-110">Direktes Aufrufen von wichtigem Code.</span><span class="sxs-lookup"><span data-stu-id="140da-110">Directly call critical code.</span></span>  
  
    -   <span data-ttu-id="140da-111">Aufrufen von systemeigenen Code oder von Code mit dem <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="140da-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>  
  
    -   <span data-ttu-id="140da-112">Aufrufen eines Members, der von einem <xref:System.Security.Permissions.SecurityAction.LinkDemand>-Feld geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="140da-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>  
  
    -   <span data-ttu-id="140da-113">Erben von wichtigen Typen.</span><span class="sxs-lookup"><span data-stu-id="140da-113">Inherit from critical types.</span></span>  
  
     <span data-ttu-id="140da-114">Außerdem können transparente Methoden keine wichtigen virtuellen Methoden überschreiben oder wichtige Schnittstellenmethoden implementieren.</span><span class="sxs-lookup"><span data-stu-id="140da-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>  
  
-   <span data-ttu-id="140da-115">Sicherheitsgeschützter Code ist vollständig vertrauenswürdig, kann aber durch transparenten Code aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="140da-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="140da-116">Er macht einen beschränkten Oberflächenbereich mit vollständig vertrauenswürdigem Code verfügbar. Korrektheits- und Sicherheitsüberprüfungen werden in sicherheitsgeschütztem Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="140da-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>  
  
-   <span data-ttu-id="140da-117">Mit sicherheitskritischem Code kann jeder Code aufgerufen werden, und er ist vollständig vertrauenswürdig, kann jedoch nicht von transparentem Code aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="140da-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>  
  
 <span data-ttu-id="140da-118">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="140da-118">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="140da-119">Verwendungsbeispiele und Verhalten</span><span class="sxs-lookup"><span data-stu-id="140da-119">Usage Examples and Behaviors</span></span>](#examples)  
  
-   [<span data-ttu-id="140da-120">Überschreibungsmuster</span><span class="sxs-lookup"><span data-stu-id="140da-120">Override Patterns</span></span>](#override)  
  
-   [<span data-ttu-id="140da-121">Vererbungsregeln</span><span class="sxs-lookup"><span data-stu-id="140da-121">Inheritance Rules</span></span>](#inheritance)  
  
-   [<span data-ttu-id="140da-122">Weitere Informationen und Regeln</span><span class="sxs-lookup"><span data-stu-id="140da-122">Additional Information and Rules</span></span>](#additional)  
  
<a name="examples"></a>   
## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="140da-123">Verwendungsbeispiele und Verhalten</span><span class="sxs-lookup"><span data-stu-id="140da-123">Usage Examples and Behaviors</span></span>  
 <span data-ttu-id="140da-124">Verwenden Sie die folgende Anmerkung für eine Assembly, um [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]-Regeln festzulegen:</span><span class="sxs-lookup"><span data-stu-id="140da-124">To specify [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules (level 2 transparency), use the following annotation for an assembly:</span></span>  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level2)]  
```  
  
 <span data-ttu-id="140da-125">Um die .NET Framework 2.0-Regeln (Transparenz der Ebene 1) festzulegen, verwenden Sie die folgende Anmerkung:</span><span class="sxs-lookup"><span data-stu-id="140da-125">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 <span data-ttu-id="140da-126">Wenn Sie eine Assembly nicht mit einer Anmerkung versehen, werden standardmäßig die [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]-Regeln verwendet.</span><span class="sxs-lookup"><span data-stu-id="140da-126">If you do not annotate an assembly, the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules are used by default.</span></span> <span data-ttu-id="140da-127">Die empfohlene bewährte Methode ist jedoch mit der <xref:System.Security.SecurityRulesAttribute> -Attribut anstelle von abhängig von der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="140da-127">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>  
  
### <a name="assembly-wide-annotation"></a><span data-ttu-id="140da-128">Assemblyweite Anmerkung</span><span class="sxs-lookup"><span data-stu-id="140da-128">Assembly-wide Annotation</span></span>  
 <span data-ttu-id="140da-129">Die folgenden Regeln gelten für die Verwendung von Attributen auf Assemblyebene:</span><span class="sxs-lookup"><span data-stu-id="140da-129">The following rules apply to the use of attributes at the assembly level:</span></span>  
  
-   <span data-ttu-id="140da-130">Keine Attribute: Wenn Sie keine Attribute angeben, interpretiert die Laufzeit den gesamten Code als sicherheitskritisch, es sei denn, in dem als sicherheitskritisch eine Vererbungsregel (z. B., wenn überschreiben oder Implementieren einer transparenten virtuellen oder Schnittstellenmethode).</span><span class="sxs-lookup"><span data-stu-id="140da-130">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="140da-131">In diesen Fällen sind die Methoden sicherheitsgeschützt.</span><span class="sxs-lookup"><span data-stu-id="140da-131">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="140da-132">Wenn kein Attribut angegeben wird, bestimmt die Common Language Runtime die Transparenzregeln.</span><span class="sxs-lookup"><span data-stu-id="140da-132">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>  
  
-   <span data-ttu-id="140da-133">`SecurityTransparent`: Der gesamte Code ist transparent. die gesamte Assembly wird keine privilegierten oder unsicheren Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="140da-133">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>  
  
-   <span data-ttu-id="140da-134">`SecurityCritical`: Der gesamte Code, der von Typen in dieser Assembly eingeführt wird, ist wichtig, und der gesamte andere Code ist transparent.</span><span class="sxs-lookup"><span data-stu-id="140da-134">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="140da-135">Dieses Szenario ähnelt dem Fall, dass keine Attribute angegeben werden, allerdings werden die Transparenzregeln nicht automatisch von der Common Language Runtime bestimmt.</span><span class="sxs-lookup"><span data-stu-id="140da-135">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="140da-136">Wenn Sie beispielsweise eine virtuelle oder abstrakte Methode überschreiben oder eine Schnittstellenmethode implementieren, ist diese Methode standardmäßig transparent.</span><span class="sxs-lookup"><span data-stu-id="140da-136">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="140da-137">Sie müssen die Methode explizit als `SecurityCritical` oder `SecuritySafeCritical` kommentieren, andernfalls wird zur Ladezeit eine <xref:System.TypeLoadException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="140da-137">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="140da-138">Diese Regel gilt auch, wenn die Basisklasse und die abgeleitete Klasse sich in der gleichen Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="140da-138">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>  
  
-   <span data-ttu-id="140da-139">`AllowPartiallyTrustedCallers` (Stufe 2 nur): Der gesamte Code ist standardmäßig transparent.</span><span class="sxs-lookup"><span data-stu-id="140da-139">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="140da-140">Einzelne Typen und Member können jedoch andere Attribute haben.</span><span class="sxs-lookup"><span data-stu-id="140da-140">However, individual types and members can have other attributes.</span></span>  
  
 <span data-ttu-id="140da-141">Die folgende Tabelle vergleicht das Verhalten des Assembly für Ebene 2 mit Ebene 1.</span><span class="sxs-lookup"><span data-stu-id="140da-141">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>  
  
|<span data-ttu-id="140da-142">Assembly-Attribut</span><span class="sxs-lookup"><span data-stu-id="140da-142">Assembly attribute</span></span>|<span data-ttu-id="140da-143">Ebene 2</span><span class="sxs-lookup"><span data-stu-id="140da-143">Level 2</span></span>|<span data-ttu-id="140da-144">Ebene 1</span><span class="sxs-lookup"><span data-stu-id="140da-144">Level 1</span></span>|  
|------------------------|-------------|-------------|  
|<span data-ttu-id="140da-145">Kein Attribut in einer teilweise vertrauenswürdigen Assembly</span><span class="sxs-lookup"><span data-stu-id="140da-145">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="140da-146">Typen und Member sind standardmäßig transparent, aber können sicherheitskritisch oder sicherheitsgeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="140da-146">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="140da-147">Alle Typen und Member sind transparent.</span><span class="sxs-lookup"><span data-stu-id="140da-147">All types and members are transparent.</span></span>|  
|<span data-ttu-id="140da-148">Kein Attribut</span><span class="sxs-lookup"><span data-stu-id="140da-148">No attribute</span></span>|<span data-ttu-id="140da-149">Wenn kein Attribut angegeben wird, bestimmt die Common Language Runtime die Transparenzregeln.</span><span class="sxs-lookup"><span data-stu-id="140da-149">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="140da-150">Alle Typen und Member sind sicherheitskritisch, es sei denn, die Einstufung als sicherheitskritisch verletzt eine Vererbungsregel.</span><span class="sxs-lookup"><span data-stu-id="140da-150">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="140da-151">In einer voll vertrauenswürdigen Assembly (im globalen Assemblycache oder als voll vertrauenswürdig in der `AppDomain` identifiziert) sind alle Typen transparent, und alle Member sind sicherheitsgeschützt.</span><span class="sxs-lookup"><span data-stu-id="140da-151">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|  
|`SecurityTransparent`|<span data-ttu-id="140da-152">Alle Typen und Member sind transparent.</span><span class="sxs-lookup"><span data-stu-id="140da-152">All types and members are transparent.</span></span>|<span data-ttu-id="140da-153">Alle Typen und Member sind transparent.</span><span class="sxs-lookup"><span data-stu-id="140da-153">All types and members are transparent.</span></span>|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="140da-154">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="140da-154">Not applicable.</span></span>|<span data-ttu-id="140da-155"> Alle Typen und Member sind sicherheitskritisch.</span><span class="sxs-lookup"><span data-stu-id="140da-155">All types and members are security-critical.</span></span>|  
|`SecurityCritical`|<span data-ttu-id="140da-156">Der gesamte Code, der von Typen in dieser Assembly eingeführt wird, ist wichtig, und der gesamte andere Code ist transparent.</span><span class="sxs-lookup"><span data-stu-id="140da-156">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="140da-157">Wenn Sie eine virtuelle oder abstrakte Methode überschreiben oder eine Schnittstellenmethode implementieren, müssen Sie diese Methode explizit per Anmerkung als `SecurityCritical` oder `SecuritySafeCritical` kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="140da-157">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="140da-158">Der gesamte Code ist standardmäßig transparent.</span><span class="sxs-lookup"><span data-stu-id="140da-158">All code defaults to transparent.</span></span> <span data-ttu-id="140da-159">Einzelne Typen und Member können jedoch andere Attribute haben.</span><span class="sxs-lookup"><span data-stu-id="140da-159">However, individual types and members can have other attributes.</span></span>|  
  
### <a name="type-and-member-annotation"></a><span data-ttu-id="140da-160">Typ- und Memberanmerkung</span><span class="sxs-lookup"><span data-stu-id="140da-160">Type and Member Annotation</span></span>  
 <span data-ttu-id="140da-161">Die Sicherheitsattribute, die auf einen Typ angewendet werden, gelten auch für die Elemente, die vom Typ eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="140da-161">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="140da-162">Allerdings gelten sie nicht für virtuelle oder abstrakte Überschreibungen der Basisklassen- oder  Schnittstellenimplementierungen.</span><span class="sxs-lookup"><span data-stu-id="140da-162">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="140da-163">Die folgenden Regeln gelten für die Verwendung von Attributen auf Typ- und Memberebene:</span><span class="sxs-lookup"><span data-stu-id="140da-163">The following rules apply to the use of attributes at the type and member level:</span></span>  
  
-   <span data-ttu-id="140da-164">`SecurityCritical`: Der Typ oder Member ist wichtig und kann nur von voll vertrauenswürdigem Code aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="140da-164">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="140da-165">Methoden, die in einem sicherheitsrelevanten Typ eingeführt werden, sind wichtig.</span><span class="sxs-lookup"><span data-stu-id="140da-165">Methods that are introduced in a security-critical type are critical.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="140da-166">Virtuelle und abstrakte Methoden, die in Basisklassen oder Schnittstellen eingeführt und überschrieben oder in einer sicherheitskritischen Klasse implementiert werden, sind standardmäßig transparent.</span><span class="sxs-lookup"><span data-stu-id="140da-166">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="140da-167">Sie müssen als `SecuritySafeCritical` oder `SecurityCritical` identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="140da-167">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>  
  
-   <span data-ttu-id="140da-168">`SecuritySafeCritical`: Der Typ oder Member ist sicherheitsgeschützt.</span><span class="sxs-lookup"><span data-stu-id="140da-168">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="140da-169">Allerdings kann der Typ oder Member von transparentem (teilweise vertrauenswürdigem) Code aufgerufen werden und ist so leistungsfähig wie jeder andere wichtige Code.</span><span class="sxs-lookup"><span data-stu-id="140da-169">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="140da-170">Der Code muss hinsichtlich der Sicherheit überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="140da-170">The code must be audited for security.</span></span>  
  
 [<span data-ttu-id="140da-171">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="140da-171">Back to top</span></span>](#top)  
  
<a name="override"></a>   
## <a name="override-patterns"></a><span data-ttu-id="140da-172">Überschreibungsmuster</span><span class="sxs-lookup"><span data-stu-id="140da-172">Override Patterns</span></span>  
 <span data-ttu-id="140da-173">In der folgenden Tabelle werden die für die Transparenz der Ebene 2 zulässigen Methodenüberschreibungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="140da-173">The following table shows the method overrides allowed for level 2 transparency.</span></span>  
  
|<span data-ttu-id="140da-174">Basis virtuell/Schnittstellenmember</span><span class="sxs-lookup"><span data-stu-id="140da-174">Base virtual/interface member</span></span>|<span data-ttu-id="140da-175">Überschreiben/Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="140da-175">Override/interface</span></span>|  
|------------------------------------|-------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 [<span data-ttu-id="140da-176">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="140da-176">Back to top</span></span>](#top)  
  
<a name="inheritance"></a>   
## <a name="inheritance-rules"></a><span data-ttu-id="140da-177">Vererbungsregeln</span><span class="sxs-lookup"><span data-stu-id="140da-177">Inheritance Rules</span></span>  
 <span data-ttu-id="140da-178">In diesem Abschnitt wird `Transparent`, `Critical` und `SafeCritical` Code basierend auf Zugriff und Funktionalität folgende Reihenfolge zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="140da-178">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>  
  
 `Transparent` < `SafeCritical` < `Critical`  
  
-   <span data-ttu-id="140da-179">Regeln für Typen: Wechseln von links nach rechts, immer den Zugriff stärker eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="140da-179">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="140da-180">Abgeleitete Typen müssen mindestens so restriktiv wie der Basistyp sein.</span><span class="sxs-lookup"><span data-stu-id="140da-180">Derived types must be at least as restrictive as the base type.</span></span>  
  
-   <span data-ttu-id="140da-181">Regeln für Methoden: Zugriff auf nicht von der Basismethode abgeleitete Methoden geändert werden.</span><span class="sxs-lookup"><span data-stu-id="140da-181">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="140da-182">Standardmäßig sind alle abgeleiteten Methoden, die nicht mit einer Anmerkung versehen sind, `Transparent`.</span><span class="sxs-lookup"><span data-stu-id="140da-182">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="140da-183">Ableitungen wichtiger Typen bewirken, dass eine Ausnahme ausgelöst wird, wenn die überschriebene Methode nicht explizit als `SecurityCritical` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="140da-183">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>  
  
 <span data-ttu-id="140da-184">In der folgenden Tabelle werden die zulässigen Muster der Typenvererbung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="140da-184">The following table shows the allowed type inheritance patterns.</span></span>  
  
|<span data-ttu-id="140da-185">Basisklasse</span><span class="sxs-lookup"><span data-stu-id="140da-185">Base class</span></span>|<span data-ttu-id="140da-186">Abgeleitete Klasse kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="140da-186">Derived class can be</span></span>|  
|----------------|--------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`SafeCritical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Critical`|  
  
 <span data-ttu-id="140da-187">In der folgenden Tabelle werden die unzulässigen Muster der Typenvererbung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="140da-187">The following table shows the disallowed type inheritance patterns.</span></span>  
  
|<span data-ttu-id="140da-188">Basisklasse</span><span class="sxs-lookup"><span data-stu-id="140da-188">Base class</span></span>|<span data-ttu-id="140da-189">Abgeleitete Klasse kann Folgendes nicht sein:</span><span class="sxs-lookup"><span data-stu-id="140da-189">Derived class cannot be</span></span>|  
|----------------|-----------------------------|  
|`SafeCritical`|`Transparent`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
 <span data-ttu-id="140da-190">In der folgenden Tabelle werden die zulässigen Muster der Methodenvererbung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="140da-190">The following table shows the allowed method inheritance patterns.</span></span>  
  
|<span data-ttu-id="140da-191">Basismethode</span><span class="sxs-lookup"><span data-stu-id="140da-191">Base method</span></span>|<span data-ttu-id="140da-192">Abgeleitete Methode kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="140da-192">Derived method can be</span></span>|  
|-----------------|---------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 <span data-ttu-id="140da-193">In der folgenden Tabelle werden die unzulässigen Muster der Methodenvererbung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="140da-193">The following table shows the disallowed method inheritance patterns.</span></span>  
  
|<span data-ttu-id="140da-194">Basismethode</span><span class="sxs-lookup"><span data-stu-id="140da-194">Base method</span></span>|<span data-ttu-id="140da-195">Abgeleitete Methode kann Folgendes nicht sein:</span><span class="sxs-lookup"><span data-stu-id="140da-195">Derived method cannot be</span></span>|  
|-----------------|------------------------------|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
> [!NOTE]
>  <span data-ttu-id="140da-196">Diese Vererbungsregeln gelten für Typen und Member der Ebene 2.</span><span class="sxs-lookup"><span data-stu-id="140da-196">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="140da-197">Typen in Assemblys der Ebene 1 können von sicherheitskritischen Typen und Membern der Ebene 2 erben.</span><span class="sxs-lookup"><span data-stu-id="140da-197">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="140da-198">Daher müssen Typen und Member der Ebene 2 separate  Vererbungsanforderungen für Erben der Ebene 1 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="140da-198">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>  
  
 [<span data-ttu-id="140da-199">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="140da-199">Back to top</span></span>](#top)  
  
<a name="additional"></a>   
## <a name="additional-information-and-rules"></a><span data-ttu-id="140da-200">Zusätzliche Informationen und Regeln</span><span class="sxs-lookup"><span data-stu-id="140da-200">Additional Information and Rules</span></span>  
  
### <a name="linkdemand-support"></a><span data-ttu-id="140da-201">LinkDemand-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="140da-201">LinkDemand Support</span></span>  
 <span data-ttu-id="140da-202">Das Transparenzmodell der Ebene 2 ersetzt <xref:System.Security.Permissions.SecurityAction.LinkDemand> durch das <xref:System.Security.SecurityCriticalAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="140da-202">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="140da-203">In Legacycode (Stufe 1) wird ein <xref:System.Security.Permissions.SecurityAction.LinkDemand> automatisch als ein <xref:System.Security.Permissions.SecurityAction.Demand> behandelt.</span><span class="sxs-lookup"><span data-stu-id="140da-203">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>  
  
### <a name="reflection"></a><span data-ttu-id="140da-204">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="140da-204">Reflection</span></span>  
 <span data-ttu-id="140da-205">Das Aufrufen einer wichtigen Methode oder das Lesen eines wichtigen Felds löst eine Anforderung vollständiger Vertrauenswürdigkeit aus (wie beim Aufrufen einer privaten Methode oder eines privaten Felds).</span><span class="sxs-lookup"><span data-stu-id="140da-205">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="140da-206">Aus diesem Grund kann voll vertrauenswürdiger Code eine wichtige Methode aufrufen, teilweise vertrauenswürdiger Code hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="140da-206">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>  
  
 <span data-ttu-id="140da-207">Die folgenden Eigenschaften wurden dem Namespace "<xref:System.Reflection>" hinzugefügt, um zu bestimmen, ob der Typ, die Methode oder das Feld `SecurityCritical`, `SecuritySafeCritical` oder `SecurityTransparent` ist:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> und <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="140da-207">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="140da-208">Verwenden Sie diese Eigenschaften zur Bestimmung der Transparenz durch Reflektion statt durch Prüfen auf das Vorhandensein des Attributs.</span><span class="sxs-lookup"><span data-stu-id="140da-208">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="140da-209">Die Transparenzregeln sind komplex, und das Prüfen auf das Attribut ist möglicherweise nicht ausreichend.</span><span class="sxs-lookup"><span data-stu-id="140da-209">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="140da-210">Ein `SafeCritical` Methodenrückgabe `true` für beide <xref:System.Type.IsSecurityCritical%2A> und <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, da `SafeCritical` tatsächlich wichtig ist (er weist die gleichen Funktionen wie Kritischer Code, aber sie kann von transparentem Code aufgerufen werden).</span><span class="sxs-lookup"><span data-stu-id="140da-210">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>  
  
 <span data-ttu-id="140da-211">Dynamische Methoden erben die Transparenz der Module, denen sie zugeordnet sind. Sie erben nicht die Transparenz des Typs (sofern sie einem Typ zugeordnet sind).</span><span class="sxs-lookup"><span data-stu-id="140da-211">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>  
  
### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="140da-212">Überspringen der Überprüfung bei vollständiger Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="140da-212">Skip Verification in Full Trust</span></span>  
 <span data-ttu-id="140da-213">Sie können die Überprüfung für vollständig vertrauenswürdige transparente Assemblys überspringen, indem Sie die Eigenschaft "<xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A>" im Attribut "<xref:System.Security.SecurityRulesAttribute>" auf "`true`" festlegen:</span><span class="sxs-lookup"><span data-stu-id="140da-213">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>  
  
 `[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`  
  
 <span data-ttu-id="140da-214">Die Eigenschaft "<xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A>" ist standardmäßig "`false`" und muss daher auf "`true`" festgelegt werden, um die Überprüfung zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="140da-214">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="140da-215">Dies sollte nur zu Optimierungszwecken erfolgen.</span><span class="sxs-lookup"><span data-stu-id="140da-215">This should be done for optimization purposes only.</span></span> <span data-ttu-id="140da-216">Sie sollten sicherstellen, dass der transparente Code in der Assembly mit überprüfbar ist die `transparent` option die [PEVerify-Tool](../../../docs/framework/tools/peverify-exe-peverify-tool.md).</span><span class="sxs-lookup"><span data-stu-id="140da-216">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../../../docs/framework/tools/peverify-exe-peverify-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="140da-217">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="140da-217">See also</span></span>
- [<span data-ttu-id="140da-218">Sicherheitstransparenter Code, Ebene 1</span><span class="sxs-lookup"><span data-stu-id="140da-218">Security-Transparent Code, Level 1</span></span>](../../../docs/framework/misc/security-transparent-code-level-1.md)
- [<span data-ttu-id="140da-219">Sicherheitsänderungen</span><span class="sxs-lookup"><span data-stu-id="140da-219">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)
