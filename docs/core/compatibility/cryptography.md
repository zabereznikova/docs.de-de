---
title: Breaking Changes bei der Kryptografie
description: Listet die Breaking Changes bei der Kryptografie in .NET Core auf.
ms.date: 04/22/2020
ms.openlocfilehash: 621a3dad28b67ee33056dce3df0379efaeb90776
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065102"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="82312-103">Breaking Changes bei der Kryptografie</span><span class="sxs-lookup"><span data-stu-id="82312-103">Cryptography breaking changes</span></span>

<span data-ttu-id="82312-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="82312-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="82312-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="82312-105">Breaking change</span></span> | <span data-ttu-id="82312-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="82312-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="82312-107">Funktionalität von System.Security.Cryptography.Oid mit init-only-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="82312-107">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="82312-108">5.0</span><span class="sxs-lookup"><span data-stu-id="82312-108">5.0</span></span> |
| [<span data-ttu-id="82312-109">BEGIN TRUSTED CERTIFICATE-Syntax nicht mehr für Stammzertifikate unter Linux unterstützt</span><span class="sxs-lookup"><span data-stu-id="82312-109">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="82312-110">3.0</span><span class="sxs-lookup"><span data-stu-id="82312-110">3.0</span></span> |
| [<span data-ttu-id="82312-111">EnvelopedCms verwendet standardmäßig AES-256-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="82312-111">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="82312-112">3.0</span><span class="sxs-lookup"><span data-stu-id="82312-112">3.0</span></span> |
| [<span data-ttu-id="82312-113">Die Mindestgröße für die Generierung von RSAOpenSsl-Schlüsseln wurde heraufgesetzt</span><span class="sxs-lookup"><span data-stu-id="82312-113">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="82312-114">3.0</span><span class="sxs-lookup"><span data-stu-id="82312-114">3.0</span></span> |
| [<span data-ttu-id="82312-115">.NET Core 3.0 zieht OpenSSL 1.1.x OpenSSL 1.0.x vor</span><span class="sxs-lookup"><span data-stu-id="82312-115">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="82312-116">3.0</span><span class="sxs-lookup"><span data-stu-id="82312-116">3.0</span></span> |
| [<span data-ttu-id="82312-117">CryptoStream.Dispose transformiert den abschließenden Block nur beim Schreiben</span><span class="sxs-lookup"><span data-stu-id="82312-117">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="82312-118">3.0</span><span class="sxs-lookup"><span data-stu-id="82312-118">3.0</span></span> |
| [<span data-ttu-id="82312-119">Der boolesche Parameter von SignedCms.ComputeSignature wird beachtet</span><span class="sxs-lookup"><span data-stu-id="82312-119">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="82312-120">2.1</span><span class="sxs-lookup"><span data-stu-id="82312-120">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="82312-121">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="82312-121">.NET 5.0</span></span>

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="82312-122">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="82312-122">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="82312-123">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="82312-123">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
