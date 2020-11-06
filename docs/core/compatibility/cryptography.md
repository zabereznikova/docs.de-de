---
title: Breaking Changes bei der Kryptografie
description: Listet die Breaking Changes bei der Kryptografie in .NET Core auf.
ms.date: 04/22/2020
ms.openlocfilehash: b755876624a7709cfe08b5993655e78be9f8e1f2
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888611"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="cfaaf-103">Breaking Changes bei der Kryptografie</span><span class="sxs-lookup"><span data-stu-id="cfaaf-103">Cryptography breaking changes</span></span>

<span data-ttu-id="cfaaf-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="cfaaf-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="cfaaf-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="cfaaf-105">Breaking change</span></span> | <span data-ttu-id="cfaaf-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="cfaaf-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="cfaaf-107">Der Standardwert für FeedbackSize für mit TripleDES.Create erstellte Instanzen wurde geändert</span><span class="sxs-lookup"><span data-stu-id="cfaaf-107">Default FeedbackSize value for instances created by TripleDES.Create changed</span></span>](#default-feedbacksize-value-for-instances-created-by-tripledescreate-changed) | <span data-ttu-id="cfaaf-108">5.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-108">5.0</span></span> |
| [<span data-ttu-id="cfaaf-109">Das Instanziieren von Standardimplementierungen kryptografischer Abstraktionen wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="cfaaf-109">Instantiating default implementations of cryptographic abstractions is not supported</span></span>](#instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported) | <span data-ttu-id="cfaaf-110">5.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-110">5.0</span></span> |
| [<span data-ttu-id="cfaaf-111">TLS-Standardverschlüsselungssuites für .NET unter Linux</span><span class="sxs-lookup"><span data-stu-id="cfaaf-111">Default TLS cipher suites for .NET on Linux</span></span>](#default-tls-cipher-suites-for-net-on-linux) | <span data-ttu-id="cfaaf-112">5.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-112">5.0</span></span> |
| [<span data-ttu-id="cfaaf-113">System.Security.Cryptography-APIs werden in Blazor WebAssembly nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="cfaaf-113">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | <span data-ttu-id="cfaaf-114">5.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-114">5.0</span></span> |
| [<span data-ttu-id="cfaaf-115">Funktionalität von System.Security.Cryptography.Oid mit init-only-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cfaaf-115">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="cfaaf-116">5.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-116">5.0</span></span> |
| [<span data-ttu-id="cfaaf-117">BEGIN TRUSTED CERTIFICATE-Syntax nicht mehr für Stammzertifikate unter Linux unterstützt</span><span class="sxs-lookup"><span data-stu-id="cfaaf-117">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="cfaaf-118">3.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-118">3.0</span></span> |
| [<span data-ttu-id="cfaaf-119">EnvelopedCms verwendet standardmäßig AES-256-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="cfaaf-119">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="cfaaf-120">3.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-120">3.0</span></span> |
| [<span data-ttu-id="cfaaf-121">Die Mindestgröße für die Generierung von RSAOpenSsl-Schlüsseln wurde heraufgesetzt</span><span class="sxs-lookup"><span data-stu-id="cfaaf-121">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="cfaaf-122">3.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-122">3.0</span></span> |
| [<span data-ttu-id="cfaaf-123">.NET Core 3.0 zieht OpenSSL 1.1.x OpenSSL 1.0.x vor</span><span class="sxs-lookup"><span data-stu-id="cfaaf-123">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="cfaaf-124">3.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-124">3.0</span></span> |
| [<span data-ttu-id="cfaaf-125">CryptoStream.Dispose transformiert den abschließenden Block nur beim Schreiben</span><span class="sxs-lookup"><span data-stu-id="cfaaf-125">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="cfaaf-126">3.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-126">3.0</span></span> |
| [<span data-ttu-id="cfaaf-127">Der boolesche Parameter von SignedCms.ComputeSignature wird beachtet</span><span class="sxs-lookup"><span data-stu-id="cfaaf-127">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="cfaaf-128">2.1</span><span class="sxs-lookup"><span data-stu-id="cfaaf-128">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="cfaaf-129">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-129">.NET 5.0</span></span>

[!INCLUDE [tripledes-default-feedback-size-change](../../../includes/core-changes/cryptography/5.0/tripledes-default-feedback-size-change.md)]

***

[!INCLUDE [instantiating-default-implementations-of-cryptographic-abstractions-not-supported](../../../includes/core-changes/cryptography/5.0/instantiating-default-implementations-of-cryptographic-abstractions-not-supported.md)]

<span data-ttu-id="cfaaf-130">\*\*_</span><span class="sxs-lookup"><span data-stu-id="cfaaf-130">\*\*_</span></span>

[!INCLUDE [default-cipher-suites-for-tls-on-linux](../../../includes/core-changes/cryptography/5.0/default-cipher-suites-for-tls-on-linux.md)]

_*_

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

_*_

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="cfaaf-131">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cfaaf-131">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

_*_

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

_*_

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

_*_

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

_*_

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="cfaaf-132">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cfaaf-132">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

<span data-ttu-id="cfaaf-133">_\*\*</span><span class="sxs-lookup"><span data-stu-id="cfaaf-133">_\*\*</span></span>
