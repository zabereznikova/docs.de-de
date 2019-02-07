---
title: SqlStreamChars.SetLength(Int64)-Methode (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 750b46c2050228f630eaa6be31922869bff15e0a
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827343"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="fc86b-102">SqlStreamChars.SetLength(Int64)-Methode</span><span class="sxs-lookup"><span data-stu-id="fc86b-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="fc86b-103">Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die vom Datenstrom verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="fc86b-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="fc86b-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="fc86b-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="fc86b-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="fc86b-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="fc86b-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fc86b-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="fc86b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc86b-107">Parameters</span></span>

`value`\
<span data-ttu-id="fc86b-108">Die gewünschte Länge des aktuellen Streams in Bytes.</span><span class="sxs-lookup"><span data-stu-id="fc86b-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc86b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc86b-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="fc86b-110">Die `SqlStreamChars.SetLength` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fc86b-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="fc86b-111">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="fc86b-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc86b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fc86b-112">Requirements</span></span>

<span data-ttu-id="fc86b-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="fc86b-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="fc86b-114">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="fc86b-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="fc86b-115">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="fc86b-115">**.NET Framework versions:** Available since 2.0.</span></span>