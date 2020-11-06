---
title: Starke Namen und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden für starke Namen für .NET-Bibliotheken.
ms.date: 10/16/2018
ms.openlocfilehash: 6f9533d768331964a8e640243536b12ddde158e5
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189211"
---
# <a name="strong-naming"></a><span data-ttu-id="156ef-103">Starke Namen</span><span class="sxs-lookup"><span data-stu-id="156ef-103">Strong naming</span></span>

<span data-ttu-id="156ef-104">Starke Namen bezieht sich auf das Signieren einer Assembly mit einem Schlüssel, wodurch eine [Assembly mit starkem Namen](../assembly/strong-named.md) entsteht.</span><span class="sxs-lookup"><span data-stu-id="156ef-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../assembly/strong-named.md).</span></span> <span data-ttu-id="156ef-105">Wenn eine Assembly einen starken Namen hat, erzeugt sie eine eindeutige Identität basierend auf dem Namen und der Versionsnummer der Assembly, und dies kann helfen, Konflikte in der Assembly zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="156ef-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="156ef-106">Der Nachteil eines starken Namens ist, dass das .NET Framework unter Windows ein striktes Laden von Assemblys ermöglicht, sobald eine Assembly einen starken Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="156ef-106">The downside to strong naming is that .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="156ef-107">Eine Referenz auf eine Assembly mit starkem Namen muss genau der Version der geladenen Assembly entsprechen. Dadurch sind Entwickler gezwungen, [Bindungsumleitungen](../../framework/configure-apps/redirect-assembly-versions.md) zu konfigurieren, wenn sie die Assembly verwenden:</span><span class="sxs-lookup"><span data-stu-id="156ef-107">A strong-named assembly reference must exactly match the version of the loaded assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly" publicKeyToken="32ab4ba45e0a69a1" culture="neutral" />
            <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

<span data-ttu-id="156ef-108">Wenn sich .NET-Entwickler über starke Namen beschweren, geht es in der Regel um das strikte Laden einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="156ef-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="156ef-109">Glücklicherweise besteht dieses Problem nur im .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="156ef-109">Fortunately, this issue is isolated to .NET Framework.</span></span> <span data-ttu-id="156ef-110">.NET 5 und höher, .NET Core, Xamarin, UWP und die meisten anderen .NET-Implementierungen sind vom strikten Laden von Assemblys und somit dem größten Nachteil starker Namen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="156ef-110">.NET 5+, .NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading, which is the main downside of strong naming.</span></span>

<span data-ttu-id="156ef-111">Ein wichtiger Aspekt eines starken Namens ist, dass sie viral ist: eine Assembly mit einem starken Namen kann nur auf andere Assemblys mit einem starken Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="156ef-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="156ef-112">Wenn Ihre Bibliothek keinen starken Namen hat, dann haben Sie Entwickler, die eine Anwendung oder Bibliothek erstellen, die einen starken Namen benötigt, von der Verwendung ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="156ef-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="156ef-113">Die Vorteile der starken Namen sind:</span><span class="sxs-lookup"><span data-stu-id="156ef-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="156ef-114">Die Assembly kann nur von anderen Assemblys mit starkem Namen referenziert und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="156ef-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="156ef-115">Die Assembly kann im globalen Assemblycache (GAC) gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="156ef-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="156ef-116">Die Assembly kann parallel mit anderen Versionen der Assembly geladen werden.</span><span class="sxs-lookup"><span data-stu-id="156ef-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="156ef-117">Das parallele Laden von Assemblys ist häufig für Anwendungen mit Plug-in-Architekturen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="156ef-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="156ef-118">Erstellen von .NET-Bibliotheken mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="156ef-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="156ef-119">Sie sollten Ihren .NET-Open-Source-Bibliotheken einen starken Namen geben.</span><span class="sxs-lookup"><span data-stu-id="156ef-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="156ef-120">Der starke Name einer Assembly stellt sicher, dass die meisten Benutzer sie verwenden können. Das strikte Laden der Assembly betrifft nur das .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="156ef-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="156ef-121">Diese Anleitung bezieht sich auf öffentlich verteilte .NET-Bibliotheken, wie z.B. auf NuGet.org veröffentlichte .NET-Bibliotheken. Ein starker Namen ist für die meisten .NET-Anwendungen nicht erforderlich und sollte nicht standardmäßig vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="156ef-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="156ef-122">✔️ Erwägen Sie, Ihren Bibliotheksassemblys einen starken Namen zu geben.</span><span class="sxs-lookup"><span data-stu-id="156ef-122">✔️ CONSIDER strong naming your library's assemblies.</span></span>

<span data-ttu-id="156ef-123">✔️ Erwägen Sie, den Schlüssel für die eindeutige Benennung zu Ihrem Quellcodeverwaltungssystem hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="156ef-123">✔️ CONSIDER adding the strong naming key to your source control system.</span></span>

> <span data-ttu-id="156ef-124">Ein öffentlich verfügbarer Schlüssel ermöglicht es Entwicklern, den Quellcode Ihrer Bibliothek mit demselben Schlüssel zu ändern und neu zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="156ef-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>
>
> <span data-ttu-id="156ef-125">Sie sollten den starken Namensschlüssel nicht öffentlich machen, wenn er in der Vergangenheit zur Vergabe von Sonderrechten in [teilweise vertrauenswürdigen Szenarien](../../framework/misc/using-libraries-from-partially-trusted-code.md) verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="156ef-125">You shouldn't make the strong naming key public if it has been used in the past to give special permissions in [partial-trust scenarios](../../framework/misc/using-libraries-from-partially-trusted-code.md).</span></span> <span data-ttu-id="156ef-126">Andernfalls können Sie vorhandene Umgebungen beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="156ef-126">Otherwise, you might compromise existing environments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="156ef-127">Wenn die Identität des Herausgebers des Codes erwünscht ist, werden [Authenticode](/windows-hardware/drivers/install/authenticode) und [NuGet-Paketsignierung](/nuget/create-packages/sign-a-package) empfohlen.</span><span class="sxs-lookup"><span data-stu-id="156ef-127">When the identity of the publisher of the code is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="156ef-128">Die Codezugriffssicherheit (Code Access Security, CAS) sollte nicht zur Risikominderung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="156ef-128">Code Access Security (CAS) should not be used as a security mitigation.</span></span>

<span data-ttu-id="156ef-129">✔️ Erwägen Sie, die Assemblyversion nur bei größeren Versionsänderungen zu erhöhen, um Benutzern zu helfen, Bindungsumleitungen und die Häufigkeit ihrer Aktualisierung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="156ef-129">✔️ CONSIDER incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="156ef-130">Erfahren Sie mehr über die [Versionsverwaltung und die Assemblyversion](./versioning.md#assembly-version).</span><span class="sxs-lookup"><span data-stu-id="156ef-130">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="156ef-131">❌ Den Schlüssel für die eindeutige Benennung weder hinzufügen, noch ändern oder entfernen</span><span class="sxs-lookup"><span data-stu-id="156ef-131">❌ DO NOT add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="156ef-132">Das Ändern des starken Namensschlüssels einer Assembly ändert die Identität der Assembly und zerlegt kompilierten Code, der ihn verwendet.</span><span class="sxs-lookup"><span data-stu-id="156ef-132">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="156ef-133">Weitere Informationen finden Sie unter [Binäre Breaking Changes](./breaking-changes.md#binary-breaking-change).</span><span class="sxs-lookup"><span data-stu-id="156ef-133">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="156ef-134">❌ Veröffentlichen Sie NICHT die Versionen Ihrer Bibliothek mit oder ohne starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="156ef-134">❌ DO NOT publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="156ef-135">Beispiel: `Contoso.Api` und `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="156ef-135">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="156ef-136">Die Veröffentlichung von zwei Paketen verzweigt Ihr Entwicklerökosystem.</span><span class="sxs-lookup"><span data-stu-id="156ef-136">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="156ef-137">Auch wenn eine Anwendung letztendlich von beiden Paketen abhängig ist, kann es bei dem Entwickler zu Typnamenskonflikten kommen.</span><span class="sxs-lookup"><span data-stu-id="156ef-137">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="156ef-138">Was .NET betrifft, so sind sie verschiedene Typen in verschiedenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="156ef-138">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="156ef-139">[Zurück](cross-platform-targeting.md)
>[Weiter](nuget.md)</span><span class="sxs-lookup"><span data-stu-id="156ef-139">[Previous](cross-platform-targeting.md)
[Next](nuget.md)</span></span>
