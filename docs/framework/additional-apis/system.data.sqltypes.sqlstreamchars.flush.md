---
title: SqlStreamChars.Flush-Methode (System.Data.SqlTypes)
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
ms.openlocfilehash: 411bd0036de904dd485d9fb54fa5fd45e3b55dbb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634336"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="d7d0b-102">SqlStreamChars.Flush-Methode</span><span class="sxs-lookup"><span data-stu-id="d7d0b-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="d7d0b-103">Löscht beim Überschreiben in einer abgeleiteten Klasse alle Puffer für diesen Stream und veranlasst die Ausgabe aller gepufferten Daten an das zugrunde liegende Gerät.</span><span class="sxs-lookup"><span data-stu-id="d7d0b-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="d7d0b-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="d7d0b-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="d7d0b-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="d7d0b-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="d7d0b-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d7d0b-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="d7d0b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7d0b-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="d7d0b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7d0b-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d7d0b-109">Die `SqlStreamChars.Flush` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d7d0b-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d7d0b-110">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="d7d0b-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7d0b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7d0b-111">Requirements</span></span>

<span data-ttu-id="d7d0b-112">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="d7d0b-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="d7d0b-113">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="d7d0b-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="d7d0b-114">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="d7d0b-114">**.NET Framework versions:** Available since 2.0.</span></span>
