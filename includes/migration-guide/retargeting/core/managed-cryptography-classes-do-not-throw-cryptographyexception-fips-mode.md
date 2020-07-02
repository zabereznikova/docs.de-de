---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616253"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a><span data-ttu-id="029b0-101">Verwaltete Kryptografieklassen lösen im FIPS-Modus keine CryptographyException aus</span><span class="sxs-lookup"><span data-stu-id="029b0-101">Managed cryptography classes do not throw a CryptographyException in FIPS mode</span></span>

#### <a name="details"></a><span data-ttu-id="029b0-102">Details</span><span class="sxs-lookup"><span data-stu-id="029b0-102">Details</span></span>

<span data-ttu-id="029b0-103">In .NET Framework 4.7.2 und früheren Versionen lösen verwaltete Kryptografieanbieterklassen wie <xref:System.Security.Cryptography.SHA256Managed> eine Ausnahme des Typs <xref:System.Security.Cryptography.CryptographicException> aus, wenn die kryptografischen Systembibliotheken im FIPS-Modus konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="029b0-103">In .NET Framework 4.7.2 and earlier versions, managed cryptographic provider classes such as <xref:System.Security.Cryptography.SHA256Managed> throw a <xref:System.Security.Cryptography.CryptographicException> when the system cryptographic libraries are configured in FIPS mode.</span></span> <span data-ttu-id="029b0-104">Diese Ausnahmen werden ausgelöst, da die verwalteten Versionen nicht gemäß FIPS 140-2 (Federal Information Processing Standards) zertifiziert sind. Zudem werden Kryptografiealgorithmen blockiert, die im Sinne der FIPS-Regeln als nicht genehmigt galten.</span><span class="sxs-lookup"><span data-stu-id="029b0-104">These exceptions are thrown because the managed versions have not undergone FIPS (Federal Information Processing Standards) 140-2 certification, as well as to block cryptographic algorithms that were not considered to be approved based on the FIPS rules.</span></span>  <span data-ttu-id="029b0-105">Da nur wenige Entwickler ihre Entwicklungscomputer im FIPS-Modus betreiben, werden diese Ausnahmen regelmäßig nur bei Produktionssystemen ausgelöst. Anwendungen, die .NET Framework 4.8 und höhere Versionen verwenden, wechseln automatisch zur neueren, gelockerten Richtlinie, sodass <xref:System.Security.Cryptography.CryptographicException> in diesen Fällen nicht mehr standardmäßig ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="029b0-105">Because few developers have their development machines in FIPS mode, these exceptions are frequently thrown only on production systems.Applications that target .NET Framework 4.8 and later versions automatically switch to the newer, relaxed policy, so that a <xref:System.Security.Cryptography.CryptographicException> is no longer thrown by default in such cases.</span></span> <span data-ttu-id="029b0-106">Stattdessen leiten die verwalteten Kryptografieklassen kryptografische Vorgänge an eine kryptografische Systembibliothek weiter.</span><span class="sxs-lookup"><span data-stu-id="029b0-106">Instead, the managed cryptography classes redirect cryptographic operations to a system cryptography library.</span></span> <span data-ttu-id="029b0-107">Durch diese Richtlinienänderung wird ein möglicherweise verwirrender Unterschied zwischen Entwicklungs- und Produktionsumgebungen beseitigt, und native Komponenten und verwaltete Komponenten werden gemäß derselben Kryptografierichtlinie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="029b0-107">This policy change effectively removes a potentially confusing difference between developer environments and the production environments and makes native components and managed components operate under the same cryptographic policy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="029b0-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="029b0-108">Suggestion</span></span>

<span data-ttu-id="029b0-109">Wenn dieses Verhalten nicht erwünscht ist, können Sie sich dagegen entscheiden und das vorherige Verhalten wiederherstellen, sodass <xref:System.Security.Cryptography.CryptographicException> im FIPS-Modus ausgelöst wird, indem Sie die folgende [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Konfigurationseinstellung im Abschnitt [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Konfigurationsdatei Ihrer Anwendung hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="029b0-109">If this behavior is undesirable, you can opt out of it and restore the previous behavior so that a <xref:System.Security.Cryptography.CryptographicException> is thrown in FIPS mode by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

<span data-ttu-id="029b0-110">Wenn Ihre Anwendung .NET Framework 4.7.2 oder frühere Versionen verwendet, können Sie diese Änderung aktivieren, indem Sie die folgende [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Konfigurationseinstellung im Abschnitt [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Konfigurationsdatei Ihrer Anwendung hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="029b0-110">If your application targets .NET Framework 4.7.2 or earlier, you can also opt in to this change by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| <span data-ttu-id="029b0-111">name</span><span class="sxs-lookup"><span data-stu-id="029b0-111">Name</span></span>    | <span data-ttu-id="029b0-112">Wert</span><span class="sxs-lookup"><span data-stu-id="029b0-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="029b0-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="029b0-113">Scope</span></span>   | <span data-ttu-id="029b0-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="029b0-114">Edge</span></span>        |
| <span data-ttu-id="029b0-115">Version</span><span class="sxs-lookup"><span data-stu-id="029b0-115">Version</span></span> | <span data-ttu-id="029b0-116">4.8</span><span class="sxs-lookup"><span data-stu-id="029b0-116">4.8</span></span>         |
| <span data-ttu-id="029b0-117">Typ</span><span class="sxs-lookup"><span data-stu-id="029b0-117">Type</span></span>    | <span data-ttu-id="029b0-118">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="029b0-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="029b0-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="029b0-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>
