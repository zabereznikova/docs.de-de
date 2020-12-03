---
title: Breaking Changes bei der Kryptografie
description: Liste der Breaking Changes bei der Kryptografie in .NET Core 2.1–3.0
ms.date: 04/22/2020
ms.openlocfilehash: a4801bb4d5a859e2c8c2b536ee0597cb4db2f65d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682652"
---
# <a name="cryptography-breaking-changes-for-net-core-21-30"></a><span data-ttu-id="51504-103">Breaking Changes bei der Kryptografie für .NET Core 2.1–3.0</span><span class="sxs-lookup"><span data-stu-id="51504-103">Cryptography breaking changes for .NET Core 2.1-3.0</span></span>

<span data-ttu-id="51504-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="51504-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="51504-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="51504-105">Breaking change</span></span> | <span data-ttu-id="51504-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="51504-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="51504-107">BEGIN TRUSTED CERTIFICATE-Syntax nicht mehr für Stammzertifikate unter Linux unterstützt</span><span class="sxs-lookup"><span data-stu-id="51504-107">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="51504-108">3.0</span><span class="sxs-lookup"><span data-stu-id="51504-108">3.0</span></span> |
| [<span data-ttu-id="51504-109">EnvelopedCms verwendet standardmäßig AES-256-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="51504-109">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="51504-110">3.0</span><span class="sxs-lookup"><span data-stu-id="51504-110">3.0</span></span> |
| [<span data-ttu-id="51504-111">Die Mindestgröße für die Generierung von RSAOpenSsl-Schlüsseln wurde heraufgesetzt</span><span class="sxs-lookup"><span data-stu-id="51504-111">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="51504-112">3.0</span><span class="sxs-lookup"><span data-stu-id="51504-112">3.0</span></span> |
| [<span data-ttu-id="51504-113">.NET Core 3.0 zieht OpenSSL 1.1.x OpenSSL 1.0.x vor</span><span class="sxs-lookup"><span data-stu-id="51504-113">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="51504-114">3.0</span><span class="sxs-lookup"><span data-stu-id="51504-114">3.0</span></span> |
| [<span data-ttu-id="51504-115">CryptoStream.Dispose transformiert den abschließenden Block nur beim Schreiben</span><span class="sxs-lookup"><span data-stu-id="51504-115">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="51504-116">3.0</span><span class="sxs-lookup"><span data-stu-id="51504-116">3.0</span></span> |
| [<span data-ttu-id="51504-117">Der boolesche Parameter von SignedCms.ComputeSignature wird beachtet</span><span class="sxs-lookup"><span data-stu-id="51504-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="51504-118">2.1</span><span class="sxs-lookup"><span data-stu-id="51504-118">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="51504-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="51504-119">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

<span data-ttu-id="51504-120">\*\*_</span><span class="sxs-lookup"><span data-stu-id="51504-120">\*\*_</span></span>

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

_*_

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

_*_

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="51504-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="51504-121">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

<span data-ttu-id="51504-122">_\*\*</span><span class="sxs-lookup"><span data-stu-id="51504-122">_\*\*</span></span>
