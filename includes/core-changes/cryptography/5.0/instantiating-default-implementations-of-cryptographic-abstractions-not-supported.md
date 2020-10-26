---
ms.openlocfilehash: 8198eca5b9c63d9717260b71ac6687dbf7245f35
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159552"
---
### <a name="instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported"></a><span data-ttu-id="27043-101">Das Instanziieren von Standardimplementierungen kryptografischer Abstraktionen wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="27043-101">Instantiating default implementations of cryptographic abstractions is not supported</span></span>

<span data-ttu-id="27043-102">Die `Create()`-Überladungen ohne Parameter in kryptografischen Abstraktionen gelten ab .NET 5.0 als Warnung als veraltet.</span><span class="sxs-lookup"><span data-stu-id="27043-102">The parameterless `Create()` overloads on cryptographic abstractions are obsolete as warning as of .NET 5.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="27043-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="27043-103">Change description</span></span>

<span data-ttu-id="27043-104">In .NET Framework 2.0–4.8 können abstrakte kryptografische Primitivfactorys wie <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> so konfiguriert werden, dass sie verschiedene Algorithmen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27043-104">In .NET Framework 2.0 - 4.8, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> can be configured to return different algorithms.</span></span> <span data-ttu-id="27043-105">In einer Standardinstallation von .NET Framework 4.8 gibt die statische Methode <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> ohne Parameter beispielsweise eine Instanz des SHA1-Algorithmus zurück. Sehen Sie sich dazu den folgenden Codeausschnitt an.</span><span class="sxs-lookup"><span data-stu-id="27043-105">For example, on a default install of .NET Framework 4.8, the parameterless, static method <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> returns an instance of the SHA1 algorithm, as shown in the following snippet.</span></span>

<span data-ttu-id="27043-106">**Nur für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="27043-106">**.NET Framework only**</span></span>

```csharp
// Return an instance of the default hash algorithm (SHA1).
HashAlgorithm alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA1CryptoServiceProvider'.
Console.WriteLine(alg.GetType());

// Change the default algorithm to be SHA256, not SHA1.
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), typeof(HashAlgorithm).FullName);
alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA256CryptoServiceProvider'.
Console.WriteLine(alg.GetType());
```

<span data-ttu-id="27043-107">Sie können auch eine [computerweite Konfiguration](../../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) verwenden, um den Standardalgorithmus zu ändern, ohne `CryptoConfig` programmgesteuert aufrufen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="27043-107">You can also use [machine-wide configuration](../../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) to change the default algorithm without needing to call into `CryptoConfig` programmatically.</span></span>

<span data-ttu-id="27043-108">In .NET Core 2.0–3.1 führen abstrakte kryptografische Primitivfactorys wie <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> immer zu einer <xref:System.PlatformNotSupportedException>-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="27043-108">In .NET Core 2.0 - 3.1, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> always throw a <xref:System.PlatformNotSupportedException>.</span></span>

```csharp
// Throws PlatformNotSupportedException on .NET Core.
HashAlgorithm alg = HashAlgorithm.Create();
```

<span data-ttu-id="27043-109">In .NET 5.0 und höheren Versionen sind abstrakte kryptografische Primitivfactorys wie <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> als veraltet gekennzeichnet und führen zu einer Kompilierzeitwarnung mit der ID `SYSLIB0007`.</span><span class="sxs-lookup"><span data-stu-id="27043-109">In .NET 5.0 and later versions, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> are marked obsolete and produce a compile-time warning with ID `SYSLIB0007`.</span></span> <span data-ttu-id="27043-110">Zur Laufzeit wird für diese Methoden weiterhin eine <xref:System.PlatformNotSupportedException>-Ausnahme zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27043-110">At run time, these methods continue to throw a <xref:System.PlatformNotSupportedException>.</span></span>

```csharp
// Throws PlatformNotSupportedException.
// Also produces compile-time warning SYSLIB0007 on .NET 5+.
HashAlgorithm alg = HashAlgorithm.Create();
```

<span data-ttu-id="27043-111">Dies ist eine Änderung, die nur die Kompilierzeit betrifft.</span><span class="sxs-lookup"><span data-stu-id="27043-111">This is a compile-time only change.</span></span> <span data-ttu-id="27043-112">Hinsichtlich der Laufzeit gibt es keine Änderung im Vergleich zu früheren Versionen von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="27043-112">There is no run-time change from previous versions of .NET Core.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="27043-113">Nur die Überladungen der `Create()`-Methoden ohne Parameter sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="27043-113">Only the parameterless overloads of the `Create()` methods are obsolete.</span></span> <span data-ttu-id="27043-114">Parametrisierte Überladungen sind nicht veraltet und funktionieren weiterhin wie zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="27043-114">Parameterized overloads are not obsolete and still function as expected.</span></span>
>
>   ```csharp
>   // Call Create(string), providing an explicit algorithm family name.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   HashAlgorithm hashAlg = HashAlgorithm.Create("SHA256");
>   ```
>
> - <span data-ttu-id="27043-115">Überladungen ohne Parameter aus *bestimmten* Algorithmusfamilien (keine Abstraktionen) sind nicht veraltet und funktionieren weiterhin wie zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="27043-115">Parameterless overloads of *specific* algorithm families (not abstractions) are not obsolete, and will continue to function as expected.</span></span>
>
>   ```csharp
>   // Call a specific algorithm family's parameterless Create() ctor.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   Aes aesAlg = Aes.Create();
>   ```

#### <a name="reason-for-change"></a><span data-ttu-id="27043-116">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="27043-116">Reason for change</span></span>

<span data-ttu-id="27043-117">Das im .NET Framework vorhandene kryptografische Konfigurationssystem ist in .NET Core und .NET 5.0 und höher nicht mehr vorhanden, da das Legacysystem nicht die erforderliche kryptografische Agilität bieten kann.</span><span class="sxs-lookup"><span data-stu-id="27043-117">The cryptographic configuration system present in .NET Framework is no longer present in .NET Core and .NET 5.0+, since that legacy system doesn't allow for proper cryptographic agility.</span></span> <span data-ttu-id="27043-118">Die Anforderungen von .NET an die Abwärtskompatibilität hindern das Framework außerdem daran, bestimmte kryptografische APIs zu aktualisieren, um bei den Fortschritten der Kryptografie auf dem aktuellen Stand zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="27043-118">.NET's backward-compatibility requirements also prohibit the framework from updating certain cryptographic APIs to keep up with advances in cryptography.</span></span> <span data-ttu-id="27043-119">Die <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>-Methode wurde beispielsweise in .NET Framework 1.0 eingeführt, als der SHA-1-Hashalgorithmus aktuell war.</span><span class="sxs-lookup"><span data-stu-id="27043-119">For example, the <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> method was introduced in .NET Framework 1.0, when the SHA-1 hash algorithm was state-of-the-art.</span></span> <span data-ttu-id="27043-120">Seitdem sind zwanzig Jahre vergangen, und SHA-1 gilt heute als nicht mehr funktionsfähig. <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> kann aber nicht so geändert werden, dass ein anderer Algorithmus zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="27043-120">Twenty years have passed, and now SHA-1 is considered broken, but we cannot change <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> to return a different algorithm.</span></span> <span data-ttu-id="27043-121">Diese Änderung würde einen nicht akzeptablen Breaking Change für das Verwenden von Anwendungen mit sich führen.</span><span class="sxs-lookup"><span data-stu-id="27043-121">Doing so would introduce an unacceptable breaking change in consuming applications.</span></span>

<span data-ttu-id="27043-122">Laut Best Practices müssen Bibliotheken, die Kryptografieprimitive wie AES, SHA-\* und RSA verwenden, die volle Kontrolle darüber haben, wie diese Primitive verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27043-122">Best practice dictates that libraries that consume cryptographic primitives (such as AES, SHA-\*, and RSA) should be in full control over how they consume these primitives.</span></span> <span data-ttu-id="27043-123">Anwendungen, für die zukünftige Überprüfungen erforderlich sind, sollten höhere Bibliotheken verwenden, die diese Primitive einschließen, und Funktionen für Schlüsselverwaltung und kryptografische Agilität hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="27043-123">Applications that require future-proofing should utilize higher-level libraries that wrap these primitives and add key management and cryptographic agility capabilities.</span></span> <span data-ttu-id="27043-124">Diese Bibliotheken werden oft von der Hostingumgebung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="27043-124">These libraries are often provided by the hosting environment.</span></span> <span data-ttu-id="27043-125">Ein Beispiel ist die [Datenschutzbibliothek von ASP.NET](/aspnet/core/security/data-protection/), die diese Bedenken für die aufrufende Anwendung auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="27043-125">One example is [ASP.NET's Data Protection library](/aspnet/core/security/data-protection/), which handles these concerns on behalf of the calling application.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="27043-126">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="27043-126">Version introduced</span></span>

<span data-ttu-id="27043-127">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="27043-127">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="27043-128">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="27043-128">Recommended action</span></span>

- <span data-ttu-id="27043-129">Es wird empfohlen, Aufrufe der jetzt veralteten APIs für bestimmte Algorithmen, z. B. <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>, durch Aufrufe von Factorymethoden zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="27043-129">The recommended course of action is to replace calls to the now-obsolete APIs with calls to factory methods for specific algorithms, for example, <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>.</span></span> <span data-ttu-id="27043-130">So haben Sie die vollständige Kontrolle darüber, welche Algorithmen instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="27043-130">This gives you full control over which algorithms are instantiated.</span></span>

- <span data-ttu-id="27043-131">Wenn Sie die Kompatibilität mit vorhandenen von .NET Framework-Apps generierten Payloads aufrechterhalten müssen, die die nun veralteten APIs verwenden, verwenden Sie die in der folgenden Tabelle vorgeschlagenen Ersetzungen.</span><span class="sxs-lookup"><span data-stu-id="27043-131">If you need to maintain compatibility with existing payloads generated by .NET Framework apps that use the now-obsolete APIs, use the replacements suggested in the following table.</span></span> <span data-ttu-id="27043-132">Die Tabelle liefert Ihnen eine Zuordnung von Standardalgorithmen des .NET Frameworks zu ihren Entsprechungen in .NET 5 und höher.</span><span class="sxs-lookup"><span data-stu-id="27043-132">The table provides a mapping from .NET Framework default algorithms to their .NET 5+ equivalents.</span></span>

  | <span data-ttu-id="27043-133">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="27043-133">.NET Framework</span></span> | <span data-ttu-id="27043-134">Mit .NET Core/.NET 5.0 und höher kompatible Ersetzung</span><span class="sxs-lookup"><span data-stu-id="27043-134">.NET Core / .NET 5.0+ compatible replacement</span></span> | <span data-ttu-id="27043-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="27043-135">Remarks</span></span> |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | <span data-ttu-id="27043-136">Der SHA-1-Algorithmus gilt als nicht mehr nutzbar.</span><span class="sxs-lookup"><span data-stu-id="27043-136">The SHA-1 algorithm is considered broken.</span></span> <span data-ttu-id="27043-137">Sie sollten wenn möglich einen stärkeren Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="27043-137">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="27043-138">Wenden Sie sich an Ihren Sicherheitsberater, um weitere Schritte abzusprechen.</span><span class="sxs-lookup"><span data-stu-id="27043-138">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | <span data-ttu-id="27043-139">Der HMACSHA1-Algorithmus sollte für die meisten modernen Anwendungen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27043-139">The HMACSHA1 algorithm is discouraged for most modern applications.</span></span> <span data-ttu-id="27043-140">Sie sollten wenn möglich einen stärkeren Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="27043-140">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="27043-141">Wenden Sie sich an Ihren Sicherheitsberater, um weitere Schritte abzusprechen.</span><span class="sxs-lookup"><span data-stu-id="27043-141">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | <span data-ttu-id="27043-142">Der HMACSHA1-Algorithmus sollte für die meisten modernen Anwendungen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27043-142">The HMACSHA1 algorithm is discouraged for most modern applications.</span></span> <span data-ttu-id="27043-143">Sie sollten wenn möglich einen stärkeren Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="27043-143">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="27043-144">Wenden Sie sich an Ihren Sicherheitsberater, um weitere Schritte abzusprechen.</span><span class="sxs-lookup"><span data-stu-id="27043-144">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

- <span data-ttu-id="27043-145">Wenn Sie die veralteten `Create()`-Überladungen ohne Parameter weiterhin aufrufen müssen, können Sie die `SYSLIB0007`-Warnung im Code unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="27043-145">If you must continue to call the obsolete parameterless `Create()` overloads, you can suppress the `SYSLIB0007` warning in code.</span></span>

  ```csharp
  #pragma warning disable SYSLIB0007 // Disable the warning.
  HashAlgorithm alg = HashAlgorithm.Create(); // Still throws PNSE.
  #pragma warning restore SYSLIB0007 // Re-enable the warning.
  ```

  <span data-ttu-id="27043-146">Sie können die Warnung auch in der Projektdatei unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="27043-146">You can also suppress the warning in your project file.</span></span> <span data-ttu-id="27043-147">Wenn Sie dies tun, wird die Warnung für alle Quelldateien im Projekt deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="27043-147">Doing so disables the warning for all source files within the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0007 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0007</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > <span data-ttu-id="27043-148">Ein Unterdrücken von `SYSLIB0007` deaktiviert nur die Veraltungswarnungen für die hier aufgeführten Kryptografie-APIs.</span><span class="sxs-lookup"><span data-stu-id="27043-148">Suppressing `SYSLIB0007` disables only the obsoletion warnings for the cryptography APIs listed here.</span></span> <span data-ttu-id="27043-149">Andere Warnungen werden nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="27043-149">It does not disable any other warnings.</span></span> <span data-ttu-id="27043-150">Zusätzlich lösen diese veralteten APIs zur Laufzeit weiterhin eine <xref:System.PlatformNotSupportedException>-Ausnahme aus, selbst wenn Sie die Warnung unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="27043-150">Additionally, even if you suppress the warning, these obsoleted APIs will still throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

#### <a name="category"></a><span data-ttu-id="27043-151">Kategorie</span><span class="sxs-lookup"><span data-stu-id="27043-151">Category</span></span>

- <span data-ttu-id="27043-152">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="27043-152">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="27043-153">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="27043-153">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.AsymmetricAlgorithm.Create`
- `M:System.Security.Cryptography.HashAlgorithm.Create`
- `M:System.Security.Cryptography.HMAC.Create`
- `M:System.Security.Cryptography.KeyedHashAlgorithm.Create`
- `M:System.Security.Cryptography.SymmetricAlgorithm.Create`

-->
