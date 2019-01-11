---
title: SqlStreamChars.Dispose(Boolean)-Methode (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
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
ms.openlocfilehash: 930a4a69c6c44269e728fbcef62e561ab165ea22
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222362"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="797c9-102">SqlStreamChars.Dispose(Boolean)-Methode</span><span class="sxs-lookup"><span data-stu-id="797c9-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="797c9-103">Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die vom Datenstrom verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="797c9-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="797c9-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="797c9-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="797c9-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="797c9-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="797c9-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="797c9-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="797c9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="797c9-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="797c9-108">`true`, um sowohl verwaltete als auch nicht verwaltete Ressourcen freizugeben, `false`, um ausschließlich nicht verwaltete Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="797c9-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="797c9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="797c9-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="797c9-110">Die `SqlStreamChars.Dispose` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="797c9-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="797c9-111">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="797c9-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="797c9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="797c9-112">Requirements</span></span>

<span data-ttu-id="797c9-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="797c9-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="797c9-114">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="797c9-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="797c9-115">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="797c9-115">**.NET Framework versions:** Available since 2.0.</span></span>