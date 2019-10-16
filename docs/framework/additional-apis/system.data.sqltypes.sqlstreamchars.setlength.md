---
title: SqlStreamChars. SetLength (Int64)-Methode (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 291d6e9395581f2370dafc728521a314d54a686d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395725"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="c06bb-102">SqlStreamChars. SetLength (Int64)-Methode</span><span class="sxs-lookup"><span data-stu-id="c06bb-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="c06bb-103">Gibt beim Überschreiben in einer abgeleiteten Klasse die vom Stream verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="c06bb-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="c06bb-104">Die Assembly, die diese Methode enthält, hat eine Friend-Beziehung mit SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="c06bb-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="c06bb-105">Sie ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c06bb-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="c06bb-106">Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.</span><span class="sxs-lookup"><span data-stu-id="c06bb-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="c06bb-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c06bb-107">Parameters</span></span>

`value`\
<span data-ttu-id="c06bb-108">Die gewünschte Länge des aktuellen Streams in Bytes.</span><span class="sxs-lookup"><span data-stu-id="c06bb-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="c06bb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c06bb-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c06bb-110">Die `SqlStreamChars.SetLength`-Methode ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c06bb-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c06bb-111">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="c06bb-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c06bb-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c06bb-112">Requirements</span></span>

<span data-ttu-id="c06bb-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="c06bb-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="c06bb-114">**Assembly:** System. Data (in "System. Data. dll")</span><span class="sxs-lookup"><span data-stu-id="c06bb-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="c06bb-115">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="c06bb-115">**.NET Framework versions:** Available since 2.0.</span></span>
