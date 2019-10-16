---
title: SqlStreamChars. IsNull-Eigenschaft (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d80f653724b3ef0a1cadb69a5f72b1d9455597d6
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395737"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="e9df7-102">SqlStreamChars. IsNull (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="e9df7-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="e9df7-103">Ruft beim Überschreiben in einer abgeleiteten Klasse einen Wert ab, der angibt, ob der Stream `null` ist.</span><span class="sxs-lookup"><span data-stu-id="e9df7-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="e9df7-104">Die Assembly, die diese Eigenschaft enthält, hat eine Friend-Beziehung mit SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="e9df7-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="e9df7-105">Sie ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e9df7-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="e9df7-106">Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.</span><span class="sxs-lookup"><span data-stu-id="e9df7-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="e9df7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9df7-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="e9df7-108">Eigenschafts Wert</span><span class="sxs-lookup"><span data-stu-id="e9df7-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="e9df7-109">`true`, wenn der Stream `null` ist. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="e9df7-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9df7-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9df7-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e9df7-111">Die `SqlStreamChars.IsNull`-Eigenschaft ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9df7-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e9df7-112">Microsoft unterstützt die Verwendung dieser Eigenschaft in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="e9df7-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e9df7-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9df7-113">Requirements</span></span>

<span data-ttu-id="e9df7-114">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="e9df7-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="e9df7-115">**Assembly:** System. Data (in "System. Data. dll")</span><span class="sxs-lookup"><span data-stu-id="e9df7-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="e9df7-116">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="e9df7-116">**.NET Framework versions:** Available since 2.0.</span></span>
