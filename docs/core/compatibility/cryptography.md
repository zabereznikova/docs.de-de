---
title: Breaking Changes bei der Kryptografie
description: Listet die Breaking Changes bei der Kryptografie in .NET Core auf.
ms.date: 04/22/2020
ms.openlocfilehash: 667d983fc6f2592c2169f97d328cd7947c8bcc81
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406145"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="129cd-103">Breaking Changes bei der Kryptografie</span><span class="sxs-lookup"><span data-stu-id="129cd-103">Cryptography breaking changes</span></span>

<span data-ttu-id="129cd-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="129cd-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="129cd-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="129cd-105">Breaking change</span></span> | <span data-ttu-id="129cd-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="129cd-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="129cd-107">System.Security.Cryptography-APIs werden in Blazor WebAssembly nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="129cd-107">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | <span data-ttu-id="129cd-108">5.0</span><span class="sxs-lookup"><span data-stu-id="129cd-108">5.0</span></span> |
| [<span data-ttu-id="129cd-109">Funktionalität von System.Security.Cryptography.Oid mit init-only-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="129cd-109">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="129cd-110">5.0</span><span class="sxs-lookup"><span data-stu-id="129cd-110">5.0</span></span> |
| [<span data-ttu-id="129cd-111">BEGIN TRUSTED CERTIFICATE-Syntax nicht mehr für Stammzertifikate unter Linux unterstützt</span><span class="sxs-lookup"><span data-stu-id="129cd-111">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="129cd-112">3.0</span><span class="sxs-lookup"><span data-stu-id="129cd-112">3.0</span></span> |
| [<span data-ttu-id="129cd-113">EnvelopedCms verwendet standardmäßig AES-256-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="129cd-113">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="129cd-114">3.0</span><span class="sxs-lookup"><span data-stu-id="129cd-114">3.0</span></span> |
| [<span data-ttu-id="129cd-115">Die Mindestgröße für die Generierung von RSAOpenSsl-Schlüsseln wurde heraufgesetzt</span><span class="sxs-lookup"><span data-stu-id="129cd-115">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="129cd-116">3.0</span><span class="sxs-lookup"><span data-stu-id="129cd-116">3.0</span></span> |
| [<span data-ttu-id="129cd-117">.NET Core 3.0 zieht OpenSSL 1.1.x OpenSSL 1.0.x vor</span><span class="sxs-lookup"><span data-stu-id="129cd-117">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="129cd-118">3.0</span><span class="sxs-lookup"><span data-stu-id="129cd-118">3.0</span></span> |
| [<span data-ttu-id="129cd-119">CryptoStream.Dispose transformiert den abschließenden Block nur beim Schreiben</span><span class="sxs-lookup"><span data-stu-id="129cd-119">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="129cd-120">3.0</span><span class="sxs-lookup"><span data-stu-id="129cd-120">3.0</span></span> |
| [<span data-ttu-id="129cd-121">Der boolesche Parameter von SignedCms.ComputeSignature wird beachtet</span><span class="sxs-lookup"><span data-stu-id="129cd-121">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="129cd-122">2.1</span><span class="sxs-lookup"><span data-stu-id="129cd-122">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="129cd-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="129cd-123">.NET 5.0</span></span>

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

***

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="129cd-124">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="129cd-124">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="129cd-125">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="129cd-125">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
