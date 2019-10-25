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
# <a name="pooledstreamnetworkstream-property"></a>Pooledstream. NetworkStream-Eigenschaft

Ruft den Netzwerkstream für den `PooledStream` Socket ab oder legt ihn fest.

## <a name="syntax"></a>Syntax

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a>Eigenschafts Wert

<xref:System.Net.Sockets.NetworkStream>  
Der Netzwerkstream für den `PooledStream` Socket.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `PooledStream.NetworkStream`-Eigenschaft ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Eigenschaft in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Net>

**Assembly:** System (in "System. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
