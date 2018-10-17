---
title: Starke Namen und Bibliotheken für .NET
description: Best Practice-Empfehlungen für starke Benennung Bibliotheken für .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: e3f7d443eb9acc84c800ea2611b803733085391c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372805"
---
# <a name="strong-naming"></a><span data-ttu-id="7e45f-103">Starke Namen</span><span class="sxs-lookup"><span data-stu-id="7e45f-103">Strong naming</span></span>

<span data-ttu-id="7e45f-104">Starke Namen verweist, auf das Signieren einer Assembly mit einem Schlüssel erzeugt eine [Assembly mit starkem Namen](../../framework/app-domains/strong-named-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="7e45f-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../../framework/app-domains/strong-named-assemblies.md).</span></span> <span data-ttu-id="7e45f-105">Wenn eine Assembly mit starkem Namen handelt, erstellt eine eindeutige Identität, die basierend auf den Namen und die Assembly-Versionsnummer, und es verhindert assemblykonflikte.</span><span class="sxs-lookup"><span data-stu-id="7e45f-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="7e45f-106">Starke Namen in der Nachteil ist, dass .NET Framework unter Windows ermöglicht strict Laden von Assemblys aus, sobald eine Assembly einen starken Namen besitzt.</span><span class="sxs-lookup"><span data-stu-id="7e45f-106">The downside to strong naming is that the .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="7e45f-107">Ein Assemblyverweis mit starkem Namen muss genau die Version, die auf die verwiesen wird von einer Assembly, die Entwickler zu zwingen [konfigurieren bindungsumleitungen](../../framework/configure-apps/redirect-assembly-versions.md) , wenn die Assembly verwenden:</span><span class="sxs-lookup"><span data-stu-id="7e45f-107">A strong-named assembly reference must exactly match the version referenced by an assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

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

<span data-ttu-id="7e45f-108">Wenn starke Namen in .NET Entwickler der Adresssyntax, ist was sie in der Regel zu beschweren sind strenge beim Laden von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="7e45f-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="7e45f-109">Glücklicherweise wird dieses Problem isoliert auf .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e45f-109">Fortunately, this issue is isolated to the .NET Framework.</span></span> <span data-ttu-id="7e45f-110">.NET Core, Xamarin, UWP und die meisten anderen Implementierungen von .NET keine strenge beim Laden von Assemblys und den wichtigsten Nachteil von starken Namen entfernt.</span><span class="sxs-lookup"><span data-stu-id="7e45f-110">.NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading and removes the main downside of strong naming.</span></span>

<span data-ttu-id="7e45f-111">Ein wichtiger Aspekt der starke Namen ist, dass es viraler handelt: einen starken Namen Assembly können nur auf anderen starken Namens Assemblys.</span><span class="sxs-lookup"><span data-stu-id="7e45f-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="7e45f-112">Wenn Ihre Bibliothek nicht sichere mit dem Namen ist, haben Sie Entwickler ausgeschlossen, die eine Anwendung oder Bibliothek, die benötigt wird, verwenden sie starke Namen erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e45f-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="7e45f-113">Die Vorteile der starken Namen sind:</span><span class="sxs-lookup"><span data-stu-id="7e45f-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="7e45f-114">Die Assembly auf die verwiesen wird, und von anderen Assemblys mit starkem Namen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7e45f-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="7e45f-115">Die Assembly kann in den globalen Assemblycache (GAC) gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="7e45f-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="7e45f-116">Die Assembly kann parallel mit anderen Versionen der Assembly geladen werden.</span><span class="sxs-lookup"><span data-stu-id="7e45f-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="7e45f-117">Laden von Assemblys für Seite-an-Seite ist im Allgemeinen von Anwendungen mit Plug-in-Architekturen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7e45f-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="7e45f-118">Erstellen Sie sichere mit dem Namen Bibliotheken für .NET</span><span class="sxs-lookup"><span data-stu-id="7e45f-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="7e45f-119">Sie sollten Ihre Open-Source-Bibliotheken .NET strong benennen.</span><span class="sxs-lookup"><span data-stu-id="7e45f-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="7e45f-120">Starke Namen einer Assemblys wird sichergestellt, die meisten Personen Sie verwenden können, und nur strenge assamblys wirkt sich auf .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e45f-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="7e45f-121">Diese Anleitung bezieht sich auf öffentlich verteilte Bibliotheken für .NET, wie z. B. Bibliotheken für .NET auf NuGet.org veröffentlicht. Starke Namen ist nicht von den meisten Anwendungen für .NET erforderlich und sollte nicht standardmäßig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7e45f-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="7e45f-122">**✔️ GGF.** starke Benennung Ihrer Bibliothek Assemblys.</span><span class="sxs-lookup"><span data-stu-id="7e45f-122">**✔️ CONSIDER** strong naming your library's assemblies.</span></span>

<span data-ttu-id="7e45f-123">**✔️ GGF.** der Schlüssel zum starken Namen in Ihr Quellcodeverwaltungssystem einchecken.</span><span class="sxs-lookup"><span data-stu-id="7e45f-123">**✔️ CONSIDER** checking in the key used to strong name into your source control system.</span></span>

> <span data-ttu-id="7e45f-124">Ein öffentlich verfügbarer Schlüssel ermöglicht Entwicklern das Ändern und Kompilieren Ihren Quellcode der Bibliothek mit dem gleichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="7e45f-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e45f-125">Wenn eine kryptografische Identität gewünscht wird, [Authenticode](/windows-hardware/drivers/install/authenticode) und [NuGet-Paketsignierung](/nuget/create-packages/sign-a-package) werden empfohlen.</span><span class="sxs-lookup"><span data-stu-id="7e45f-125">When a cryptographic identity is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="7e45f-126">Starke Namen sollten nicht für Überlegungen zur Sicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e45f-126">Strong naming should not be used for security considerations.</span></span>

<span data-ttu-id="7e45f-127">**✔️ GGF.** erhöht die Assemblyversion nur Hauptversion geändert, damit die Benutzer zu reduzieren, bindungsumleitungen, und wie oft sie aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7e45f-127">**✔️ CONSIDER** incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="7e45f-128">Erfahren Sie mehr über [versionsverwaltung und die Version der Assembly](./versioning.md#assembly-version).</span><span class="sxs-lookup"><span data-stu-id="7e45f-128">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="7e45f-129">**❌ NICHT** hinzufügen, entfernen oder ändern Sie den Schlüssel für starke benennungen.</span><span class="sxs-lookup"><span data-stu-id="7e45f-129">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="7e45f-130">Ändern einer Assembly starke Benennung Schlüssel ändert sich der Identität der Assembly und unterbricht kompilierten Code, der verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7e45f-130">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="7e45f-131">Weitere Informationen finden Sie unter [binäre wichtige Änderungen](./breaking-changes.md#binary-breaking-change).</span><span class="sxs-lookup"><span data-stu-id="7e45f-131">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="7e45f-132">**❌ NICHT** starken Namen haben und ohne starken Namen Versionen Ihrer Bibliothek veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="7e45f-132">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="7e45f-133">Beispiel: `Contoso.Api` und `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="7e45f-133">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="7e45f-134">Veröffentlichen zwei Pakete Forks umfassendes für Ihre Entwickler.</span><span class="sxs-lookup"><span data-stu-id="7e45f-134">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="7e45f-135">Wenn eine Anwendung je nach beide Pakete am Ende kann Entwickler außerdem namenstypkonflikten auftreten.</span><span class="sxs-lookup"><span data-stu-id="7e45f-135">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="7e45f-136">Als .NET betrifft, sind sie verschiedene Typen in anderen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="7e45f-136">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="7e45f-137">[Zurück](./cross-platform-targeting.md)
[Weiter](./nuget.md)</span><span class="sxs-lookup"><span data-stu-id="7e45f-137">[Previous](./cross-platform-targeting.md)
[Next](./nuget.md)</span></span>
