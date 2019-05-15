---
title: SqlStreamChars.Close-Methode (System.Data.SqlTypes)
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
ms.openlocfilehash: 942ee987f1c56abe2cb1718347886dd397e7217e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634340"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="5087a-102">SqlStreamChars.Close-Methode</span><span class="sxs-lookup"><span data-stu-id="5087a-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="5087a-103">Schließt den aktuellen Stream und gibt alle dem Stream zugeordneten Systemressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="5087a-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="5087a-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="5087a-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5087a-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="5087a-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="5087a-106"> Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5087a-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="5087a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5087a-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5087a-108">Die `SqlStreamChars.Close` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5087a-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5087a-109">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="5087a-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5087a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5087a-110">Requirements</span></span>

<span data-ttu-id="5087a-111">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="5087a-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="5087a-112">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="5087a-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5087a-113">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="5087a-113">**.NET Framework versions:** Available since 2.0.</span></span>
