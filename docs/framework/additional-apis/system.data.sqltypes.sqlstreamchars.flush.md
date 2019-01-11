---
title: SqlStreamChars.Flush-Methode (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 13c4b9424b5fc16648628e2b1022a7f1621dee88
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221361"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="25b1f-102">SqlStreamChars.Flush-Methode</span><span class="sxs-lookup"><span data-stu-id="25b1f-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="25b1f-103">Löscht beim Überschreiben in einer abgeleiteten Klasse alle Puffer für diesen Stream und veranlasst die Ausgabe aller gepufferten Daten an das zugrunde liegende Gerät.</span><span class="sxs-lookup"><span data-stu-id="25b1f-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="25b1f-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="25b1f-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="25b1f-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="25b1f-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="25b1f-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="25b1f-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="25b1f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="25b1f-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="25b1f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25b1f-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="25b1f-109">Die `SqlStreamChars.Flush` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25b1f-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="25b1f-110">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="25b1f-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="25b1f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25b1f-111">Requirements</span></span>

<span data-ttu-id="25b1f-112">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="25b1f-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="25b1f-113">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="25b1f-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="25b1f-114">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="25b1f-114">**.NET Framework versions:** Available since 2.0.</span></span>