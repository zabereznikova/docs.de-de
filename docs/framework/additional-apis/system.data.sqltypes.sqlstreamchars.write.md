---
title: SqlStreamChars.Write (Char [], Int32, Int32)-Methode (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4084c7161eaa91d78eab32f1c14624e0032cdfcf
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675756"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="d3e28-102">SqlStreamChars.Write (Char [], Int32, Int32)-Methode</span><span class="sxs-lookup"><span data-stu-id="d3e28-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="d3e28-103">Ruft beim Überschreiben in einer abgeleiteten Klasse schreibt eine Folge von Zeichen in den aktuellen Stream und erhöht die aktuelle Position im Stream um die Anzahl der geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d3e28-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="d3e28-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="d3e28-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="d3e28-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="d3e28-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="d3e28-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d3e28-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="d3e28-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d3e28-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="d3e28-108">Ein Char-Array geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="d3e28-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="d3e28-109">Ein Offset relativ zum Ursprung.</span><span class="sxs-lookup"><span data-stu-id="d3e28-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="d3e28-110">Die Anzahl der Zeichen in den aktuellen Stream geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d3e28-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3e28-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3e28-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d3e28-112">Die `SqlStreamChars.Write` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d3e28-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d3e28-113">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="d3e28-113">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d3e28-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d3e28-114">Requirements</span></span>

<span data-ttu-id="d3e28-115">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="d3e28-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="d3e28-116">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="d3e28-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="d3e28-117">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="d3e28-117">**.NET Framework versions:** Available since 2.0.</span></span>
