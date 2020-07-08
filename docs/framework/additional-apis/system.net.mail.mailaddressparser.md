---
title: Mailadressssparser-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ff83f6946539fa262ccde980052627f98c75601d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051349"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="2c6b2-102">MailAddressParser-Klasse</span><span class="sxs-lookup"><span data-stu-id="2c6b2-102">MailAddressParser class</span></span>

<span data-ttu-id="2c6b2-103">Analysiert e-Mail-Adressen, wie in RFC 2822 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-103">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="2c6b2-104">Diese Klasse kann nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="2c6b2-105">Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2c6b2-106">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="2c6b2-107">Methode "samanaddress"</span><span class="sxs-lookup"><span data-stu-id="2c6b2-107">ParseAddress method</span></span>

<span data-ttu-id="2c6b2-108">Analysiert eine einzelne e-Mail-Adresse aus der angegebenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-108">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="2c6b2-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c6b2-109">Parameters</span></span>

<span data-ttu-id="2c6b2-110">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="2c6b2-110">`data` <xref:System.String></span></span>

<span data-ttu-id="2c6b2-111">Die Zeichenfolge, die eine e-Mail-Adresse enthält, die analysiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-111">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="2c6b2-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c6b2-112">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="2c6b2-113">Eine gültige e-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-113">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="2c6b2-114">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="2c6b2-114">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="2c6b2-115">Die e-Mail-Adresse ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-115">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="2c6b2-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2c6b2-116">Requirements</span></span>

<span data-ttu-id="2c6b2-117">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2c6b2-117">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2c6b2-118">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="2c6b2-118">**Assembly:** System (in System.dll)</span></span>
