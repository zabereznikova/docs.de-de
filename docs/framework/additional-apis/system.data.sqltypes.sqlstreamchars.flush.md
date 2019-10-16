---
title: SqlStreamChars. Flush-Methode (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 38ade5ce38cfe5003b2d06c0d8bb2db1a20bc05b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395624"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="dbe7e-102">SqlStreamChars. Flush-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe7e-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="dbe7e-103">Löscht beim Überschreiben in einer abgeleiteten Klasse alle Puffer für diesen Stream und veranlasst die Ausgabe aller gepufferten Daten an das zugrunde liegende Gerät.</span><span class="sxs-lookup"><span data-stu-id="dbe7e-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="dbe7e-104">Die Assembly, die diese Methode enthält, hat eine Friend-Beziehung mit SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="dbe7e-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="dbe7e-105">Sie ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="dbe7e-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="dbe7e-106">Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.</span><span class="sxs-lookup"><span data-stu-id="dbe7e-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="dbe7e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbe7e-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="dbe7e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dbe7e-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="dbe7e-109">Die `SqlStreamChars.Flush`-Methode ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dbe7e-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="dbe7e-110">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="dbe7e-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="dbe7e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbe7e-111">Requirements</span></span>

<span data-ttu-id="dbe7e-112">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="dbe7e-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="dbe7e-113">**Assembly:** System. Data (in "System. Data. dll")</span><span class="sxs-lookup"><span data-stu-id="dbe7e-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="dbe7e-114">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="dbe7e-114">**.NET Framework versions:** Available since 2.0.</span></span>
