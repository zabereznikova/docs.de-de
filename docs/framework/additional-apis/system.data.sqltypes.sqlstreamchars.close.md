---
title: SqlStreamChars. Close-Methode (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c33c60842d181be7011528ca7550f3d09f291f43
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395639"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="87c30-102">SqlStreamChars. Close-Methode</span><span class="sxs-lookup"><span data-stu-id="87c30-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="87c30-103">Schließt den aktuellen Stream und gibt alle dem Stream zugeordneten Systemressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="87c30-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="87c30-104">Die Assembly, die diese Methode enthält, hat eine Friend-Beziehung mit SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="87c30-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="87c30-105">Sie ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="87c30-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="87c30-106"> Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.</span><span class="sxs-lookup"><span data-stu-id="87c30-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="87c30-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87c30-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="87c30-108">Die `SqlStreamChars.Close`-Methode ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87c30-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="87c30-109">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="87c30-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="87c30-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87c30-110">Requirements</span></span>

<span data-ttu-id="87c30-111">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="87c30-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="87c30-112">**Assembly:** System. Data (in "System. Data. dll")</span><span class="sxs-lookup"><span data-stu-id="87c30-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="87c30-113">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="87c30-113">**.NET Framework versions:** Available since 2.0.</span></span>
