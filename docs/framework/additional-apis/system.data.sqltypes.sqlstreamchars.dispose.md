---
title: SqlStreamChars.Dispose(Boolean)-Methode (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 2cad6015c1c4d72300d8413b7accead12f79a0be
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634301"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="e9e65-102">SqlStreamChars.Dispose(Boolean)-Methode</span><span class="sxs-lookup"><span data-stu-id="e9e65-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="e9e65-103">Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die vom Datenstrom verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="e9e65-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="e9e65-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="e9e65-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="e9e65-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e9e65-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="e9e65-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e9e65-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="e9e65-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9e65-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="e9e65-108">`true`, um sowohl verwaltete als auch nicht verwaltete Ressourcen freizugeben, `false`, um ausschließlich nicht verwaltete Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="e9e65-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9e65-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9e65-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e9e65-110">Die `SqlStreamChars.Dispose` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9e65-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e9e65-111">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="e9e65-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e9e65-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9e65-112">Requirements</span></span>

<span data-ttu-id="e9e65-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="e9e65-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="e9e65-114">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="e9e65-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="e9e65-115">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="e9e65-115">**.NET Framework versions:** Available since 2.0.</span></span>
