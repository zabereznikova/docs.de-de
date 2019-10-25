---
title: Pooledstream. NetworkStream-Eigenschaft (System.net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 541b8c94b30675c1286b48a2291c3bd3e4aeea0b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847229"
---
# <a name="pooledstreamnetworkstream-property"></a><span data-ttu-id="d200f-102">Pooledstream. NetworkStream-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d200f-102">PooledStream.NetworkStream Property</span></span>

<span data-ttu-id="d200f-103">Ruft den Netzwerkstream für den `PooledStream` Socket ab oder legt ihn fest.</span><span class="sxs-lookup"><span data-stu-id="d200f-103">Gets or sets the network stream for the `PooledStream` socket.</span></span>

## <a name="syntax"></a><span data-ttu-id="d200f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d200f-104">Syntax</span></span>

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="d200f-105">Eigenschafts Wert</span><span class="sxs-lookup"><span data-stu-id="d200f-105">Property value</span></span>

<xref:System.Net.Sockets.NetworkStream>  
<span data-ttu-id="d200f-106">Der Netzwerkstream für den `PooledStream` Socket.</span><span class="sxs-lookup"><span data-stu-id="d200f-106">The network stream for the `PooledStream` socket.</span></span>

## <a name="remarks"></a><span data-ttu-id="d200f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d200f-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d200f-108">Die `PooledStream.NetworkStream`-Eigenschaft ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d200f-108">The `PooledStream.NetworkStream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d200f-109">Microsoft unterstützt die Verwendung dieser Eigenschaft in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="d200f-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d200f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d200f-110">Requirements</span></span>

<span data-ttu-id="d200f-111">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d200f-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d200f-112">**Assembly:** System (in "System. dll")</span><span class="sxs-lookup"><span data-stu-id="d200f-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d200f-113">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="d200f-113">**.NET Framework versions:** Available since 2.0.</span></span>
