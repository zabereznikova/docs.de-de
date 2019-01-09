---
title: SqlStreamChars.Flush-Methode (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ecaf7932a4e832a88b883ceac4746afe6140b38e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152743"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="68a25-102">SqlStreamChars.Flush-Methode</span><span class="sxs-lookup"><span data-stu-id="68a25-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="68a25-103">Löscht beim Überschreiben in einer abgeleiteten Klasse alle Puffer für diesen Stream und veranlasst die Ausgabe aller gepufferten Daten an das zugrunde liegende Gerät.</span><span class="sxs-lookup"><span data-stu-id="68a25-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="68a25-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="68a25-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="68a25-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="68a25-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="68a25-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="68a25-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="68a25-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="68a25-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="68a25-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68a25-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="68a25-109">Die `SqlStreamChars.Flush` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="68a25-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="68a25-110">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="68a25-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="68a25-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68a25-111">Requirements</span></span>

<span data-ttu-id="68a25-112">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="68a25-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="68a25-113">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="68a25-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="68a25-114">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="68a25-114">**.NET Framework versions:** Available since 2.0.</span></span>