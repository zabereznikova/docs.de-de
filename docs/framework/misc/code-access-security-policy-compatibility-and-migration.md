---
title: Kompatibilität und Migration von Richtlinien für die Codezugriffssicherheit
description: Lesen Sie eine Zusammenfassung, und sehen Sie sich die Links zur Kompatibilität und Migration der Code Zugriffssicherheit in .NET Framework 4 an.
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
ms.openlocfilehash: 389976556175c0b6b300e75d01327d91f94f0db9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733385"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="a3282-103">Kompatibilität und Migration von Richtlinien für die Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="a3282-103">Code Access Security Policy Compatibility and Migration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="a3282-104">Der Richtlinien Teil der Code Zugriffssicherheit (Code Access Security, CAS) wurde in der .NET Framework 4 als veraltet eingestuft.</span><span class="sxs-lookup"><span data-stu-id="a3282-104">The policy portion of code access security (CAS) has been made obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="a3282-105">Daher können Kompilierungs Warnungen und Lauf Zeit Ausnahmen auftreten, wenn Sie die veralteten Richtlinien Typen und Member [explizit](#explicit_use) oder [implizit](#implicit_use) (über andere Typen und Member) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="a3282-105">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>

<span data-ttu-id="a3282-106">Sie können die Warnungen und Fehler folgendermaßen vermeiden:</span><span class="sxs-lookup"><span data-stu-id="a3282-106">You can avoid the warnings and errors by either:</span></span>

- <span data-ttu-id="a3282-107">[Migrieren](#migration) zu den .NET Framework 4-Ersetzungen für die veralteten Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="a3282-107">[Migrating](#migration) to the .NET Framework 4 replacements for the obsolete calls.</span></span>

   <span data-ttu-id="a3282-108">\- oder -</span><span class="sxs-lookup"><span data-stu-id="a3282-108">\- or -</span></span>

- <span data-ttu-id="a3282-109">Verwenden des- [ \<NetFx40_LegacySecurityPolicy> Konfigurations Elements](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) , um das Legacy-CAS-Richtlinien Verhalten zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="a3282-109">Using the [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>

<span data-ttu-id="a3282-110">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="a3282-110">This topic contains the following sections:</span></span>

- [<span data-ttu-id="a3282-111">Explizite Verwendung</span><span class="sxs-lookup"><span data-stu-id="a3282-111">Explicit Use</span></span>](#explicit_use)

- [<span data-ttu-id="a3282-112">Implizite Verwendung</span><span class="sxs-lookup"><span data-stu-id="a3282-112">Implicit Use</span></span>](#implicit_use)

- [<span data-ttu-id="a3282-113">Fehler und Warnungen</span><span class="sxs-lookup"><span data-stu-id="a3282-113">Errors and Warnings</span></span>](#errors_and_warnings)

- [<span data-ttu-id="a3282-114">Migration: Ersatz für veraltete Aufrufe</span><span class="sxs-lookup"><span data-stu-id="a3282-114">Migration: Replacement for Obsolete Calls</span></span>](#migration)

- [<span data-ttu-id="a3282-115">Kompatibilität: Verwenden der CAS-Legacyrichtlinienoption</span><span class="sxs-lookup"><span data-stu-id="a3282-115">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a><span data-ttu-id="a3282-116">Explizite Verwendung</span><span class="sxs-lookup"><span data-stu-id="a3282-116">Explicit Use</span></span>

<span data-ttu-id="a3282-117">Elemente, die die Sicherheitsrichtlinie direkt bearbeiten oder die CAS-Richtlinie für den Sandkasten benötigen, sind veraltet und generieren standardmäßig Fehler.</span><span class="sxs-lookup"><span data-stu-id="a3282-117">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>

<span data-ttu-id="a3282-118">Im Folgenden sind Beispiele dafür aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a3282-118">Examples of these are:</span></span>

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a><span data-ttu-id="a3282-119">Implizite Verwendung</span><span class="sxs-lookup"><span data-stu-id="a3282-119">Implicit Use</span></span>

<span data-ttu-id="a3282-120">Mehrere Überladungen beim Laden einer Assembly generieren Fehler aufgrund ihrer impliziten Verwendung der CAS-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a3282-120">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="a3282-121">Diese Überladungen nehmen einen Parameter <xref:System.Security.Policy.Evidence> an, der verwendet wird, um die CAS-Richtlinie aufzulösen und einen Berechtigungssatz für eine Assembly bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a3282-121">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>

<span data-ttu-id="a3282-122">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="a3282-122">Here are some examples.</span></span> <span data-ttu-id="a3282-123">Die veralteten Überladungen sind die Überladungen, die <xref:System.Security.Policy.Evidence> als Parameter annehmen:</span><span class="sxs-lookup"><span data-stu-id="a3282-123">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a><span data-ttu-id="a3282-124">Fehler und Warnungen</span><span class="sxs-lookup"><span data-stu-id="a3282-124">Errors and Warnings</span></span>

<span data-ttu-id="a3282-125">Die veralteten Typen und Elemente generieren die folgenden Fehlermeldungen, wenn sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3282-125">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="a3282-126">Beachten Sie, dass der Typ <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> selbst nicht veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="a3282-126">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>

<span data-ttu-id="a3282-127">Warnung zur Kompilierzeit:</span><span class="sxs-lookup"><span data-stu-id="a3282-127">Compile-time warning:</span></span>

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

<span data-ttu-id="a3282-128">Laufzeitausnahme:</span><span class="sxs-lookup"><span data-stu-id="a3282-128">Run-time exception:</span></span>

<span data-ttu-id="a3282-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="a3282-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="a3282-130">Migration: Ersatz für veraltete Aufrufe</span><span class="sxs-lookup"><span data-stu-id="a3282-130">Migration: Replacement for Obsolete Calls</span></span>

### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="a3282-131">Bestimmen der Vertrauensebene einer Assembly</span><span class="sxs-lookup"><span data-stu-id="a3282-131">Determining an Assembly’s Trust Level</span></span>

<span data-ttu-id="a3282-132">Die CAS-Richtlinie wird häufig verwendet, um den Berechtigungssatz einer Assembly oder Anwendungsdomäne oder die Vertrauensebene zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a3282-132">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="a3282-133">Der .NET Framework 4 macht die folgenden nützlichen Eigenschaften verfügbar, die nicht zum Auflösen von Sicherheitsrichtlinien erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="a3282-133">The .NET Framework 4 exposes the following useful properties that do not need to resolve security policy:</span></span>

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a><span data-ttu-id="a3282-134">Sandkasten für Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="a3282-134">Application Domain Sandboxing</span></span>

<span data-ttu-id="a3282-135">Die Methode <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> wird in der Regel verwendet, um Assemblys in einer Anwendungsdomäne in einem Sandkasten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a3282-135">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="a3282-136">Der .NET Framework 4 macht Mitglieder verfügbar, die für diesen Zweck nicht verwendet werden müssen <xref:System.Security.Policy.PolicyLevel> .</span><span class="sxs-lookup"><span data-stu-id="a3282-136">The .NET Framework 4 exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="a3282-137">Weitere Informationen finden Sie unter Gewusst [wie: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten](how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="a3282-137">For more information, see [How to: Run Partially Trusted Code in a Sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="a3282-138">Bestimmen eines sicheren oder geeigneten Berechtigungssatzes für teilweise vertrauenswürdigen Code</span><span class="sxs-lookup"><span data-stu-id="a3282-138">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>

<span data-ttu-id="a3282-139">Hosts müssen häufig die Berechtigungen ermitteln, die für das Ausführen von gehostetem Code in einem Sandkasten geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="a3282-139">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="a3282-140">Vor der .NET Framework 4 bot die CAS-Richtlinie eine Möglichkeit, dies mit der-Methode durchzuführen <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a3282-140">Before the .NET Framework 4, CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a3282-141">Als Ersatz stellt .NET Framework 4 die- <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> Methode bereit, die einen sicheren Standard Berechtigungs Satz für den bereitgestellten Beweis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a3282-141">As a replacement, .NET Framework 4 provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="a3282-142">Szenarien ohne Sandkasten: Überladungen für das Laden von Assemblys</span><span class="sxs-lookup"><span data-stu-id="a3282-142">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>

<span data-ttu-id="a3282-143">Der Grund für die Verwendung einer Überladung für das Laden einer Assembly kann die Verwendung von Parametern sein, die andernfalls nicht verfügbar sind, anstatt die Assembly in einem Sandkastens auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a3282-143">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="a3282-144">Beginnend mit dem .NET Framework 4 werden bei assemblylastenüberladungen, die kein- <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> Objekt als Parameter benötigen, z <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType> . b., dieses Szenario aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a3282-144">Starting with the .NET Framework 4, assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>

<span data-ttu-id="a3282-145">Wenn Sie einen Sandkasten für eine Assembly verwenden möchten, verwenden Sie die <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>-Überladung.</span><span class="sxs-lookup"><span data-stu-id="a3282-145">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="a3282-146">Kompatibilität: Verwenden der CAS-Legacyrichtlinienoption</span><span class="sxs-lookup"><span data-stu-id="a3282-146">Compatibility: Using the CAS Policy Legacy Option</span></span>

<span data-ttu-id="a3282-147">Mithilfe des [ \<NetFx40_LegacySecurityPolicy> Konfigurations Elements](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) können Sie angeben, dass ein Prozess oder eine Bibliothek eine Legacy-CAS-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3282-147">The [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="a3282-148">Wenn Sie dieses Element aktivieren, funktionieren die Richtlinien- und Beweisüberladungen wie in früheren Versionen des Frameworks.</span><span class="sxs-lookup"><span data-stu-id="a3282-148">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>

> [!NOTE]
> <span data-ttu-id="a3282-149">Das CAS-Richtlinienverhalten wird auf der Grundlage einer Laufzeitversion angegeben. Das Ändern der CAS-Richtlinie für eine Laufzeitversion besitzt daher keine Auswirkungen auf die CAS-Richtlinie einer anderen Version.</span><span class="sxs-lookup"><span data-stu-id="a3282-149">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a3282-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3282-150">See also</span></span>

- [<span data-ttu-id="a3282-151">How to: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten</span><span class="sxs-lookup"><span data-stu-id="a3282-151">How to: Run Partially Trusted Code in a Sandbox</span></span>](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="a3282-152">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="a3282-152">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
