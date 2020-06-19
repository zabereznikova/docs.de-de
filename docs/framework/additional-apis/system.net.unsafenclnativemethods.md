---
title: Unsafenclnativemethods-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.UnsafeNclNativeMethods
- System.Net.UnsafeNclNativeMethods.NativePKI
- System.Net.UnsafeNclNativeMethods.NativePKI.FindClientCertificates
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 46756a0d1d69b4768dbb8dcdd7ab098d3f1849bf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990447"
---
# <a name="unsafenclnativemethods-class"></a><span data-ttu-id="d8f42-102">Unsafenclnativemethods-Klasse</span><span class="sxs-lookup"><span data-stu-id="d8f42-102">UnsafeNclNativeMethods class</span></span>

<span data-ttu-id="d8f42-103">Enthält Klassen, die unsichere Native Netzwerk Methoden importieren.</span><span class="sxs-lookup"><span data-stu-id="d8f42-103">Contains classes that import unsafe native networking methods.</span></span> <span data-ttu-id="d8f42-104">Diese Klasse kann nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="d8f42-104">This class cannot be inherited.</span></span>

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> <span data-ttu-id="d8f42-105">Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8f42-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d8f42-106">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="d8f42-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="nativepki-class"></a><span data-ttu-id="d8f42-107">Nativepki-Klasse</span><span class="sxs-lookup"><span data-stu-id="d8f42-107">NativePKI class</span></span>

<span data-ttu-id="d8f42-108">Enthält Methoden, die aus crypt32.dll importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d8f42-108">Contains methods imported from crypt32.dll.</span></span> <span data-ttu-id="d8f42-109">Diese Methoden behandeln Zertifikate bei der Verwendung von Hypertext Transfer Protocol Secure (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="d8f42-109">These methods handle certificates when using Hypertext Transfer Protocol Secure (HTTPS).</span></span> <span data-ttu-id="d8f42-110">Diese Klasse kann nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="d8f42-110">This class cannot be inherited.</span></span>

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a><span data-ttu-id="d8f42-111">Nativepki. findclientzertifikate-Methode</span><span class="sxs-lookup"><span data-stu-id="d8f42-111">NativePKI.FindClientCertificates method</span></span>

<span data-ttu-id="d8f42-112">Ermittelt verfügbare Client Zertifikate, die an den Server gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d8f42-112">Discovers available client certificates to send to the server.</span></span>

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a><span data-ttu-id="d8f42-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d8f42-113">Return value</span></span>

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

<span data-ttu-id="d8f42-114">Eine Sammlung verfügbarer Client Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="d8f42-114">A collection of available client certificates.</span></span>

## <a name="requirements"></a><span data-ttu-id="d8f42-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d8f42-115">Requirements</span></span>

<span data-ttu-id="d8f42-116">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d8f42-116">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d8f42-117">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="d8f42-117">**Assembly:** System (in System.dll)</span></span>
