---
title: SqlStreamChars.Dispose(Boolean)-Methode (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4e6cfd6d4c04b1a2835b6e34b82c95b564dea588
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826862"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="46b4e-102">SqlStreamChars.Dispose(Boolean)-Methode</span><span class="sxs-lookup"><span data-stu-id="46b4e-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="46b4e-103">Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die vom Datenstrom verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="46b4e-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="46b4e-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="46b4e-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="46b4e-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="46b4e-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="46b4e-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="46b4e-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="46b4e-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="46b4e-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="46b4e-108">`true`, um sowohl verwaltete als auch nicht verwaltete Ressourcen freizugeben, `false`, um ausschließlich nicht verwaltete Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="46b4e-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="46b4e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46b4e-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="46b4e-110">Die `SqlStreamChars.Dispose` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="46b4e-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="46b4e-111">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="46b4e-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="46b4e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46b4e-112">Requirements</span></span>

<span data-ttu-id="46b4e-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="46b4e-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="46b4e-114">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="46b4e-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="46b4e-115">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="46b4e-115">**.NET Framework versions:** Available since 2.0.</span></span>