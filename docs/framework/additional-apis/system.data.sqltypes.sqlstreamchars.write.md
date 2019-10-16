---
title: SqlStreamChars. Write (Char [], Int32, Int32)-Methode (System. Data. SqlTypes)
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
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395576"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="b6e95-102">SqlStreamChars. Write (Char [], Int32, Int32)-Methode</span><span class="sxs-lookup"><span data-stu-id="b6e95-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="b6e95-103">Schreibt beim Überschreiben in einer abgeleiteten Klasse eine Sequenz von Zeichen in den aktuellen Stream und erhöht die aktuelle Position in diesem Stream um die Anzahl der geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b6e95-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="b6e95-104">Die Assembly, die diese Methode enthält, hat eine Friend-Beziehung mit SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="b6e95-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="b6e95-105">Sie ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b6e95-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="b6e95-106">Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.</span><span class="sxs-lookup"><span data-stu-id="b6e95-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="b6e95-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6e95-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="b6e95-108">Ein Char-Array, das geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6e95-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="b6e95-109">Ein Offset relativ zum Ursprung.</span><span class="sxs-lookup"><span data-stu-id="b6e95-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="b6e95-110">Die Anzahl der Zeichen, die in den aktuellen Stream geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b6e95-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6e95-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6e95-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="b6e95-112">Die `SqlStreamChars.Write`-Methode ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6e95-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b6e95-113">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="b6e95-113">Microsoft does not support the use of this method write in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b6e95-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6e95-114">Requirements</span></span>

<span data-ttu-id="b6e95-115">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="b6e95-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="b6e95-116">**Assembly:** System. Data (in "System. Data. dll")</span><span class="sxs-lookup"><span data-stu-id="b6e95-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="b6e95-117">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="b6e95-117">**.NET Framework versions:** Available since 2.0.</span></span>
