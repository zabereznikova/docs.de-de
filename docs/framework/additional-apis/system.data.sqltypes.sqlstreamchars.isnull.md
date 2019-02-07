---
title: SqlStreamChars.IsNull-Eigenschaft (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 7d2a2cf66ce2a375b1e5989b2fb6ddc9e3d94411
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825445"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="111fb-102">SqlStreamChars.IsNull-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="111fb-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="111fb-103">Ruft beim Überschreiben in einer abgeleiteten Klasse ruft einen Wert, der angibt, ob der Datenstrom ist `null`.</span><span class="sxs-lookup"><span data-stu-id="111fb-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="111fb-104">Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="111fb-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="111fb-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="111fb-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="111fb-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="111fb-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="111fb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="111fb-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="111fb-108">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="111fb-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="111fb-109">`true` Wenn der Stream `null`ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="111fb-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="111fb-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="111fb-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="111fb-111">Die `SqlStreamChars.IsNull` -Eigenschaft ist privat und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="111fb-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="111fb-112">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="111fb-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="111fb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="111fb-113">Requirements</span></span>

<span data-ttu-id="111fb-114">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="111fb-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="111fb-115">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="111fb-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="111fb-116">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="111fb-116">**.NET Framework versions:** Available since 2.0.</span></span>