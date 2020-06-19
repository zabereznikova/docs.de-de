---
title: HttpStatus Description-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990476"
---
# <a name="httpstatusdescription-class"></a><span data-ttu-id="9b14d-102">HttpStatus Description-Klasse</span><span class="sxs-lookup"><span data-stu-id="9b14d-102">HttpStatusDescription class</span></span>

<span data-ttu-id="9b14d-103">Stellt standardmäßige HTTP-Status Beschreibungen bereit.</span><span class="sxs-lookup"><span data-stu-id="9b14d-103">Provides standard HTTP status descriptions.</span></span> <span data-ttu-id="9b14d-104">Diese Klasse kann nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="9b14d-104">This class cannot be inherited.</span></span>

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> <span data-ttu-id="9b14d-105">Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b14d-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="9b14d-106">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="9b14d-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="get-method"></a><span data-ttu-id="9b14d-107">Get-Methode</span><span class="sxs-lookup"><span data-stu-id="9b14d-107">Get method</span></span>

<span data-ttu-id="9b14d-108">Gibt die Beschreibung zurück, die dem angegebenen HTTP-Statuscode zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9b14d-108">Returns the description associated with the specified HTTP status code.</span></span>

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a><span data-ttu-id="9b14d-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b14d-109">Parameters</span></span>

<span data-ttu-id="9b14d-110">`code` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="9b14d-110">`code` <xref:System.Int32></span></span>

<span data-ttu-id="9b14d-111">Der HTTP-Statuscode, z `404` . b..</span><span class="sxs-lookup"><span data-stu-id="9b14d-111">The HTTP status code, for example, `404`.</span></span>

### <a name="return-value"></a><span data-ttu-id="9b14d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9b14d-112">Return value</span></span>

<xref:System.String?displayProperty=nameWithType>

<span data-ttu-id="9b14d-113">Die http-Statusbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="9b14d-113">The HTTP status description.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b14d-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9b14d-114">Requirements</span></span>

<span data-ttu-id="9b14d-115">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="9b14d-115">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="9b14d-116">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="9b14d-116">**Assembly:** System (in System.dll)</span></span>
