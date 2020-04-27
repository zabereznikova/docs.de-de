---
ms.openlocfilehash: 8790637c31d503455eb8ba722cca827c2a24b7c9
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021458"
---
### <a name="openssl-versions-on-macos"></a><span data-ttu-id="705ee-101">OpenSSL-Versionen unter macOS</span><span class="sxs-lookup"><span data-stu-id="705ee-101">OpenSSL versions on macOS</span></span>

<span data-ttu-id="705ee-102">Die Runtimes von .NET Core 3.0 und höher unter macOS bevorzugen jetzt OpenSSL 1.1.x-Versionen gegenüber OpenSSL 1.0.x-Versionen für die Typen <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> und <xref:System.Security.Cryptography.SafeEvpPKeyHandle>.</span><span class="sxs-lookup"><span data-stu-id="705ee-102">The .NET Core 3.0 and later runtimes on macOS now prefer OpenSSL 1.1.x versions to OpenSSL 1.0.x versions for the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, and <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

<span data-ttu-id="705ee-103">Die .NET Core 2.1-Runtime unterstützt jetzt OpenSSL 1.1.x-Versionen, bevorzugt aber immer noch OpenSSL 1.0.x-Versionen.</span><span class="sxs-lookup"><span data-stu-id="705ee-103">The .NET Core 2.1 runtime now supports OpenSSL 1.1.x versions, but still prefers OpenSSL 1.0.x versions.</span></span>

#### <a name="change-description"></a><span data-ttu-id="705ee-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="705ee-104">Change description</span></span>

<span data-ttu-id="705ee-105">Zuvor verwendete die .NET Core-Runtime OpenSSL 1.0.x-Versionen unter macOS für Typen, die mit OpenSSL interagieren.</span><span class="sxs-lookup"><span data-stu-id="705ee-105">Previously, the .NET Core runtime used OpenSSL 1.0.x versions on macOS for types that interact with OpenSSL.</span></span> <span data-ttu-id="705ee-106">Die neueste Version von OpenSSL 1.0.x, OpenSSL 1.0.2, wird jetzt nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="705ee-106">The most recent OpenSSL 1.0.x version, OpenSSL 1.0.2, is now out of support.</span></span> <span data-ttu-id="705ee-107">Um Typen, die OpenSSL auf unterstützten Versionen von OpenSSL verwenden, beizubehalten, verwenden die .NET Core 3.0 und spätere Runtimes jetzt neuere Versionen von OpenSSL unter macOS.</span><span class="sxs-lookup"><span data-stu-id="705ee-107">To keep types that use OpenSSL on supported versions of OpenSSL, the .NET Core 3.0 and later runtimes now use newer versions of OpenSSL on macOS.</span></span>

<span data-ttu-id="705ee-108">Mit dieser Änderung sieht das Verhalten für die .NET Core-Runtimes unter macOS wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="705ee-108">With this change, the behavior for the .NET Core runtimes on macOS is as follows:</span></span>

- <span data-ttu-id="705ee-109">Die Runtimes von .NET Core 3.0 und höheren Versionen verwenden OpenSSL 1.1.x, falls verfügbar, und greifen nur dann auf OpenSSL 1.0.x zurück, wenn keine 1.1.x-Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="705ee-109">The .NET Core 3.0 and later version runtimes use OpenSSL 1.1.x, if available, and fall back to OpenSSL 1.0.x only if there's no 1.1.x version available.</span></span>

  <span data-ttu-id="705ee-110">Für Aufrufer, die die OpenSSL-Interop-Typen mit benutzerdefinierten P/Invokes verwenden, befolgen Sie die Anleitung in den <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="705ee-110">For callers that use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span> <span data-ttu-id="705ee-111">Ihre App stürzt möglicherweise ab, wenn Sie den <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion>-Wert nicht überprüfen.</span><span class="sxs-lookup"><span data-stu-id="705ee-111">Your app may crash if you don't check the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> value.</span></span>

- <span data-ttu-id="705ee-112">Die Runtime von .NET Core 2.1 verwendet OpenSSL 1.0.x, falls verfügbar, und greift auf OpenSSL 1.1.x zurück, wenn keine 1.0.x-Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="705ee-112">The .NET Core 2.1 runtime uses OpenSSL 1.0.x, if available, and falls back to OpenSSL 1.1.x if there's no 1.0.x version available.</span></span>

  <span data-ttu-id="705ee-113">Die 2.1-Runtime bevorzugt die frühere Version von OpenSSL, da die <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>-Eigenschaft in .NET Core 2.1 nicht existiert, sodass die OpenSSL-Version zur Laufzeit nicht zuverlässig ermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="705ee-113">The 2.1 runtime prefers the earlier version of OpenSSL because the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property does not exist in .NET Core 2.1, so the OpenSSL version cannot be reliably determined at run time.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="705ee-114">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="705ee-114">Version introduced</span></span>

- <span data-ttu-id="705ee-115">.NET Core 2.1.16</span><span class="sxs-lookup"><span data-stu-id="705ee-115">.NET Core 2.1.16</span></span>
- <span data-ttu-id="705ee-116">.NET Core 3.0.3</span><span class="sxs-lookup"><span data-stu-id="705ee-116">.NET Core 3.0.3</span></span>
- <span data-ttu-id="705ee-117">.NET Core 3.1.2</span><span class="sxs-lookup"><span data-stu-id="705ee-117">.NET Core 3.1.2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="705ee-118">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="705ee-118">Recommended action</span></span>

- <span data-ttu-id="705ee-119">Deinstallieren Sie OpenSSL, Version 1.0.2, wenn es nicht mehr benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="705ee-119">Uninstall OpenSSL version 1.0.2 if it's no longer needed.</span></span>

- <span data-ttu-id="705ee-120">Installieren Sie OpenSSL 1.1.x, wenn Sie die Typen <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> oder <xref:System.Security.Cryptography.SafeEvpPKeyHandle> verwenden.</span><span class="sxs-lookup"><span data-stu-id="705ee-120">Install OpenSSL 1.1.x if you use the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, or <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

- <span data-ttu-id="705ee-121">Wenn Sie die OpenSSL-Interop-Typen mit benutzerdefinierten P/Invokes verwenden, befolgen Sie die Anleitung in den <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="705ee-121">If you use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span>

#### <a name="category"></a><span data-ttu-id="705ee-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="705ee-122">Category</span></span>

<span data-ttu-id="705ee-123">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="705ee-123">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="705ee-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="705ee-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->
