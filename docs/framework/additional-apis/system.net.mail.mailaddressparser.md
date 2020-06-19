---
title: Mailadressssparser-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.MailAddressParser
- System.Net.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 2c17970614ff9b6f1e6793a064a956da7248d693
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990455"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="a0896-102">Mailadressssparser-Klasse</span><span class="sxs-lookup"><span data-stu-id="a0896-102">MailAddressParser class</span></span>

<span data-ttu-id="a0896-103">Analysiert e-Mail-Adressen, wie in RFC 2822 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0896-103">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="a0896-104">Diese Klasse kann nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="a0896-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="a0896-105">Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0896-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a0896-106">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="a0896-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="a0896-107">Methode "samanaddress"</span><span class="sxs-lookup"><span data-stu-id="a0896-107">ParseAddress method</span></span>

<span data-ttu-id="a0896-108">Analysiert eine einzelne e-Mail-Adresse aus der angegebenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a0896-108">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="a0896-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0896-109">Parameters</span></span>

<span data-ttu-id="a0896-110">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a0896-110">`data` <xref:System.String></span></span>

<span data-ttu-id="a0896-111">Die Zeichenfolge, die eine e-Mail-Adresse enthält, die analysiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0896-111">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="a0896-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0896-112">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="a0896-113">Eine gültige e-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="a0896-113">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="a0896-114">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="a0896-114">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="a0896-115">Die e-Mail-Adresse ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a0896-115">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0896-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a0896-116">Requirements</span></span>

<span data-ttu-id="a0896-117">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a0896-117">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a0896-118">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="a0896-118">**Assembly:** System (in System.dll)</span></span>
