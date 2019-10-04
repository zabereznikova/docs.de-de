---
title: Breaking Changes bei der Kryptografie – .NET Core
description: Listet die Breaking Changes bei der Kryptografie in .NET Core auf.
ms.date: 09/20/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80b62f9b32487e88a309ea7686f78d68af8f2e0a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216984"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="4f437-103">Breaking Changes bei der Kryptografie</span><span class="sxs-lookup"><span data-stu-id="4f437-103">Cryptography breaking changes</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f437-104">Dieser Artikel wird aktuell überarbeitet.</span><span class="sxs-lookup"><span data-stu-id="4f437-104">This article is under construction.</span></span> <span data-ttu-id="4f437-105">Nicht alle Breaking Changes für .NET Core werden hier aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4f437-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="4f437-106">Weitere Informationen zu Breaking Changes für .NET Core finden Sie in den jeweiligen [Issues zu Breaking Changes](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) im Repository „dotnet/docs“ auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="4f437-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="4f437-107">Im Folgenden sind die Breaking Changes bei der Kryptografie in .NET Core aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4f437-107">The following is a list of cryptography-related breaking changes by .NET Core version.</span></span>

## <a name="net-core-30-preview-9"></a><span data-ttu-id="4f437-108">.NET Core 3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="4f437-108">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

## <a name="net-core-30"></a><span data-ttu-id="4f437-109">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4f437-109">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/net-core-3-0-prefers-openssl-1-1-x.md)]
