---
title: SqlStreamChars.Seek ("Int64", "SeekOrigin")-Methode (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 1710c802324920e324b18ddea843f0a532fa0d17
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222986"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="3acd2-102">SqlStreamChars.Seek ("Int64", "SeekOrigin")-Methode</span><span class="sxs-lookup"><span data-stu-id="3acd2-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="3acd2-103">Legt beim Überschreiben in einer abgeleiteten Klasse die Position im aktuellen Stream fest.</span><span class="sxs-lookup"><span data-stu-id="3acd2-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="3acd2-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="3acd2-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="3acd2-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="3acd2-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="3acd2-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3acd2-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="3acd2-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="3acd2-107">Parameters</span></span>

`offset`\
<span data-ttu-id="3acd2-108">Ein Byteoffset relativ zum `origin`.</span><span class="sxs-lookup"><span data-stu-id="3acd2-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="3acd2-109">Einer der Enumerationswerte, der den Bezugspunkt, von dem aus die neue Position ermittelt angibt.</span><span class="sxs-lookup"><span data-stu-id="3acd2-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="3acd2-110">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="3acd2-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="3acd2-111">Die neue Position innerhalb des aktuellen Streams.</span><span class="sxs-lookup"><span data-stu-id="3acd2-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="3acd2-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3acd2-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="3acd2-113">Die `SqlStreamChars.Seek` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3acd2-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3acd2-114">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="3acd2-114">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3acd2-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3acd2-115">Requirements</span></span>

<span data-ttu-id="3acd2-116">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="3acd2-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="3acd2-117">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="3acd2-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="3acd2-118">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="3acd2-118">**.NET Framework versions:** Available since 2.0.</span></span>