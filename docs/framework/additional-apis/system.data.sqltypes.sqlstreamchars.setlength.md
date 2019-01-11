---
title: SqlStreamChars.SetLength(Int64)-Methode (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c7199cbd08e62b1f0391437a0c1864cb9036fe1f
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222697"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="02329-102">SqlStreamChars.SetLength(Int64)-Methode</span><span class="sxs-lookup"><span data-stu-id="02329-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="02329-103">Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die vom Datenstrom verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="02329-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="02329-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="02329-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="02329-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="02329-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="02329-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="02329-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="02329-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="02329-107">Parameters</span></span>

`value`\
<span data-ttu-id="02329-108">Die gewünschte Länge des aktuellen Streams in Bytes.</span><span class="sxs-lookup"><span data-stu-id="02329-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="02329-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02329-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="02329-110">Die `SqlStreamChars.SetLength` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="02329-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="02329-111">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="02329-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="02329-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02329-112">Requirements</span></span>

<span data-ttu-id="02329-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="02329-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="02329-114">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="02329-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="02329-115">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="02329-115">**.NET Framework versions:** Available since 2.0.</span></span>