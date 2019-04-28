---
title: SqlStreamChars.Length-Eigenschaft (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c2ef66fa493512e1fa062e22858ea251ced39453
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705843"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="29fc2-102">SqlStreamChars.Length-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="29fc2-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="29fc2-103">Ruft beim Überschreiben in einer abgeleiteten Klasse ruft die Länge des aktuellen Streams ab.</span><span class="sxs-lookup"><span data-stu-id="29fc2-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="29fc2-104">Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="29fc2-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="29fc2-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="29fc2-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="29fc2-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="29fc2-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="29fc2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="29fc2-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="29fc2-108">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="29fc2-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="29fc2-109">Die Länge des Streams.</span><span class="sxs-lookup"><span data-stu-id="29fc2-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="29fc2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29fc2-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="29fc2-111">Die `SqlStreamChars.Length` -Eigenschaft ist privat und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="29fc2-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="29fc2-112">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="29fc2-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="29fc2-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29fc2-113">Requirements</span></span>

<span data-ttu-id="29fc2-114">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="29fc2-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="29fc2-115">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="29fc2-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="29fc2-116">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="29fc2-116">**.NET Framework versions:** Available since 2.0.</span></span>